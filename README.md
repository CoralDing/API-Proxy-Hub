# API Proxy Hub

API Proxy Hub 是一个简单而高效的 API 代理服务，支持 HTTP 和 HTTPS 请求转发，帮助开发者克服跨域限制并简化 API 调用流程。

## 特性

- 支持 HTTP 和 HTTPS 请求代理
- 简单易用的 URL 结构
- 部署在 Vercel 平台，享受全球边缘网络的低延迟
- 针对亚太地区优化（使用 hnd1 区域）

## 使用方法

API Proxy Hub 提供了两种代理路径：

### HTTPS 代理

```
https://your-domain/https-proxy/api.example.com/v1/path
```

### HTTP 代理

```
https://your-domain/http-proxy/example.com/path
```

只需将目标 API 的主机名和路径（不含协议部分）附加到相应的代理路径后即可使用。

## 代码示例

### JavaScript/Fetch API

```javascript
fetch('https://your-domain/https-proxy/api.example.com/v1/endpoint', {
    method: 'POST',
    headers: {
        'Authorization': 'Bearer YOUR_API_KEY',
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        // 你的请求参数
    })
})
.then(res => res.json())
.then(data => console.log(data));
```

### curl 示例

```bash
curl -X GET "https://your-domain/https-proxy/api.example.com/v1/endpoint" \
  -H "Authorization: Bearer YOUR_API_KEY"
```

## 部署指南

1. 克隆此仓库
2. 使用 Vercel CLI 或 Vercel 仪表板部署
3. 默认配置使用东京区域 (hnd1)，可以根据需要在 `vercel.json` 中修改

```bash
vercel deploy
```

## 项目结构

- `index.html` - 项目主页和使用说明
- `vercel.json` - Vercel 配置文件，包含路由规则和区域设置

## 注意事项

- 此服务仅用于开发和测试环境
- 对于生产环境，建议设置适当的安全措施和访问控制
- 遵循目标 API 的使用条款和限制

## 许可证

© 2025 API Proxy Hub - Powered by Coralding

---

将上述文档中的 `your-domain` 替换为你实际部署的域名。
