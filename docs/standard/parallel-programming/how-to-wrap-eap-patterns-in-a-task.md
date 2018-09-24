---
title: 'Cómo: Encapsular modelos de EAP en una tarea'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4287879bd95f7bc1e1dc99f74fa0d7cc0fe737f
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004265"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a>Cómo: Encapsular modelos de EAP en una tarea
En el ejemplo siguiente se muestra cómo exponer una secuencia arbitraria de operaciones de modelo asincrónico basado en eventos (EAP) como una tarea mediante el uso de una clase <xref:System.Threading.Tasks.TaskCompletionSource%601>. En el ejemplo también se muestra cómo usar una clase <xref:System.Threading.CancellationToken> para invocar los métodos de cancelación integrados en los objetos <xref:System.Net.WebClient>.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a>Vea también

- [TPL y la programación asincrónica tradicional de .NET Framework](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
