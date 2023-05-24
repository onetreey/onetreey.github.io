# 小知识点点


PPT上所有内容都要涉及到(具体而言，是表格上的数据)，方案建模要先有一个总体的建模，不只是探测噪声。

原位测量，即在 MOT 区让原子自由落体(先上抛再自由落体，会多一个囚禁光带来的噪声，需要评估)。

首先需要 'hugo' 建立站点
然后 'hugo server' 查看本地博客，作为一个预览。

   '''base
   hugo
   hugo server
   '''
之后需要将本地博客推到远端库，具体而言：
   
   '''base
   git init        #重置 '.git' 库
   git add .       #添加文件
   git commit -m  "说明文字"        #提交
   git status                      #查看状态
   git push -u origin master       #推到远端库
   '''

具体有其他问题建议直接复制报错百度。

另外，全局设置需要注意：

    '''base
    git config -global user.name ""
    git config -global user.email ""
    '''
    


