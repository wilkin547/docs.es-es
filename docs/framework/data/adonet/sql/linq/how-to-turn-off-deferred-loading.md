---
title: Procedimiento para desactivar la carga diferida
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: b2193e7e8bda396451274d2da96e7cb86774fd03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196967"
---
# <a name="how-to-turn-off-deferred-loading"></a>Procedimiento para desactivar la carga diferida

Puede desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`. Para obtener más información, vea [carga aplazada frente a carga inmediata](deferred-versus-immediate-loading.md).  
  
> [!NOTE]
> La carga aplazada se desactiva al desactivar el seguimiento de los objetos. Para obtener más información, vea [Cómo: recuperar información como de solo lectura](how-to-retrieve-information-as-read-only.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Consulte también

- [Conceptos sobre consultas](query-concepts.md)
- [Consultar la base de datos](querying-the-database.md)
