---
title: nslookup set search
description: "\"Nslookup 集搜索\" 命令的参考文章，该命令会在 DNS 域搜索列表中追加域名系统 (DNS) 域名发送给请求，直到收到答案。"
ms.topic: reference
ms.assetid: 064ac660-8b04-4af9-8b2c-e4e0549771b8
ms.author: lizross
author: eross-msft
manager: mtillman
ms.date: 10/16/2017
ms.openlocfilehash: 91efbb50ab54a920be4c2942db1ea8b9cea71fbe
ms.sourcegitcommit: db2d46842c68813d043738d6523f13d8454fc972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "89637454"
---
# <a name="nslookup-set-search"></a>nslookup set search

将 DNS 域搜索列表中的域名系统 (DNS) 域名追加到请求，直到收到答案。 这适用于以下情况：集和查找请求至少包含一个句点，但不以尾随句点结束。

## <a name="syntax"></a>语法

```
set [no]search
```

### <a name="parameters"></a>参数

| 参数 | 说明 |
| --------- | ----------- |
| nosearch | 停止在请求的 DNS 域搜索列表中追加域名系统 (DNS) 域名。 |
| 搜索 | 将域名系统追加到请求的 DNS 域搜索列表中的域名系统 (DNS) 域名，直到接收到答案。 这是默认值。 |
| /? | 在命令提示符下显示帮助。 |
| /help | 在命令提示符下显示帮助。 |

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)
