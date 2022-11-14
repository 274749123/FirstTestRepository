# something

**因为远程仓库新建时，有LIENCE，由于本地仓库和远程仓库有不同的开始点，也就是两个仓库没有共同的commit出现，无法提交，此时我们需要allow-unrelated-histories。也就是我们的 pull 命令改为下面这样的：**

git pull origin master --allow-unrelated-histories