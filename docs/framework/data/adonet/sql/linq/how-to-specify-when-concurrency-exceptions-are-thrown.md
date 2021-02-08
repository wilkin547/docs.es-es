---
description: 'Más información acerca de cómo: especificar Cuándo se inician las excepciones de simultaneidad'
title: Procedimiento para especificar cuándo se inician las excepciones de simultaneidad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: d445cabfd2498f3599d874c2b7983a86c2c36c7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785879"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Procedimiento para especificar cuándo se inician las excepciones de simultaneidad

En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando los objetos no se actualizan debido a conflictos de simultaneidad optimista. Para obtener más información, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).  
  
 Antes de enviar cambios a la base de datos, puede especificar cuándo se deberían iniciar excepciones de simultaneidad:  
  
- Iniciar la excepción en el primer error (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).  
  
- Finalizar todos los intentos de actualización, acumular todos los errores e informar de todos ellos en la excepción (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).  
  
 Cuando se inicia, la excepción <xref:System.Data.Linq.ChangeConflictException> proporciona acceso a una colección <xref:System.Data.Linq.ChangeConflictCollection>. Esta colección proporciona detalles sobre cada conflicto (asignado a un único intento de actualización con error), incluido el acceso a la colección <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>. Cada conflicto de miembro se asigna a un único miembro en la actualización que no pasó la comprobación de simultaneidad.  
  
## <a name="example"></a>Ejemplo  

 El código siguiente muestra ejemplos de ambos valores.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para administrar conflictos de cambios](how-to-manage-change-conflicts.md)
- [Realizar y enviar cambios de datos](making-and-submitting-data-changes.md)
