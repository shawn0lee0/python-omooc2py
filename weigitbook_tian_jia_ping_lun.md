# 为Gitbook添加评论

参考链接：
[Disqus integration for GitBook](https://plugins.gitbook.com/plugin/disqus)

1. 在[Disqus](https://disqus.com)注册账号
2. 点击头像中[add-disqus to side ](https://publishers.disqus.com/engage?utm_source=Home-Nav) 申请讨论组关键词，复制后
3. 在book.json文件中插入下列脚本
    - ```
    {
    "plugins": ["disqus"],
    "pluginsConfig": {
        "disqus": {
            "shortName": "XXXXXXX"
        }
    }  
}```
注意括号配对

4. 使用2中复制的关键词替换代码中的XXXXXXX
5. 保存





