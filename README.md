1. Tạo 1 tk trên github.com (dùng mail cá nhân)
2. Download Git for Windows, cài vào máy
https://git-scm.com/download/win
3. Mở App Git Bash
4. Cấu hình xác thực với github.com bằng public key
- Tạo cặp private/public keys
ssh-keygen -t rsa -C "your-email-address"
vd:
ssh-keygen -t rsa -C "thuanlv@fpt.edu.vn"
- Copy nội dung file public key lên github.com
cat ~/.ssh/id_rsa.pub

Lab - Cơ bản về git
=======================
1. open git bash
2. cd ~/Desktop
3. mkdir -p myProjects/git-tutorial
4. cd myProjects/git-tutorial
pwd
ls -al
--Khởi tạo cấu trúc git
5. git init
ls -al
==> .git
cd .git
ls
cd ..
6. echo "#abc" > README.md
ls
cat README.md
--Add các files từ working directory
 sang staging area
7. git add .
--Commit files từ staging area sang local repository
8. git commit -m "git init"
9. Tạo remote repository name "git-tutorial"
trên github.com
10. Quay lại git bash
--Add remote url vào file config trong thư mục .git
git remote add origin git@github.com:your-account/git-tutorial.git
git branch -M main
--Đẩy lên remote branch main
git push -u origin main
11. Kiểm tra các branch hiện tại
git branch
* main
12. Tạo 1 nhánh mới
git checkout -b branch_name
vd:
git checkout -b abc
13. Kiểm tra nhánh vừa tạo
git branch
* abc
main
14. Tạo mới file ở nhánh abc
echo "123" > 123.txt
15. Kiểm tra trạng thái của git
git status
16. add file vừa tạo vào vùng staging và local repo
git add 123.txt
git commit -m "tao moi file 123.txt"
17. Đẩy nhánh vừa tạo lên remote repository
git push origin abc
18. Nhảy về nhánh main
git checkout main
ls 
==> Nhánh main ko file 123.txt
19. Gộp nhánh abc vào main
--Đứng từ nhánh main
git merge abc
ls
==> Nhánh main đã có file 123.txt
20. Update lên remote branch main
git push origin main
21. Xóa local branch
git branch -d abc
22. Kiểm tra tất cả các branch hiện có
git branch -a
22. Xóa remote branch
git push origin --delete abc
23. Kiểm tra branch đã bị xóa
git branch -a
