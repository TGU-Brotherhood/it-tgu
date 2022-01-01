# Hướng dẫn markdown trên Github

# Cú pháp định dạng và cách viết cơ bản

Tạo định dạng cho đoạn văn và mã của bạn trên GitHub với cú pháp đơn giản

## Phần đầu (Heading)

Để tạo tiêu đê trong Markdown, hãy thêm một dấu **`#`** trước tiêu đề của bạn. Số lượng dấu **`#`** mà bạn sử dụng sẽ xác định kích thước của tiêu đề. Ví dụ:

> #The largest heading  
> ##The second largest heading  
> ######The smallest heading

# The largest heading

## The second largest heading

###### The smallest heading

<br>


## Kiểu văn bản (Styling text)

Bạn có thể biêu thị sự nhấn mạnh văn bản im đậm, in nghiêng hoặc gạch ngang trong các trường nhận xét và tệp `.md`

| Kiểu                                                    | Cú pháp              | Phím tắt           | Ví dụ                                    | Output                                 |
| ------------------------------------------------------- | -------------------- | ------------------ | ---------------------------------------- | -------------------------------------- |
| Bold(chữ đậm)                                           | `** **` hoặc `__ __` | command/control +B | `**This is bold text**`                  | **This is bold text**                  |
| Italic(chữ nghiêng)                                     | `* *` hoặc `_ _`     | command/control +i | `*This text is italic*`                  | _This text is italic_                  |
| Strikethrough(Gạch ngang)                               | `~~ ~~`              |                    | `~~This was mistaken text~~`             | ~~This was mistaken text~~             |
| Bold and nested italic (In đậm và in nghiêng lồng nhau) | `** **` và `_ _`     |                    | `**This text is _extremely_ important**` | **This text is _extremely_ important** |
| All bold and italic (In đậm và in nghiêng)               | `*** ***`            |                    | `***All this text is important ***`      | **_All this text is important_**       |

<br>


## Trích dẫn văn bản (Quoting text)

Bạn có thể trích dẫn văn bản chỉ với dấu **`>`** trước mỗi đoạn văn bản cẩn trích dẫn.

> `Text that is not a quote.`  
> `>Text that is a quote.`

Text that is not a quote.

> Text that is a quote.

`Mẹo vặt: Khi xem một cuộc hội thoại, bạn có thể tự động trích dẫn văn bản trong nhận xét bằng cách đánh đấu văn bản, sau đó nhập phím _`r`_.`

<br>


## Mã trích dẫn (Quoting code)

Bạn có thể gọi ra mã hoặc một lênh trong một câu có dấu gạch ngược đơn. Khi đó văn bản trong dấu gạch ngược sẽ không được định dạng. Bạn cũng có thể nhấn lệnh hoặc phím tắt _`Ctrl + e`_ để chèn dấu gạch ngược cho khối mã trong một dòng của Markdown.

> Sử dụng `git status` để liệt kê tất cả các tệp mới hoặc đã sửa đổi chưa được cam kết.

> Một số lệnh Git cơ bản là:

```
git status
git add
git commit
```  
Để biết thêm thông tin, hãy truy cập: "[Creating and highlighting code blocks](https://docs.github.com/es/github/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks)".

<br>

## Liên kết (Links)

Bạn có thể tạo liên kết nội tuyến bằng cách đặt văn bản liên kết trong dấu ngoặc `[]`, và sau đó đến gói URL trong dấu ngoặc đơn `()`. Bạn cũng có thể sử dụng phím tắt `Command + k` để tạo liên kết. Khi bạn đã chọn văn bản, bạn có thể dán URL từ khay nhớ tạm của mình để tự động tạo liên kết từ sự lựa chọn mà bạn đưa ra.

`This site was built using [GitHub Pages](https://pages.github.com/).`

