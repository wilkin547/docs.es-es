---
title: Procedimiento para detectar y resolver envíos con conflictos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 96e96208d9bb28092701164e6cd5943ef81515a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147728"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>Procedimiento para detectar y resolver envíos con conflictos

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona muchos recursos para detectar y resolver los conflictos que ocasionan los cambios que realizan varios usuarios en la base de datos. Para obtener más información, vea [Cómo: administrar conflictos de cambios](how-to-manage-change-conflicts.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra un `try` / `catch` bloque que detecta una <xref:System.Data.Linq.ChangeConflictException> excepción. La información de entidad y miembro de cada conflicto se muestra en la ventana de la consola.  
  
> [!NOTE]
> Debe incluir la directiva `using System.Reflection` (`Imports System.Reflection` en Visual Basic) para habilitar la recuperación de la información. Para obtener más información, vea <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Realizar y enviar cambios de datos](making-and-submitting-data-changes.md)
- [Procedimiento para administrar conflictos de cambios](how-to-manage-change-conflicts.md)
