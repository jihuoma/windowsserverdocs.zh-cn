---
ms.assetid: 65e474b5-3076-4ba3-809d-a09160f7c2bd
title: 声明规则的角色
description: ''
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server-threshold
ms.technology: identity-adfs
ms.openlocfilehash: e47dbecdeee620d3a237ad8d8c41a550d3ef069c
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2019
ms.locfileid: "59860778"
---
>适用于：Windows Server 2016 中，Windows Server 2012 R2、 Windows Server 2012

# <a name="the-role-of-claim-rules"></a>声明规则的角色
Active Directory 联合身份验证服务中的联合身份验证服务的总体功能\(AD FS\)是颁发令牌，其中包含一组声明。 AD FS 接受，然后发出哪些声明，相关决定是由声明规则控制。  
  
## <a name="what-are-claim-rules"></a>什么是声明规则？  
声明规则表示业务逻辑，需要一个或多个传入声明、 向其应用条件的实例\(if x，then y\)并生成一个或多个基于条件参数的传出声明。 有关传入和传出声明的详细信息，请参阅[The Role of Claims](The-Role-of-Claims.md)。  
  
当需要实现的业务逻辑会通过声明管道控制声明流时，可以使用声明规则。 虽然声明管道在更多的逻辑概念结束\-到\-结束使声明流过的进程、 声明规则是可用于自定义通过声明颁发过程的声明流的实际管理元素。  
  
有关声明管道的详细信息，请参阅[The Role of the Claims Engine](The-Role-of-the-Claims-Engine.md)。  
  
声明规则提供了以下好处：  
  
-   提供一种机制，管理员可以应用运行\-时业务逻辑来信任来自声明提供程序的声明  
  
-   为管理员提供了一种机制，用于定义向信赖方发布的声明  
  
-   提供丰富且详细声明\-基于管理员想要允许或拒绝对特定用户访问的授权功能  
  
### <a name="how-claim-rules-are-processed"></a>处理声明规则的方式  
声明规则使用“声明引擎”通过声明管道进行处理。 声明引擎是联合身份验证服务的一个逻辑组件，它检查用户提供的传入声明集，然后根据每个规则中的逻辑生成输出声明集。  
  
声明规则引擎与给定联合信任相关联的声明规则集结合在一起可确定是传入声明在由联合身份验证服务作为传出声明发出之前，是应按原样传递、进行筛选以满足特定条件的标准还是转换为全新的声明集。  
  
有关此过程的详细信息，请参阅[The Role of the Claims Engine](The-Role-of-the-Claims-Engine.md)。  
  
## <a name="what-are-claim-rule-templates"></a>什么是声明规则模板？  
AD FS 包含一组预定义的声明规则模板，旨在帮助您轻松地选择并创建你的特定业务需求的最合适声明规则。 声明规则模板仅在声明规则创建过程中使用。  
  
在 AD FS 管理管理单元\-中，规则可以仅使用创建声明规则模板。 使用管理单元后\-中选择声明规则模板，输入规则逻辑的所需的数据，并将其保存到配置数据库，它将是\(从该时间点\)UI 作为声明规则中引用。  
  
### <a name="how-claim-rule-templates-work"></a>声明规则模板的工作原理  
第一次看到声明规则模板似乎只需输入窗体提供的管理单元\-以对传入声明收集数据和处理特定逻辑。 但是，在详细得多的级别，声明规则模板存储所需的声明规则语言框架，组成使你可以快速创建规则（无需熟悉语言）所需的基本逻辑。  
  
每个用户界面中提供的模板\(UI\)表示预填充的声明规则语言语法，基于最常需要的管理任务。 但是有一个规则模板例外。 此模板称为自定义规则模板。 对于此模板，没有预填充任何语法。 而是必须使用声明规则语言语法，在声明规则模板表单的正文中直接创作声明规则语言语法。  
  
有关如何使用声明规则语言语法的详细信息，请参阅[的声明规则语言角色](The-Role-of-the-Claim-Rule-Language.md)AD FS 部署指南中。  
  
> [!TIP]  
> 可以通过在声明规则的属性上单击“查看规则语言”按钮，随时查看与规则关联的声明规则语言。  
  
### <a name="how-to-create-a-claim-rule"></a>如何创建声明规则  
声明规则对于联合身份验证服务中的每个联合信任关系单独进行创建，不在多个信任间共享。 可以从声明规则模板创建规则、通过使用声明规则语言创建规则来从头开始或是使用 Windows PowerShell 自定义规则。  
  
