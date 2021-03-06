---
ms.assetid: 330c7b61-dde0-432f-9b74-d250ad9cc808
title: 添加登录页面描述
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.openlocfilehash: 033663720750ee2990cbc6eb4dd0c6d9abe1a002
ms.sourcegitcommit: dfa48f77b751dbc34409aced628eb2f17c912f08
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2020
ms.locfileid: "87962631"
---
# <a name="add-sign-in-page-description"></a>添加登录 \- 页说明

## <a name="to-add-sign-in-page-description"></a>添加登录 \- 页说明
若要将登录 \- 页说明添加到 "登录" \- 页，请使用以下 Windows PowerShell cmdlet 和语法。

![添加登录说明](media/AD-FS-user-sign-in-customization/ADFS_Blue_Custom2.png)

```powershell
Set-AdfsGlobalWebContent -SignInPageDescriptionText "<p>Sign-in to Contoso requires device registration. Click <A href='http://fs1.contoso.com/deviceregistration/'>here</A> for more information.</p>"
```

> [!IMPORTANT]
> `SignInPageDescriptionText` 参数的字符串同时支持带标记和不带标记的纯 HTML。 因此，你还可以运行以下 cmdlet 而无需使用 &lt; p &gt; 标记。  `Set-AdfsGlobalWebContent -SignInPageDescriptionText "Sign-in to Contoso requires device registration. Click <A href='http://fs1.contoso.com/deviceregistration/'>here</A> for more information." `

\-自定义登录页面后，将优先使用自定义; 因此，你应该为你想要支持的所有语言进行自定义。 所有自定义的内容都使用区域设置参数。 在配置本地化内容时，应在配置国家（地区）和区域特定的区域设置（如 "en-us"）之前，先使用国家/地区的 \- 区域设置，例如 "en" \- \- 。

## <a name="additional-references"></a>其他参考

[AD FS 用户登录自定义](AD-FS-user-sign-in-customization.md)
