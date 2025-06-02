# MinimalMcpServer

## 專案概述
MinimalMcpServer 是一個基於 .NET  的最小化 Model Context Protocol (MCP) 伺服器範例。此伺服器使用 Microsoft.Extensions.Hosting 和 ModelContextProtocol 套件，提供 MCP 工具的實現。

## 功能
- 提供 MCP 工具類型 `EchoTool` 和 `LeaveRequestTool`。
- 支援標準輸入/輸出 (Stdio) 傳輸。
- 支援工具的自動註冊。

### MCP 工具
#### EchoTool
- **Echo**: 回傳輸入的訊息。
- **Reverse**: 回傳反轉的訊息。

#### LeaveRequestTool
- **GetLeaveRecordAmount**: 查詢員工的請假天數。
- **LeaveRequest**: 提交請假申請，回傳結果。
- **GetCurrentDate**: 取得目前日期。

## 系統需求
- .NET 8+
- Microsoft.Extensions.Hosting 9.0.5
- ModelContextProtocol 0.2.0-preview.2

## 安裝與執行
1. 確保已安裝 .NET 8+ SDK。
2. 使用以下指令執行伺服器：
   ```bash
   dotnet run --project MinimalMcpServer.csproj
   ```

## 程式架構
### `Program.cs`
- 使用 `Host.CreateApplicationBuilder` 建立伺服器。
- 註冊 MCP 工具。
- 設定日誌記錄。

### `MinimalMcpServer.csproj`
- 定義專案的目標框架和套件依賴。

## MCP 工具範例

### LeaveRequestTool 範例
```csharp
GetLeaveRecordAmount("David") // 回傳 5
LeaveRequest(DateTime.Now, "3", "出國玩", "代理人", "David") // 回傳請假結果
GetCurrentDate() // 回傳目前日期
```

## 目錄結構
- `Program.cs`: 伺服器的主要程式碼。
- `MinimalMcpServer.csproj`: 專案檔案。
