---
title: 创建自动分类规则
description: 本文介绍如何针对属性创建分类规则。
ms.date: 7/7/2017
ms.topic: article
author: JasonGerend
manager: brianlic
ms.author: jgerend
ms.openlocfilehash: 3793e8cd7f72e9e8d365df855c8c3450d9107f9b
ms.sourcegitcommit: dfa48f77b751dbc34409aced628eb2f17c912f08
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2020
ms.locfileid: "87961471"
---
# <a name="create-an-automatic-classification-rule"></a>创建自动分类规则

> 适用于：Windows Server（半年频道）、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2

以下步骤将引导你完成创建分类规则的过程。 每个规则均对单个属性设置值。 默认情况下，规则仅运行一次，并且会忽略已分配属性值的文件。 但是，无论是否为属性分配值，都可以配置用于评估文件的规则。

## <a name="to-create-a-classification-rule"></a>若要创建分类规则，请执行以下操作：

1.  在“分类管理”**** 中，单击“分类规则”**** 节点。

2.  右键单击**分类规则**，然后单击**新建规则**（或单击**操作**窗格中的**新建规则**）。 此操作将打开**分类规则定义**对话框。

3.  在**规则设置**选项卡上输入以下信息：

    -   “规则名称”****。 键入规则的名称。
    -   “启用”。 只有选中“已启用”复选框，才能应用该规则。 若要禁用规则，请清除该框。
    -   **说明**。 键入该规则的可选说明。
    -   **范围**。 单击**添加**选择将应用此规则的位置。 你可以添加多个位置，或单击**删除**以删除某个位置。 分类规则适用于此列表中所有文件夹及其子文件夹。

4.  在“分类”**** 选项卡上，输入以下信息：

    -   **分类机制**。 选择一种属性值分配方法。
    -   **属性名称**。 选择此规则将分配的属性。
    -   **属性值**。 选择此规则将分配的属性值。

5.  或者，可单击**高级**按钮以选择其他选项。 默认情况下，**评估类型**选项卡上的**重新评估文件**复选框未选中。 下列选项可供选择：

    -   取消选中**重新评估文件**：当且仅当未将规则所规定的属性设置为任何文件相关的值时，规则才能够应用于该文件。
    -   选中**重新评估文件**并选择**覆盖现有值**选项：每次运行自动分类进程时，该规则都将应用于文件。 例如，如果某个文件中的布尔属性设置为**是**，则使用文件夹分类器通过此选项集将所有文件设置为**否**的规则将会使该属性设置为**否**。
    -   选中**重新评估文件**并选择**聚合值**选项：每次运行自动分类进程时，该规则都将应用于文件。 但是，如果该规则已确定为属性文件设置的值，则该规则会将该值与文件中已有的值聚合。 例如，如果某个文件中的布尔属性设置为**是**，则使用文件夹分类器通过此选项集将所有文件设置为**否**的规则将会使该属性设置为**是**。

    可在**其他分类参数**选项卡上指定由所选分类方式识别的其他参数，方法为输入名称和值，然后单击**插入**按钮。

6.  单击**确定**或**取消**关闭**高级**对话框。

7.  单击“确定”。

## <a name="additional-references"></a>其他参考

-   [创建分类属性](create-classification-property.md)
-   [分类管理](classification-management.md)