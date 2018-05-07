---
title: 'Cómo: Especificar cuándo se inician las excepciones de simultaneidad'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 6890cc130f4f4101c02bb88c5f5666bcd5cf9b98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Cómo: Especificar cuándo se inician las excepciones de simultaneidad
En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando los objetos no se actualizan debido a conflictos de simultaneidad optimista. Para obtener más información, consulte [simultaneidad optimista: información general sobre](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
 Antes de enviar cambios a la base de datos, puede especificar cuándo se deberían iniciar excepciones de simultaneidad:  
  
-   Iniciar la excepción en el primer error (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).  
  
-   Finalizar todos los intentos de actualización, acumular todos los errores e informar de todos ellos en la excepción (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).  
  
 Cuando se inicia, la excepción <xref:System.Data.Linq.ChangeConflictException> proporciona acceso a una colección <xref:System.Data.Linq.ChangeConflictCollection>. Esta colección proporciona detalles sobre cada conflicto (asignado a un único intento de actualización con error), incluido el acceso a la colección <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>. Cada conflicto de miembro se asigna a un único miembro en la actualización que no pasó la comprobación de simultaneidad.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra ejemplos de ambos valores.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Administración de conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Realización y envío de cambios de datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
