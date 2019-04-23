---
ms.assetid: c28a1b8b-5bec-4eed-8c95-a1a29cfc957c
title: 安装 AD FS 角色服务
description: ''
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server-threshold
ms.technology: identity-adfs
ms.openlocfilehash: 9851134d1ad73092ee44c34c99bc2d873d20ca07
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2019
ms.locfileid: "59831168"
---
# <a name="install-the-ad-fs-role-service"></a>安装 AD FS 角色服务

>适用于：Windows Server 2016, Windows Server 2012 R2

可以使用以下过程在现有的联合服务器场中运行 Windows Server 2012 R2，若要成为联合服务器场中的第一个联合服务器或联合身份验证服务器的计算机上安装 AD FS 角色服务。  
  
中的成员身份**管理员**，或在本地计算机上等效身份是完成此过程的最低要求。  可在[本地默认组和域默认组](https://go.microsoft.com/fwlink/?LinkId=83477)中查看有关使用适合的帐户和组成员身份的详细信息。   
  
### <a name="to-install-the-ad-fs-server-role-via-the-add-roles-and-features-wizard"></a>若要安装 AD FS 服务器角色通过添加角色和功能向导  
  
1.  打开服务器管理器。 若要打开服务器管理器，请单击**服务器管理器**上**启动**屏幕中，或**服务器管理器**桌面上的任务栏中。 在“仪表板”页面上的“欢迎”磁贴的“快速启动”选项卡中，单击“添加角色和功能”。 或者，也可以在“管理”菜单中单击“添加角色和功能”。  
  
2.  在“开始之前”  页上，单击“下一步” 。  
  
3.  上**选择安装类型**页上，单击**角色\-基于或功能\-基于安装**，然后单击**下一步**。  
  
4.  在“选择目标服务器”页面上，单击“从服务器池中选择一个服务器”，验证目标计算机是否已选中，然后单击“下一步”。  
  
5.  在“选择服务器角色”  页面上，单击“Active Directory 联合身份验证服务” ，然后单击“下一步” 。  
  
6.  在“选择功能”页上，单击“下一步”。 所需的先决条件是为你预先选择。 无需选择任何其他功能。  
  
7.  上**Active Directory 联合身份验证服务\(AD FS\)** 页上，单击**下一步**。  
  
8.  在验证信息后**确认安装选择**页上，单击**安装**。  
  
9. 在“安装进度”页面上，验证所有内容是否正确安装，然后单击“关闭”。  
  
### <a name="to-install-the-ad-fs-server-role-via-windows-powershell"></a>若要安装通过 Windows PowerShell 的 AD FS 服务器角色  
  
1.  在你想要将配置为联合身份验证服务器的计算机，打开 Windows PowerShell 命令窗口，然后运行以下命令： `Install-windowsfeature adfs-federation –IncludeManagementTools`。  
  
## <a name="see-also"></a>请参阅 

[AD FS 部署](../../ad-fs/AD-FS-Deployment.md)  

[Windows Server 2012 R2 AD FS 部署指南](../../ad-fs/deployment/Windows-Server-2012-R2-AD-FS-Deployment-Guide.md)  
 
[部署联合服务器场](../../ad-fs/deployment/Deploying-a-Federation-Server-Farm.md)  
  