This site was built using [GitHub Pages](https://pages.github.com/).

```
Mẹo: GitHub tự động tạo liên kết khi các URL hợp lệ được viết trong nhận xét.
```

<br>


## Liên kết phần (Section links)  

<br>


## Liên kết tương đối (Relative links)  

<br>



Bạn có thể xác định các liên kế tương đối và đường dẫn hình ảnh trong các tệp được kết xuất để giúp người đọc điều hướng đến các tệp khác nhau trong kho lưu trữ của bạn.

Liên kết tương đối là liên kết có liên quan đến tệp hiện tại. Ví dụ: nếu bạn có tệp README trong thư mục gốc của kho lưu trữ và bạn có tệp khác trong docs/CONTRIBUTING.md, liên kết cho CONTRIBUTING.md trong tệp README của bạn có thể trông giống như sau:  
`[Contribution guidelines for this project](docs/CONTRIBUTING.md)`

GitHub sẽ tự động chuyển đổi liên kết tương đối hoặc đường dẫn hình ảnh thành bất kì nhánh nào bạn đang hiện truy cập, để liên kết hoặc đường dẫn luôn hoạt động. Bạn có thể sử dụng tất cả các toán hạng của liên kết tương đối, chẳng hạn như `./` và `../`.

Các liên kết tương đối dễ dàng hơn cho người dùng nhân bản kho lưu trữ của bạn. Các liên kết tuyệt đối có thể không hoạt động trên các bản sao trong kho lưu trữ của bạn. Một điều là khuyên bạn nên sử dụng các liên kết tương đối để truy vấn các tệp trong kho lưu trữ của bạn.

<br>

## Hình ảnh (Images)

Bạn có thể hiển thị một hình ảnh bằng cách thêm `!` và gói văn bản thay thế trong `[]`. Sau đó bọc liên kết hình ảnh trong dấu ngoặc đơn `()`.  
`![This is an image](https://myoctocat.com/assets/images/base-octocat.svg)`  
![This is an image](https://myoctocat.com/assets/images/base-octocat.svg)

GitHub hỗ trợ nhúng hình ảnh vào các vấn đề của bạn, yêu cầu kéo, thảo luận, nhận xét và tệp `.md`. Bạn có thể hiển thị hình ảnh từ kho lưu trữ của mình, thêm liên kết đến hình ảnh trực tuyến hoặc tải ảnh lên hình ảnh.  
```
Mẹo: Khi bạn muốn hiển thị một hình ảnh trong kho lưu trữ của mình, bạn nên sử dụng liên kết tương đối thay vì liên kết tuyệt đối.
```

Dưới đây là một số ví dụ về việc sử dụng liên kết tương đối để hiển thị hình ảnh.

| Context                                                     | Relative Link                                                        |
| ----------------------------------------------------------- | -------------------------------------------------------------------- |
| In a `.md` file on the same branch                          | /assets/images/electrocat.png                                        |
| In a .md file on another branch                             | /../main/assets/images/electrocat.png                                |
| In issues, pull requests and comments of the repository     | ../blob/main/assets/images/electrocat.png                            |
| In a .md file in another repository                         | /../../../../github/docs/blob/main/assets/images/electrocat.png      |
| In issues, pull requests and comments of another repository | ../../../github/docs/blob/main/assets/images/electrocat.png?raw=true |

`Note: Hai liên kết tương đối cuối cùng trong bản trên sẽ chỉ hoạt động đối với hình ảnh trong kho lưu trữ riêng tư nếu người xem ít nhất có quyền truy cập đọc vào kho lưu trữ riêng tư chứa những hình ảnh này.`

<br>


### Chỉ định chủ đề mà một hình ảnh được hiển thị

Bạn có thể chỉ định chủ để mà hình ảnh được hiển thị bằng cách thêm `#gh-dark-mode-ony` hoặc `#gh-light-only` vào cuối URL hình ảnh, trong Markdown.

Chúng tôi phân biệt giữa hai chế độ màu sáng và tối, vì vậy có hai tuỳ chọn có sẵn. Bạn có thể sử dụng các tuỳ chọn này để hiển thị hình ảnh được tối ưu hoá cho nền tối hoặc sáng. Điều này thật hữu ích cho các hình ảnh PNG trong suốt.

| Context    | URL                                                                      |
| ---------- | ------------------------------------------------------------------------ |
| Dark Theme | `![GitHub Light](https://github.com/github-light.png#gh-dark-mode-only)` |
|Light Theme|`![GitHub Dark](https://github.com/github-dark.png#gh-light-mode-only)`|

<br>



## Danh sách (List)

Bạn có thể tạo một danh sách không có thứ tự bằng cách đặt trước một hoặc nhiều dòng văn bản với dấu  `-`  hoặc  `*` .

> Ngôn ngữ lập trình:  
> `-C/C++`  
> `-Java`  
>`-JavaScript`

- C/C++
- Java
- JavaScript

Để sắp xếp danh sách của bạn, hãy đánh số trước mỗi dòng

> Ngôn ngữ lập trình:  
> `1. Python`  
> `2. PHP`  
> `3. C#`

1. Python  
2. PHP  
3. C#

<br>

## Danh sách lồng nhau (Nested Lists)

<br>

Bạn có thể tạo danh sách lồng nhau bằng cách thụt lề một hoặc nhiều mục danh sách bên dưới một mục khác.

Để tạo danh sách lồng nhau bằng trình chỉnh sửa web trên GitHub hoặc trình soạn thảo văn bản sử dụng phông chữ monospaced, như Atom, bạn có thể chỉnh danh sách của mình một cách trực quan. Nhập các ký tự khoảng trắng trước danh sách lồng nhau của bạn, cho đến khi ký tự đánh dấu danh sách (`-` hoặc `*`) nằm ngay bên dưới ký tự đầu tiên của văn bản trong mục phía trên mục đó.

>1. First list items  
>    - First nested list item  
>       - Second nested list item

Để tạo danh sách lồng nhau trong trình chỉnh sửa nhận xét trên GitHub, không sử dụng phông chữ monospaced, bạn có thể nhìn vào mục danh sách ngay phía trên danh sách lồng nhau và đếm số ký tự xuất hiện trước nội dung của mục đó. Sau đó, nhập số ký tự khoảng trắng đó vào trước mục danh sách lồng nhau.

Trong ví dụ này, bạn có thể thêm một mục danh sách lồng nhau dưới mục danh sách `100. First list item` bằng cách thụt lề cho mục danh sách lồng nhau tối thiểu năm dấu cách, vì có năm kí tự (`100.`) trước `First list item`.

>100. First list item  
>     `- First nested list item`

100. First list item
     - First nested list item  


Bạn có thể tạo nhiều cấp danh sách lồng nhau bằng cùng một phương pháp. Ví dụ: vì mục danh sách lồng nhau đầu tiên có bảy ký tự trước danh sách lồng nhau `First nested list item`, bạn phải thụt lùi cho danh sách lồng nhau thứ hai bảy dấu cách.

> 100. First list item  
>      - First nested list item  
>        - Second nested list item

Để biết thêm ví dụ, hãy truy cập [GitHub Flavored Markdown Spec](https://github.github.com/gfm/#example-265).

<br>

## Danh sách công việc (Task lists)

Để tạo danh sách việc cần làm, hãy nhập các mục danh sách bằng ký tự khoảng trắng thông thường, sau đó là `[]`. Để đánh dấu một công việc là đã hoàn thành, hãy sử dụng `[x]`.

> `- [x] #739`  
> `- [] https://github.com/octo-org/octo-repo/issues/740`  
> `- [] Add delight to the experience when all tasks are complete :tada:`

- [x] #739
- [ ] https://github.com/octo-org/octo-repo/issues/740  
- [ ] Add delight to the experience when all tasks are complete :tada:

Nếu mô tả mục trong danh sách nhiệm vụ bắt đầu bằng dấu ngoặc đơn, bạn cần phải thoát khỏi nó bằng `\`:  
`- [ ] \(Optional) Open a followup issue`  

Để biết thêm thông tin, hãy xem: "[About task lists](https://docs.github.com/es/issues/tracking-your-work-with-issues/about-task-lists)".

<br>

## Đề cập đến với mọi người và nhóm (Metioning people and teams)

<br>

Bạn có thể đề cập đến một người hoặc *nhóm* trên GitHub bằng cách nhập `@` cùng với tên người dùng hoặc tên nhóm của họ. Điều này sẽ kích hoạt thông báo và thu hút sự chú ý của họ vào cuộc trò chuyện. Mọi người cũng sẽ nhận được thông báo nếu bạn chỉnh sửa nhận xét đề cập đến tên người dùng hoặc tên nhóm của họ. Để biết thêm thông tin về thông báo, hãy xem: "[About notification](https://docs.github.com/es/account-and-profile/managing-subscriptions-and-notifications-on-github/setting-up-notifications/about-notifications)".   
`@github/support What do you think about these updates?`  

@github/support What do you think about these updates?

<br>

Khi bạn đề cập đến nhóm chính, các thành viên của nhóm con cũng nhận được thông báo, giúp đơn giản hóa việc giao tiếp với nhiều nhóm người. Để biết thêm thông tin, hãy xem "[About team](https://docs.github.com/es/organizations/organizing-members-into-teams/about-teams)".

Gõ ký hiệu `@` sẽ hiển thị danh sách người hoặc nhóm trong một dự án. Danh sách lọc khi bạn nhập, vì vậy khi bạn tìm thấy tên của người hoặc nhóm bạn đang tìm kiếm, bạn có thể sử dụng các phím mũi tên để chọn và nhấn tab hoặc enter để hoàn thành tên. Đối với các nhóm, hãy nhập @ tổ chức / tên nhóm và tất cả các thành viên của nhóm đó sẽ được đăng ký tham gia cuộc trò chuyện.  

Các kết quả tự động hoàn thành bị hạn chế đối với các cộng tác viên của kho lưu trữ và bất kỳ người tham gia nào khác trên chuỗi.

<br>

## Tham chiếu các vấn đề và yêu cầu kéo (Referencing issues and pull requests)

Bạn có thể hiển thị danh sách các vấn đề được đề xuất và lấy các yêu cầu trong kho lưu trữ bằng cách nhập `#`. Nhập vấn đề hoặc số yêu cầu kéo hoặc tiêu đề để lọc danh sách, sau đó nhấn một trong hai tab hoặc enter để hoàn thành kết quả được đánh dấu.  

Để biết thêm thông tin, hãy xem "[Autolinked Reference and URLS](https://docs.github.com/es/github/writing-on-github/working-with-advanced-formatting/autolinked-references-and-urls)".

<br>

## Tham khảo các nguồn bên ngoài (Referencing external resources)

Nếu các tham chiếu tự liên kết tùy chỉnh được định cấu hình cho một kho lưu trữ, thì các tham chiếu đến tài nguyên bên ngoài, chẳng hạn như báo cáo sự cố JIRA hoặc vé Zendesk, sẽ trở thành liên kết rút gọn. Để tìm hiểu những liên kết tự động nào có sẵn trong kho lưu trữ của bạn, hãy liên hệ với người có quyền quản trị trên đó. 

<br>

## Tải lên nội dung (Uploading assets)

Bạn có thể tải lên các nội dung như hình ảnh bằng cách kéo và thả, chọn từ trình duyệt tệp hoặc dán. Bạn có thể tải nội dung lên các vấn đề, yêu cầu kéo, nhận xét và tệp .md trong kho lưu trữ của mình.

<br>

## Sử dụng biểu tượng cảm xúc (Using emoji)

Bạn có thể thêm biểu tượng cảm xúc vào bài viết của mình bằng cách nhập `:EMOJICODE:`.  
`@octocat :+1: This PR looks great - it's ready to merge! :shipit:`

@octocat :+1: This PR looks great - it's ready to merge! :shipit:

<br>

Nhập vào `:` sẽ hiển thị danh sách các biểu tượng cảm xúc được đề xuất. Danh sách sẽ lọc khi bạn nhập, vì vậy khi bạn tìm thấy biểu tượng cảm xúc mà bạn đang tìm kiếm, hãy nhấn **Tab** hoặc **Enter** để hoàn thành kết quả được đánh dấu.  

Để có danh sách đầy đủ các biểu tượng và mã biểu tượng cảm xúc có sẵn, hãy xem "[the Emoji-Cheat-Sheet](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md)".

<br>

## Đoạn văn (Paragraphs)

Bạn có thể tạo một đoạn văn mới bằng cách để trống một dòng giữa các dòng văn bản.

<br>

## Chú thích (Footnotes)

Bạn có thể thêm chú thích cuối trang vào nội dung của mình bằng cách sử dụng cú pháp ngoặc này:

>Đây là một chú thích đơn giản [^ 1].

>Chú thích cuối trang cũng có thể có nhiều dòng [^ 2].

>Bạn cũng có thể sử dụng các từ để phù hợp hơn với phong cách viết của mình [^ note].

>[^ 1]: Tài liệu tham khảo của tôi.  
>[^ 2]: Mỗi dòng mới phải được bắt đầu bằng 2 dấu cách.  
    `Điều này cho phép bạn có một chú thích với nhiều dòng.`  
>[^ note]:  
>Các chú thích được đặt tên sẽ vẫn hiển thị bằng số thay vì văn bản nhưng cho phép xác định và liên kết dễ dàng hơn.  
>Chú thích cuối trang này cũng đã được thực hiện với một cú pháp khác, sử dụng 4 dấu cách cho các dòng mới.


```
Lưu ý: Vị trí của chú thích cuối trang trong Markdown của bạn không ảnh hưởng đến vị trí của chú thích sẽ được hiển thị. Bạn có thể viết chú thích cuối trang ngay sau khi bạn tham chiếu đến chú thích cuối trang và chú thích cuối trang sẽ vẫn hiển thị ở cuối Markdown.
```
<br>

## Ẩn nội dung có nhận xét (Hiding content with comments)

Bạn có thể yêu cầu GitHub ẩn nội dung khỏi Markdown được hiển thị bằng cách đặt nội dung vào một nhận xét HTML.

`<!-- This content will not appear in the rendered Markdown -->`

<br>

## Bỏ qua định dạng Markdown (Ignoring Markdown formatting)

Bạn có thể yêu cầu GitHub bỏ qua (hoặc thoát) định dạng Markdown bằng cách sử dụng `\` trước ký tự Markdown.

`Let's rename \*our-new-project\* to \*our-old-project\*.`

Let's rename \*our-new-project\* to \*our-old-project\*.

Để biết thêm thông tin, hãy xem [Markdown Syntax](https://daringfireball.net/projects/markdown/syntax#backslash).

<br>

## Tắt hiển thị Markdown (Disabling Markdown rendering)

Khi xem tệp đánh dấu, bạn có thể nhấp vào `<>` trên cùng của tệp đó để tắt hiển thị ngôn ngữ đánh dấu và thay vào đó xem mã nguồn của tệp.

Việc tắt thông dịch ngôn ngữ đánh dấu cho phép bạn sử dụng các tính năng xem mã nguồn, chẳng hạn như liên kết dòng, không thể thực hiện được khi xem tệp được thông dịch ngôn ngữ đánh dấu.

<br>

## Đọc thêm (Further reading)

- [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
- [About writting and formatting on GitHub](https://docs.github.com/es/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/about-writing-and-formatting-on-github)
- [Working and advanced formatting](https://docs.github.com/es/github/writing-on-github/working-with-advanced-formatting)
- [Mastering Markdown](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

