# Gitlen

# 一级标题  
## 二级标题  
### 三级标题  
#### 四级标题  
##### 五级标题  
###### 六级标题 
二、编辑基本语法  
1、字体格式强调
 我们可以使用下面的方式给我们的文本添加强调的效果
*强调*  (示例：斜体)  
 _强调_  (示例：斜体)  
**加重强调**  (示例：粗体)  
 __加重强调__ (示例：粗体)  
***特别强调*** (示例：粗斜体)  
___特别强调___  (示例：粗斜体)  
2、代码  
`<hello world>`  
3、代码块高亮  
```
@Override
protected void onDestroy() {
    EventBus.getDefault().unregister(this);
    super.onDestroy();
}
```  
4、表格 （建议在表格前空一行，否则可能影响表格无法显示）
 
 表头  | 表头  | 表头
 ---- | ----- | ------  
 单元格内容  | 单元格内容 | 单元格内容 
 单元格内容  | 单元格内容 | 单元格内容  
 
5、其他引用图片  
![图片名称](https://www.baidu.com/img/bd_logo1.png)  
链接  
[链接名称](https://www.baidu.com/)    
6、列表 
1. 项目1  
2. 项目2  
3. 项目3  
   * 项目1 （一个*号会显示为一个黑点，注意⚠️有空格，否则直接显示为*项目1） 
   * 项目2   
 
7、换行（建议直接在前一行后面补两个空格）
直接回车不能换行，  
可以在上一行文本后面补两个空格，  
这样下一行的文本就换行了。
或者就是在两行文本直接加一个空行。
也能实现换行效果，不过这个行间距有点大。  
 
8、引用
> 第一行引用文字  
> 第二行引用文字   

### 新建tag

git tag -a v3.0 -m "这是4.0版本"
git push origin v3.0
//git tag -a 标签名称 -m "说明"
//git push origin 标签名称

### 删除tag
  git tag -d v1.1  //删除本地tag
  git push origin :v1.1//删除远程tag
  //也可以这样  
  git push origin --delete tag V1.1 
  
  添加远程仓库，这个远程仓库是要进行发起合并请求的仓库，简单来说就是项目的主要代码库，不是自己派生的代码库
git remote add main https://xxx.git

从远端仓库下载新分支与数据
git fetch main
创建新分支，以主仓库的master作为参照
git checkout -b release main/master
创建自己派生库的新分支release，作为纯净分支
git push origin release
非提交性合并
git merge --squash origin master
回滚一些不是自己修改的文件
git reset xxx xxx
忽视文件
git checkout .
提交自己所有改过的文件
git commit -m ""
push到自己派生库的release
git push origin release
然后请求合并
