# AD Admin Desk

[简体中文](#简体中文) | [English](#english)

AD Admin Desk 是面向本地 Active Directory 的 Windows 桌面管理工具，使用 WPF 构建，目标框架为 .NET Framework 4.7.2。管理员使用现有 AD 账号登录，实际操作范围由目录权限决定。

## 简体中文

### 功能

- **用户管理：**搜索用户，按组织单位（OU）和锁定状态筛选；新增、编辑、删除用户；启用、禁用或解锁账号。
- **密码与账号：**重置密码，设置账号到期时间，要求用户下次登录时修改密码。
- **用户组管理：**搜索、新增、编辑、删除用户组；维护组的直接用户或组成员。
- **批量操作：**逐项显示操作结果；失败或结果未确认的写操作不会自动重试。
- **域控连接：**已加域的 Windows 电脑会尝试发现域控；自动发现不可用时可手动填写域服务器地址。

组成员界面显示直接成员，不递归展开嵌套组成员。本工具管理本地 Active Directory，不管理 Microsoft Entra ID。

### 运行与权限

需要 Windows 桌面环境、.NET Framework 4.7.2 或兼容的较新版本，并能访问目标 AD 域控制器。只读查询不要求 Domain Admin 身份；新增、修改、删除、重置密码和组成员变更需要相应的 AD 委派权限。以 Windows 管理员身份运行不会增加 AD 权限。

### 本地数据与更新

记住密码为可选项，默认关闭；保存的密码由当前 Windows 用户的 DPAPI 保护。操作日志记录操作者、目标和结果，不记录密码，但不是防篡改审计记录。

程序启动后检查更新，此后每 5 分钟检查一次，请求超时为 10 秒。自动检查失败时保持静默；发现新版本后显示本地化说明，并在用户确认后打开 Release 页面。程序不会自动下载、安装、覆盖或重启。

### 下载与许可

当前稳定版：**v1.0.0**

- [下载 Windows ZIP](https://github.com/qishouvip/ADAdminDesk-Releases/releases/latest)
- 下载后核对 ZIP 附带的 SHA-256 校验文件。
- 软件使用条款及第三方许可声明随 ZIP 提供。软件采用专有许可；源码仓库为私有仓库：[qishouvip/ADAdminDesk](https://github.com/qishouvip/ADAdminDesk)。

## English

AD Admin Desk is a Windows desktop tool for managing users and groups in on-premises Active Directory. It is built with WPF and targets .NET Framework 4.7.2. Operators sign in with an existing AD account; directory permissions govern each operation.

### Features

- **User management:** Search users and filter by organizational unit (OU) or lock state; create, edit, and delete users; enable, disable, or unlock accounts.
- **Passwords and accounts:** Reset passwords, set account expiration, and require a password change at next sign-in.
- **Group management:** Search, create, edit, and delete groups; manage direct user or group membership.
- **Batch operations:** Show each operation result; failed or unconfirmed writes are not retried automatically.
- **Domain controller connection:** Domain-joined Windows computers attempt to discover a domain controller; enter a server address manually if discovery is unavailable.

Group membership views list direct members and do not recursively expand nested groups. The tool manages on-premises Active Directory and does not manage Microsoft Entra ID.

### Requirements and permissions

Requires a Windows desktop environment, .NET Framework 4.7.2 or a compatible later version, and access to the target domain controller. Read-only queries do not require Domain Admin membership. Create, edit, delete, password reset, and group-membership operations require the corresponding delegated AD permissions. Running as a Windows administrator does not grant AD permissions.

### Local data and updates

Remember Password is optional and off by default; saved passwords are protected with DPAPI for the current Windows user. Operation logs record the operator, target, and outcome, but not passwords. They are not tamper-proof audit records.

The application checks for updates at startup and every five minutes, with a 10-second request timeout. Automatic check failures are silent. When an update is available, it shows localized notes and opens the Release page after user confirmation. It does not automatically download, install, overwrite, or restart the application.

### Download and license

Current stable release: **v1.0.0**

- [Download the Windows ZIP](https://github.com/qishouvip/ADAdminDesk-Releases/releases/latest)
- Verify the ZIP against its accompanying SHA-256 file.
- Software terms and third-party notices are included in the ZIP. The application uses a proprietary license; the source repository is private: [qishouvip/ADAdminDesk](https://github.com/qishouvip/ADAdminDesk).
