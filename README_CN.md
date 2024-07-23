# vertexai-cf-workers

## 前提条件
1. 注册GCP账户：
   - 访问[https://cloud.google.com/vertex-ai](https://cloud.google.com/vertex-ai)并注册GCP账户。
   - 你可以获得150美元的免费额度（无需信用卡），或者提供信用卡获得300美元的免费额度。（请注意，免费额度在90天内到期）

2. 启用Vertex AI API：
   - 访问[https://console.cloud.google.com/marketplace/product/google/aiplatform.googleapis.com](https://console.cloud.google.com/marketplace/product/google/aiplatform.googleapis.com)为你的项目启用Vertex AI API。
   
3. 申请Claude模型：
   - 访问[https://console.cloud.google.com/vertex-ai](https://console.cloud.google.com/vertex-ai)并申请访问Claude模型。

4. 创建[服务账户](https://console.cloud.google.com/projectselector/iam-admin/serviceaccounts/create?walkthrough_id=iam--create-service-account#step_index=1)：
   - 选择你之前创建的项目ID。
   - 确保为服务账户授予"Vertex AI用户"或"Vertex AI管理员"的角色。
   - 在你刚创建的服务账户页面，转到"密钥"标签，点击"添加密钥"。
   - 选择"创建新密钥"并选择"JSON"作为密钥类型。
   - 密钥文件将自动下载。该文件包含worker所需的变量，如project_id、private_key和client_email。
   
## Workers变量

worker需要设置几个环境变量：

- `CLIENT_EMAIL`：这是与你的GCP服务账户关联的电子邮件。你可以在服务账户的JSON密钥文件中找到它。
- `PRIVATE_KEY`：这是与你的GCP服务账户关联的私钥。你可以在服务账户的JSON密钥文件中找到它。
- `PROJECT`：这是你的GCP项目的ID。你可以在服务账户的JSON密钥文件中找到它。
- `API_KEY`：这是你定义的字符串。它用于验证对worker的请求。
