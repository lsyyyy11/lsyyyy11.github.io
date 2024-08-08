# 利用 G-Core 免费 CDN 服务对网站进行加速

大家都知道[赛博活佛CF](https://cloudflare.com)提供的免费CDN加速，在国外，G-Core也是比较出名的。
G-Core的CDN中Free计划包含180+位置的数据中心，L3，L4的DDos保护，1TB流量，1M的请求。
一共是3种计费方案。建议用Free一般就足够了。

![https://lsyyyy-imagebed.pages.dev/file/3ffd394059bf005aac333.png](https://lsyyyy-imagebed.pages.dev/file/3ffd394059bf005aac333.png)

# 创建账号
<https://auth.gcore.com/login/signup?lang=zh&default_product=CDN>
跟着提示创建就可以了。有中文。可以用国内的部分邮箱。
建议选择USD，按照目前的(2024/08/07更新汇率)汇率来说，USD便宜一点。
查看汇率：<https://wise.com/zh-cn/currency-converter/usd-to-eur-rate>

# 创建存储桶

### 选择方案
### 配置
![图片_设置_2_配置](https://lsyyyy-imagebed.pages.dev/file/b1f60ed34952cab190822.png)

这里我设置的是我在Cloudflare Pages上的Telegraph图床，一定要注意CDN用量，防止刷量！！
想做慈善的可以用CDN加速Github `raw.githubusercontent.com`

![图片_设置_3_DNS](https://lsyyyy-imagebed.pages.dev/file/d70b7c4615fa97f053f86.png)
![](https://lsyyyy-imagebed.pages.dev/file/f36736b8752f31d6d1e49.png)
### 修改DNS
设置DNS就不说了，上注册域名的地方加CNAME记录。有的根域名不能识别正确，需要注意一下。
举个例子，像.cloudns.ch这样cloudns提供的公共域，不能把.example加进去。
特别注意，不要再开Cloudflare的代理了，双层CDN那白开了，

### CMS
**有**CMS:
官方说明：<https://gcore.com/docs/cdn/getting-started/integrate-cdn-with-cms/integrate-cdn-resource-with-aws-s3>
**没有**CMS:
`<img src="http://example.com/path-to-image/image.jpg" alt="image" />`
改为
`<img src="http://cdn.example.com.cdn.yourdomain.org/path-to-image/image.jpg" alt="image" />;`
就可以了。

# 总结
其实G-Core没有太大优势，只可以作为一个替代品。主要肯定使用cf，不限量而且数据中心更多。