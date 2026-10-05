1\. Mục tiêu

Tạo và cấu hình tệp .gitignore.

Ngăn Git theo dõi các tệp chứa thông tin nhạy cảm.

Gỡ tệp credentials.txt khỏi vùng theo dõi của Git nhưng vẫn giữ tệp trên máy tính.

Sử dụng git commit --amend để chỉnh sửa thông điệp của commit gần nhất.

Kiểm tra trạng thái repository và lịch sử commit sau khi thực hiện.

2\. Yêu cầu



Trong bài thực hành, tệp credentials.txt đã được đưa vào Git. Tệp này chứa thông tin nhạy cảm nên cần được gỡ khỏi Git nhưng không được xóa khỏi thư mục làm việc.



Để giải quyết vấn đề, sử dụng:



git rm --cached credentials.txt



Sau đó thêm credentials.txt vào .gitignore để Git không theo dõi tệp này trong tương lai.



3\. Tạo tệp .gitignore



Tạo tệp có tên:



.gitignore



Nội dung:



\# Sensitive files

credentials.txt



\# Environment files

.env



\# IDE files

.idea/

.vscode/



\# Operating system files

.DS\_Store

Thumbs.db



Trong đó dòng:



credentials.txt



giúp Git bỏ qua tệp credentials.txt trong các lần thay đổi tiếp theo.



4\. Gỡ credentials.txt khỏi Git Tracking



Tệp credentials.txt đã được Git theo dõi nên chỉ thêm vào .gitignore là chưa đủ.



Sử dụng lệnh:



git rm --cached credentials.txt



Tùy chọn --cached chỉ gỡ tệp khỏi Git Index/Tracking, không xóa tệp vật lý khỏi máy tính.



Sau khi thực hiện:



Git Tracking

&#x20;   ↓

credentials.txt được gỡ khỏi Git



Working Directory

&#x20;   ↓

credentials.txt vẫn còn trên máy



Kiểm tra trạng thái:



git status

5\. Commit thay đổi



Thêm tệp .gitignore:



git add .gitignore



Tạo commit:



git commit -m "Remove credentials from tracking"

6\. Sử dụng git commit --amend



Để chỉnh sửa thông điệp của commit gần nhất, sử dụng:



git commit --amend -m "Update gitignore and remove credentials"



Lệnh --amend cho phép chỉnh sửa commit gần nhất thay vì tạo thêm một commit mới.



7\. Kiểm tra lịch sử commit



Sử dụng:



git log -n 1



Kết quả mong đợi:



commit <commit\_hash>

Author: <author>

Date:   <date>



&#x20;   Update gitignore and remove credentials



Thông điệp:



Update gitignore and remove credentials



chứng minh commit gần nhất đã được sửa bằng git commit --amend.



8\. Kiểm tra tệp credentials.txt



Sau khi sử dụng:



git rm --cached credentials.txt



tệp credentials.txt vẫn tồn tại trong thư mục làm việc.



Có thể kiểm tra bằng:



dir credentials.txt



Kết quả cho thấy tệp vẫn tồn tại trên máy tính.



Điều này đáp ứng yêu cầu không xóa tệp vật lý.



9\. Kiểm tra trạng thái cuối cùng



Sử dụng:



git status



Kết quả mong đợi:



nothing to commit, working tree clean



Tệp credentials.txt không còn được Git theo dõi và đã được cấu hình trong .gitignore.



10\. Các lệnh chính đã sử dụng

Tạo .gitignore

credentials.txt

Gỡ file khỏi Git nhưng giữ file trên máy

git rm --cached credentials.txt

Thêm .gitignore

git add .gitignore

Tạo commit

git commit -m "Remove credentials from tracking"

Sửa commit gần nhất

git commit --amend -m "Update gitignore and remove credentials"

Kiểm tra lịch sử commit

git log -n 1

Kiểm tra trạng thái

git status

11\. Kết quả



Sau khi hoàn thành bài thực hành:



Đã tạo tệp .gitignore.

Đã cấu hình credentials.txt vào .gitignore.

Đã sử dụng git rm --cached credentials.txt để gỡ tệp khỏi Git Tracking.

Tệp credentials.txt vẫn được giữ lại trên máy tính.

Đã sử dụng git commit --amend để sửa thông điệp commit gần nhất.

Đã sử dụng git log -n 1 để kiểm tra commit sau khi amend.

Repository ở trạng thái sạch sau khi hoàn thành.

