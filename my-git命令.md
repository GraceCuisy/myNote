### 在工作区中改错了文件, 不小心改了同事的文件,将你在工作区中的修改退回去
      git checkout -- 回退的文件名
  或者 git restore 回退的文件名
### 提交到仓库的版本的回退准确叫版本穿梭
  git log 找到版本号
  git reset --hard 版本号
  