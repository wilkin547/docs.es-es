---
description: 'Más información acerca de cómo: recuperar información como Read-Only'
title: Procedimiento para recuperar información con formato de solo lectura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 7743e555bcc3f6371ca601d02313e30895e57961
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723457"
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
- [Consultar la base de datos](querying-the-database.md)
- [Carga inmediata y carga diferida](deferred-versus-immediate-loading.md)
