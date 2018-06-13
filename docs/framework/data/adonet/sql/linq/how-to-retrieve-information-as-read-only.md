---
title: 'Cómo: Recuperar información con formato de solo lectura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: dd3a510339bca8649f5654d00a9cbdfba156d92c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360705"
---
# <a name="how-to-retrieve-information-as-read-only"></a>Cómo: Recuperar información con formato de solo lectura
Cuando no se tiene pensado cambiar los datos, puede aumentar el rendimiento de las consultas buscando resultados de solo lectura.  
  
 El procesamiento de solo lectura se implementa estableciendo <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> en `false`.  
  
> [!NOTE]
>  Cuando <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> se establece en `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> se establece implícitamente en `false`.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente recupera una colección de solo lectura de fechas de contratación de empleados.  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [Consulta de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [Carga inmediata y carga diferida](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
