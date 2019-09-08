---
title: Procedimiento para recuperar información con formato de solo lectura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 399bf44ef5536a9adebf1cad590439741df998f0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793317"
---
# <a name="how-to-retrieve-information-as-read-only"></a>Procedimiento para recuperar información con formato de solo lectura
Cuando no se tiene pensado cambiar los datos, puede aumentar el rendimiento de las consultas buscando resultados de solo lectura.  
  
 El procesamiento de solo lectura se implementa estableciendo <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> en `false`.  
  
> [!NOTE]
> Cuando <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> se establece en `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> se establece implícitamente en `false`.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente recupera una colección de solo lectura de fechas de contratación de empleados.  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos sobre consultas](query-concepts.md)
- [Consulta de la base de datos](querying-the-database.md)
- [Carga inmediata y carga diferida](deferred-versus-immediate-loading.md)
