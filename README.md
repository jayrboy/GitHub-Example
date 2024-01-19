#### 4-12-2023

# Git (Version Control)
	การกระจาย code เพื่อ clone ไปในแต่ละเครื่อง local และกลับไปรวม code ที่ server

- หลักการพื้นฐาน
	แก้ไข code ได้ทุกที่ ทุกเวลา จะเก็บอยู่ในเครื่อง local -> แก้ไข -> sync -> update server
- ทำไมต้องใช้
	ติดตาม version
	ป้องกัน version


# Github (Git Server)
- สร้าง repository (Web)
	https://github.com/new
	- Public
	- Private

# Git bash Command

```sh
git version
git config --global user.email "j.jayox_@hotmail.com"
git config --global user.name "jayrboy"
git config --list
```

- เครื่องส่วนตัวค้าง user ไว้ตลอด
- เครื่องอื่น ใช้เสร็จต้อง unset ด้วย

# Git Work Flow
- Directory (ยังไม่มีการติดตาม)					
- Directory (Tracked) มีการติดตาม	git init		กระบวน
- Staging Area			git add		กระบวนการเอาไฟล์ไปเก็บ
- Local Repository		git commit      การเก็บข้อมูลเครื่องของผู้พัฒนา
- Git Server			git push 	อัปเดตขึ้นเซิฟเวอร์

# ลบไฟล์

```sh
git rm -r -cached .
git rm --cached index.html
```

# สร้างไฟล์
- vscode -> terminal -> git bash

```sh
touch app.js
touch index.html

git init
git status		# ยังไม่มีการติดตามจะเป็นตัว U = Untrack (No commit yet)

$ git add index.html				
$ git rm --cached index.html		
```

# Add ทุกไฟล์

```sh
git add .
```

# Log Message ดูประวัติ

```sh
git log
git log --oneline
git commit -m "Log Message"
git commit -m "add file to project"
```
<commit_id>: a3ece5e15aca62c54ac3d93df35c9021efbafd03
ID ของ Version นี้มากี่เวอร์ชั่นแล้ว

# แก้ไขไฟล์
- app.js

```sh
git add .
git -m --cached "change version"
```

# Git Diff

```sh
git log --oneline   		# เพื่อเอา ID
git diff a3ece5e eda		# V แรกอยู่ด้านล่าง
```

# Check out  กลับไป version ก่อนหน้า หรือ ยกเลิกการแก้ไขไฟล์

```sh
git checkout <file-name>
git reset --option
```

# ย้อนกลับไป version เก่าก่อนที่จะ add (หรืออาจเพิ่มไฟล์ด้วยไม่ได้ตั้งใจ)

```sh
git reset readme.txt
git reset --option <commit_id>
```
-	soft	: ลบ all commit ที่อยู่หลัง Commit ID แล้วนำไฟล์ที่เคยอยู่ใน Commit นั้นกลับมา Staging Area
-	mixed	: ลบ all commit ที่อยู่หลัง Commit ID แล้วนำไฟล์ที่เคยอยู่ใน Commit นั้นกลับมา Working Directory
-	hard	: ลบ all commit ที่อยู่หลัง Commit ID แล้ว ทำลายไฟล์ที่เคยอยู่ใน Commit

```sh
git reset --hard e1933bf
git show HEAD
```


##### Git Branching
## add

```sh
git branch
git checkout -b add-feature
git branch
```

#delete

```sh
git checkout master
git branch
git branch -d add-feature
git branch
```

#### How to
# new branch "report-sale" and new source code

```sh
$ git checkout -b report-sale
$ git branch
```

# Check source code and commit

```sh
$ git status
$ git add .
$ git commit -m "add report-sale"
```

# Switched to branch master
# ไม่ถูกแก้ไขเพราะว่าไปแก้ไขใน branch report-sale

```sh
$ git branch
$ git checkout master
```