所有这些选项共存，使你可以灵活地选择适合于给定方案的方法。 有关如何创建声明规则的详细信息，请参阅[配置声明规则](https://technet.microsoft.com/library/ee913571.aspx)AD FSDeployment 指南中。  
  
#### <a name="using-claim-rule-templates"></a>使用声明规则模板  
声明规则模板仅在声明规则创建过程中使用。 可以使用以下任何模板来创建声明规则：  
  
-   通过或筛选传入声明  
  
-   转换传入声明  
  
-   以声明方式发送 LDAP 属性  
  
-   以声明方式发送组成员身份  
  
-   使用自定义规则发送声明  
  
-   根据传入声明允许或拒绝用户  
  
-   允许所有用户  
  
有关详细信息描述其中每个声明规则模板，请参阅[确定类型的声明规则模板使用](Determine-the-Type-of-Claim-Rule-Template-to-Use.md)。  
  
#### <a name="using-the-claim-rule-language"></a>使用声明规则语言  
对于超出标准声明规则模板范围的业务规则，可以使用自定义规则模板表示一系列复杂的逻辑条件（使用声明规则语言）。 有关使用自定义规则的详细信息，请参阅[何时使用自定义声明规则](When-to-Use-a-Custom-Claim-Rule.md)。  
  
#### <a name="using-windowspowershell"></a>使用 Windows PowerShell  
您可以使用 Windows PowerShell 使用 ADFSClaimRuleSet cmdlet 对象来创建或管理 AD FS 中的规则。 有关如何将 Windows PowerShell 与此 cmdlet 结合使用的详细信息，请参阅[借助 Windows PowerShell 的 AD FS 管理](https://go.microsoft.com/fwlink/?LinkID=179634)。  
  
## <a name="what-is-a-claim-rule-set"></a>什么是声明规则集？  
如下图所示，声明规则集是用于给定联合信任的一个或多个规则的分组，会定义声明规则引擎处理声明的方式。 当联合身份验证服务收到传入声明时，声明规则引擎会应用由适当声明规则集指定的逻辑。 由集中每个规则的逻辑的最终总和来确定如何从整体上为给定信任发出声明。  
  
![AD FS 角色](media/adfs2_claimruleset.gif)  
  
声明规则由声明引擎按给定规则集内的时间顺序处理。 此顺序非常重要，因为一个规则的输出可能会用作集中下一个规则的输入。  
  
## <a name="what-are-claim-rule-set-types"></a>什么是声明规则集类型？  
声明规则集类型是联合信任的一个逻辑段，可明确标识与信任关联的声明规则集是用于声明发出、授权还是接受。 每个联合信任都可以具有相关联的一种或多种声明规则集类型（具体取决于所使用的信任类型）。  
  
下表介绍各种类型的声明规则集并说明其与声明提供方信任或信赖方信任的关系。  
  
|声明规则集类型|描述|用于|  
|-----------------------|---------------|-----------|  
|接受转换规则集|对特定声明提供方信任使用的声明规则集，用于指定从声明提供方组织接受的传入声明和发送到信赖方信任的传出声明。<br /><br />用作此规则集来源的传入声明会是由声明提供方组织中指定的发出转换规则集输出的声明。<br /><br />默认情况下，声明提供方信任节点包含名为“Active Directory”的声明提供方信任，它用于表示接受转换规则集的源属性存储。 此信任对象用于表示从联合身份验证服务到网络上的 Active Directory 数据库的连接。 此默认信任是为由 Active Directory 进行了身份验证的用户处理声明的对象，无法删除。|声明提供方信任|  
|发出转换规则|对信赖方信任使用的声明规则集，用于指定向信赖方发出的声明。<br /><br />用作此规则集来源的传入声明最初会是由接受转换规则集输出的声明。|信赖方信任|  
|发出授权规则集|对信赖方信任使用的声明规则集，用于指定允许接收信赖方的令牌的用户。<br /><br />这些规则确定用户是否可以接收有关信赖方的声明，从而访问该信赖方。<br /><br />除非指定发出授权规则，否则默认情况下会拒绝所有用户访问。|信赖方信任|  
|委派授权规则集|对信赖方信任使用的声明规则集，用于指定允许充当其他用户对信赖方的代理人的用户。<br /><br />这些规则可确定是否允许请求者模拟用户，同时仍在发送到信赖方的令牌中标识请求者。<br /><br />除非指定发出授权规则，否则默认情况下没有用户可以当代理人。|信赖方信任|  
|模拟授权规则集|可以使用 Windows PowerShell 配置的声明规则集，用于确定用户是否可以向依赖方完全模拟其他用户。<br /><br />这些规则可确定是否允许请求者模拟用户，而不在发送到信赖方的令牌中标识请求者。<br /><br />采用这种方式模拟另一位用户是一项非常强大的功能，因为信赖方不知道被模拟的用户。|信赖方信任|  
  
若要在组织中使用的合适声明规则选择有关详细信息请参阅[确定类型的声明规则模板使用](Determine-the-Type-of-Claim-Rule-Template-to-Use.md)。  
  
