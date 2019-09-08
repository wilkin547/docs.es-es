---
title: Procedimiento para especificar cuándo se inician las excepciones de simultaneidad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: c0f41d23264bbe5c9130cb5a0b03686331bc92b1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781620"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Procedimiento para especificar cuándo se inician las excepciones de simultaneidad
En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando los objetos no se actualizan debido a conflictos de simultaneidad optimista. Para obtener más información, [consulte simultaneidad optimista: Información](optimistic-concurrency-overview.md)general.  
  
 Antes de enviar cambios a la base de datos, puede especificar cuándo se deberían iniciar excepciones de simultaneidad:  
  
- Iniciar la excepción en el primer error (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).  
  
- Finalizar todos los intentos de actualización, acumular todos los errores e informar de todos ellos en la excepción (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).  
  
 Cuando se inicia, la excepción <xref:System.Data.Linq.ChangeConflictException> proporciona acceso a una colección <xref:System.Data.Linq.ChangeConflictCollection>. Esta colección proporciona detalles sobre cada conflicto (asignado a un único intento de actualización con error), incluido el acceso a la colección <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>. Cada conflicto de miembro se asigna a un único miembro en la actualización que no pasó la comprobación de simultaneidad.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra ejemplos de ambos valores.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Cómo: Administrar conflictos de cambios](how-to-manage-change-conflicts.md)
- [Realización y envío de cambios de datos](making-and-submitting-data-changes.md)
