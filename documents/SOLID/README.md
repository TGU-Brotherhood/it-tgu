# S.O.L.I.D

SOLID là 5 nguyên tắc thiết kế hướng đối tượng để thiết kế ra code dễ đọc, dễ hiểu, dễ bảo trì,...

5 nguyên tắc bao gồm:

- [S.O.L.I.D](#solid)
  - [Single Responsibility Principle](#single-responsibility-principle)
  - [Open/Close Principle](#openclose-principle)
  - [Liskov Substitution Principle](#liskov-substitution-principle)
  - [Interface Regregation Principle](#interface-regregation-principle)
  - [Dependencies Inversion Principle](#dependencies-inversion-principle)

## Single Responsibility Principle

Nguyên tắc đơn trách nhiệm

> Mỗi class chỉ nên giữ 1 trách nhiệm duy nhất

:x: :x: Ví dụ sai: 

```Java
class Math {
  public int add(int a, int b) {
    return a + b;
  }

  // Chức năng không phù hợp
  public void displayResult(int result){
    System.out.println(result);
  }
}
```

:heavy_check_mark: Ví dụ đúng:

```Java
// Class Math có trách nhiệm xử lý các chức năng tính toán
class Math {
  public int add(int a, int b){
    return a + b;
  }
}

// Class Log có trách nhiệm xử lý các chức năng hiện thị
class Logger {
  public void displayResult(int result){
    System.out.println(result);
  }
}
```

## Open/Close Principle

> Mở để mở rộng, đóng để sửa đổi. Ta có thể mở rộng một class thoải mái nhưng không được sửa đổi bên trong class đó.

:x: Ví dụ sai:

```Java
interface NhanVien {} 

class NhanVienSanXuat implements NhanVien {
  private Double luongCB;
  private Long soSP;
  private Double tongLuong;

  // getter & setter
}

class NhanVienVanPhong implements NhanVien{
  private Double luongCB;
  private Long soNgay;
  private Double tongLuong;

  // getter & setter
}

class TinhLuong {

  public void tinh(NhanVien nv) {
    if (nv == null) {
      throw new InvalidParameterException("Can not perform operation");
    }
    if (nv instanceof NhanVienSanXuat){
      NhanVienSanXuat sanxuat = (NhanVienSanXuat) nv;
      nv.setTongLuong(nv.getLuongCB() * nv.getSoSP());
    } else if (nv instanceof NhanVienVanPhong){
      NhanVienVanPhong vp = (NhanVienVanPhong) nv;
      nv.setTongLuong(nv.getLuongCB() * nv.getSoNgay());
    }
  }
}
```

Khi có yêu cầu mới về tính lương của nhân viên, ta buộc phải thay đổi class `TinhLuong`... Vi phạm `Open/Closed Principle`.

:heavy_check_mark: Ví dụ đúng:

```Java
interface NhanVien{
  void tinhLuong();
}

class NhanVienSanXuat implements NhanVien {
  private Double luongCB;
  private Long soSP;
  private Double tongLuong;

  // getter & setter

  @Override
  public void tinhLuong(){
    tongLuong = luongCB * soSP;
  }
}

class NhanVienVanPhong {
  private Double luongCB;
  private Long soNgay;
  private Double tongLuong;

  // getter & setter

  @Override
  public void tinhLuong(){
    tongLuong = soNgay * luongCB;
  }
}

class TinhLuong {
  public void tinh(NhanVien nv) {
    if (nv == null) {
      throw new InvalidParameterException("Can not perform operation");
    }
    nv.tinhLuong();
  }
}
```

Với cách này class được `Đóng` cho việc chỉnh sửa và `Mở` cho việc mở rộng. 

Ta có thể dễ dàng thêm loại nhân viên khác với cách tính lương khác mà không cần thay đổi class `TinhLuong`, Khi ta cần chỉnh sửa một class (cách tính lương của một loại nhân viên) thì ta chỉ cần chỉnh sửa class đó và không làm ảnh hưởng đến những class khác.

## Liskov Substitution Principle

> Các instance của lớp con có thể thay thế được instance lớp cha mà vẫn đảm bảo tính đúng đắn của chương trình.

:x: Ví dụ sai:

```Java
class PhuongTien {
  private String name;  
  // getters & setters

  public void doXang(){
    // chưc năng đổ xăng;
  } 
}

class XeMay extends PhuongTien{
  public void doXang() {
    System.out.println("Mở khóa và đổ xăng");
  }
}

class XeHoi extends PhuongTien{
  public void doXang() {
    System.out.println("Mở nắp xe và đổ xăng");
  }
}

class XeDap extends PhuongTien{
  public void doXang() {
    // Đừng dùng hàm này
    throw Exception("Xe đạp làm sao đổ xăng!!!");
  }
}

class QuanLyKho {
  List<PhuongTien> danhSachXe; 

  // Constructor

  public void doXangToanBo() {
    for(PhuongTien p: danhSachXe) {
      p.doXang();
    }
  }
}
```

Với cách này chương trình vẫn hoạt động nhưng nó sẽ báo lỗi nếu trong kho có xe đạp... Để chương trình ổn định lâu dài, ta cần chương trình báo lỗi ngay lúc biên dịch, tránh như trường hợp trên.

:heavy_check_mark: Ví dụ đúng:

```Java
interface PhuongTienDongCo {
  void doXang();
}

interface PhuongTienThoSo { }

class PhuongTien {
  private String name;  
  // getters & setters
}

class XeMay extends PhuongTien implements PhuongTienDongCo{
  public void doXang() {
    System.out.println("Mở khóa và đổ xăng");
  }
}

class XeHoi extends PhuongTien implements PhuongTienDongCo{
  public void doXang() {
    System.out.println("Mở nắp xe và đổ xăng");
  }
}

class XeDap extends PhuongTien implements PhuongTienThoSo{
  public void dapXe() {
    System.out.println("Đạp đạp");
  }
}

class QuanLyKho {
  List<PhuongTienDongCo> danhSachPhuongTienDongCo;
  List<PhuongTienThoSo> danhSachPhuongTienThoSo;

  public void doXangToanBo() {
    for(PhuongTienDongCo pt: danhSachPhuongTienDongCo){
      pt.doXang();
    }
  }
}
```

Với cách này ta hoàn toàn tuân thủ `Liskov Substitution Principle`. Mỗi thể hiện lớp con đều có thể thay thế lớp cha nhưng vẫn đảm bảo chương trình chạy đúng.

## Interface Regregation Principle

> Thay vì dùng 1 interface lớn ta nên tách thành nhiều interface nhỏ với mục đích cụ thể, client không nên phụ thuộc vào interface mà nó nó không sử dụng.

:x: Ví dụ sai:

```Java
interface NhanVien {
  void sanXuat();
  void tinhToan();
}

class SanXuat implements NhanVien {
  @Overrride
  public void sanXuat(){
    System.out.prinln("San xuat hang hoa");
  }

  @Override
  public void tinhToan(){
    throw Exception("Nhân viên sản xuất mà tính toán gì đâu!!!");
  }
}

class VanPhong implements NhanVien {
  @Override
  public void sanXuat(){
    throw Exception("Nhân viên văn phòng không có sản xuất gì đâu");
  }

  @Override
  public void tinhToan(){
    System.out.println("tính thu chi ...");
  }
}
```

Ví dụ trên sử dụng interface quá lớn, các class phải implement những method mà nó không sử dụng.

:heavy_check_mark: Ví dụ đúng:

```Java
interface NhanVien {
  void tinhLuong();
}

interface SanXuat extends NhanVien {
  void sanXuat();
}

interface VanPhong extends NhanVien {
  void tinhToan();
  void lamBaoCao();
}

class NhanVienSanXuat implements SanXuat {
  @Override
  public void sanXuat(){ 
    // Bussiness logic
  }

  @Override
  public void tinhLuong(){
    // TinhLuong logic
  }
}

class NhanVienVanPhong implements VanPhong {
  @Override
  public void tinhToan(){
    // Tinh toán thu chi logic
  }

  @Override
  public void lamBaoCao(){
    // Báo cáo logic
  }

  @Override
  public void tinhLuong(){
    // tính lương logic
  }
}
```

Như vậy, ta không cần phải implement những phương thức mà class không sử dụng.

## Dependencies Inversion Principle

> Các module cấp cao không nên phụ thuộc vào module cấp thấp (và ngược lại), cả 2 nên phụ thuộc vào Abstraction

> Các interface(abstraction) không nên phụ thuộc vào chi tiết mà ngược lại. Các class giao tiếp với nhau thông qua interface không phải qua implementation.

:x: Ví dụ sai:

```Java
class QuanLy {
  public void traLuong(Long idNhanVien) {
    Database db = new Database();
    db.save(daTraLuong(idNhanVien));

    Logger logger = new Logger();
    logger.info(daTraLuong(idNhanVien));

    EmailSender sender = new EmailSender();
    sender.sendMail(daTraLuong(idNhanVien));
  }
}
```

:heavy_check_mark: Ví dụ đúng:

```Java
interface Database {
  void save(String data);
}

interface Logger {
  void info(String data);
}

interface EmailSender {
  void sendMail(String data);
}

class SQLDatabase implements Database {
  public void save(String data) {
    // Bussiness Logic
  }
}

class CLILogger implements Logger {
  public void info(String data){
    // Bussiness Logic
  }
}

class GmailSender implements EmailSender {
  public void sendMail(String data) {
    // Bussiness logic
  }
}

class QuanLy {
  public void traLuong(Long idNhanVien){
    Database db = new SQLDatabase();
    db.save(daTraLuong(idNhanVien));

    Logger logger = new CLILogger();
    logger.info(daTraLuong(idNhanVien));

    EmailSender sender = new GmailSender();
    sender.sendMail(daTraLuong(idNhanVien));
  }
}
```

Như vậy module `QuanLy` không phụ thuộc vào module `SQLDatabase`, `CLILogger`, `GmailSender` mà nó phụ thuộc vào abstraction của những module đó. Ta có thể dễ dàng thay đổi mà ít làm ảnh hưởng đển bussiness logic của module `QuanLy`.

> Để đảm bảo thực hiện nguyên tắc này, người ta thường dùng Dependency Injection.

Ví dụ Dependency Injection

```Java
interface Database {
  void save(String data);
}

class SQLDatabase implements Database {
  public void save(String data) {
    System.out.println("INSERT INTO traluong...");
  }
}

class MongoDatabase implements Database {
  public void save(String data) {
    System.out.println("add vào traluong...");
  }
}

// ...

interface QuanLy {
  void traLuong(Long idNhanVien);
}

// Class QuanLyImpl chỉ sử dụng chứ không khởi tạo bất kỳ service nào
class QuanLyImpl implements QuanLy {
  private Database database;

  public QuanLyImpl(Database database) {
    this.database = database;
  }

  public void traLuong(Long idNhanVien) {
    database.save(daTraLuong(idNhanVien));

    // Ghi log

    // Send mail
  }
}

interface DatabaseInjector {
  public QuanLy getQuanLy();
}

// Inject service SQL database.
class SQLDatabaseInjector implements DatabaseInjector {
  public QuanLy getQuanLy(){
    return new QuanLyImpl(new SQLDatabase());
  }
}

// Inject service Mongo database.
class MongoDatabaseInjector implements DatabaseInjector {
  public QuanLy getQuanLy(){
    return new QuanLyImpl(new MongoDatabase());
  }
}
```

Như vậy ta đã xây dựng 1 hệ thống `dễ mở rộng và bảo trì`, các class `ít phụ thuộc vào nhau hơn`. Ta có thể thay đổi Loại database thành PostgreSQL, MySql, Cassandra,.. tùy ý mà không gây ảnh hưởng đến những class khác.

Cách sử dụng

```Java
public static void main(){
  DatabaseInjector dbInjector = null;
  QuanLy ql = null;

  dbInjector = new SQLDatabaseInjector();
  // dbInjector = new MongoDatabaseInjector();
  // inject các loại db khác cùng abstraction.
  ql = dbInjector.getQuanLy();
  ql.traLuong(1);
}
```