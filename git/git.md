# Git Style Guide

Đây là các quy ước thống nhất khi làm việc với `git`, để thuận tiện cho việc theo dõi và nhận thức được các công việc thực hiện trên mỗi nhánh code. Để cho gọn, ta chỉ tập trung vào các công việc thường gặp nhất.

# Table of contents

* [1. Rẽ nhánh](#1-branching)
* [2. Workflow diagram](#2-workflow-diagram)
* [3. Best practices](#3-best-practices)
* [Tài liệu tham chiếu](#references)


# 1. Branching

<table>
  <thead>
    <tr>
      <th>Tên nhánh</th>
      <th>Quy ước đặt tên</th>
      <th>Ghi chú</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Stable</td>
      <td>stable</td>
      <td>Nhánh ổn định: Chỉ chấp nhận các yêu cầu merge (PR) từ nhánh Working và các nhánh Hotfixes (không code trực tiếp trên nhánh này).</td>
    </tr>
    <tr>
      <td>Working</td>
      <td>master</td>
      <td>Nhánh phát triển: Chỉ chấp nhận các yêu cầu merge (PR) từ nhánh các nhánh Features/Issues và Hotfixes (không code trực tiếp trên nhánh này).</td>
    </tr>
    <tr>
      <td>Features/Issues</td>
      <td>topic-*</td>
      <td>Luôn rẽ từ ngọn (HEAD) của nhánh Working</td>
    </tr>
    <tr>
      <td>Hotfix</td>
      <td>hotfix-*</td>
      <td>Luôn rẽ từ nhánh Stable</td>
    </tr>
  </tbody>
</table>

## Các nhánh chính

Một repository sẽ luôn có 2 nhánh chính hoạt động:

* `master` - nhánh phát triển luôn chứa mã nguồn mới nhất cho bản phát hành tiếp theo.
* `stable` - nhánh ổn định mới nhất đã triển khai cho khách hàng. Trong quá trình phát triển hàng ngày, nhánh này sẽ không được tương tác.

Khi mã nguồn trên nhánh `master` được xem xét là ổn định và được triển khai thật, thì tất cả các thay đổi trên nhánh này sẽ được merge vào nhánh `stable` và tag với 1 số phiên bản phát hành mới. *Điều này được thực hiện thế nào sẽ được thảo luận sau.*

## Các nhánh hỗ trợ phát triển

Các nhánh hỗ trợ thường được sử dụng để hỗ trợ phát triển song song giữa các thành viên trong nhóm, dễ dàng theo dõi các tính năng đang được phát triển và hỗ trợ khắc phục các sự cố nóng sau khi đã triển khai. Không giống các nhánh chính, các nhánh này có thời gian sống ngắn và bị hạn chế, chúng có thể bị xóa bất cứ lúc nào sau khi nó hoàn tất nhiệm vụ.

Các nhánh này bao gồm:

* Features branches
* Bug branches
* Hotfix brances

Mỗi nhánh này có một mục đích cụ thể và có ràng buộc nghiêm ngặt, như: được rẽ từ nhánh nào và sẽ được merge vào nhánh đích nào sau khi kết thúc.

# 2. Workflow Diagram

![Git Branching Model](./gitflow.png)  

# 3. Best practices

Việc rẽ nhánh cần chọn tên ngắn và có mô tả

```bash
# good
$ git checkout -b topic-oauth-migration

# bad
$ git checkout -b login_fix
```


# References

* Ref: https://github.com/agis/git-style-guide
* Ref: https://gist.github.com/digitaljhelms/4287848