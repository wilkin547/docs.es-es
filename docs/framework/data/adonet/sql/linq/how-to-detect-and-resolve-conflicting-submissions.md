---
title: Procedimiento para detectar y resolver envíos con conflictos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 2de0182cc0b87768a9cff553b7ec6e77f8ccc7b8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793774"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>Procedimiento para detectar y resolver envíos con conflictos
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona muchos recursos para detectar y resolver los conflictos que ocasionan los cambios que realizan varios usuarios en la base de datos. Para obtener más información, consulte [Cómo Administrar conflictos](how-to-manage-change-conflicts.md)de cambios.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `try` muestra un / `catch` bloque que detecta <xref:System.Data.Linq.ChangeConflictException> una excepción. La información de entidad y miembro de cada conflicto se muestra en la ventana de la consola.  
  
> [!NOTE]
> Debe incluir la directiva `using System.Reflection` (`Imports System.Reflection` en Visual Basic) para habilitar la recuperación de la información. Para obtener más información, consulta <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Realización y envío de cambios de datos](making-and-submitting-data-changes.md)
- [Cómo: Administrar conflictos de cambios](how-to-manage-change-conflicts.md)
