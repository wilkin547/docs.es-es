---
title: "Cómo: Encapsular modelos de EAP en una tarea"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9e451c3ce8bb50cb17da7fef25ae0317bcb82c3e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a>Cómo: Encapsular modelos de EAP en una tarea
En el ejemplo siguiente se muestra cómo exponer una secuencia arbitraria de operaciones de modelo asincrónico basado en eventos (EAP) como una tarea mediante el uso de una clase <xref:System.Threading.Tasks.TaskCompletionSource%601>. En el ejemplo también se muestra cómo usar una clase <xref:System.Threading.CancellationToken> para invocar los métodos de cancelación integrados en los objetos <xref:System.Net.WebClient>.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a>Vea también  
 [TPL y la programación asincrónica tradicional de .NET Framework](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
