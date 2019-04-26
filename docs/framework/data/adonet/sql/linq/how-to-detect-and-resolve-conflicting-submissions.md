---
title: Procedimiento para detectar y resolver envíos con conflictos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 606231449263f1c26596ca8606a88053c6aded8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877284"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>Procedimiento para detectar y resolver envíos con conflictos
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona muchos recursos para detectar y resolver los conflictos que ocasionan los cambios que realizan varios usuarios en la base de datos. Para obtener más información, vea [Cómo: Administrar conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se muestra un `try` / `catch` bloque que detecta un <xref:System.Data.Linq.ChangeConflictException> excepción. La información de entidad y miembro de cada conflicto se muestra en la ventana de la consola.  
  
> [!NOTE]
>  Debe incluir la directiva `using System.Reflection` (`Imports System.Reflection` en Visual Basic) para habilitar la recuperación de la información. Para obtener más información, consulta <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Realización y envío de cambios de datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [Cómo: Administrar conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
