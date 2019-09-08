---
title: Procedimiento para recuperar información de conflictos de miembros
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 40caa07488cb40ca8e9e3eb3a570c325b92de491
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793309"
---
# <a name="how-to-retrieve-member-conflict-information"></a>Procedimiento para recuperar información de conflictos de miembros
Puede utilizar la clase <xref:System.Data.Linq.MemberChangeConflict> para recuperar información sobre cada uno de los miembros en conflicto. En este mismo contexto, puede proporcionar el control personalizado del conflicto para cualquier miembro. Para obtener más información, [consulte simultaneidad optimista: Información](optimistic-concurrency-overview.md)general.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente procesa una iteración en los objetos <xref:System.Data.Linq.ObjectChangeConflict>. Para cada objeto, procesa una iteración en los objetos <xref:System.Data.Linq.MemberChangeConflict>.  
  
> [!NOTE]
> Incluya <xref:System.Reflection> para proporcionar información de <xref:System.Data.Linq.MemberChangeConflict.Member%2A>.  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Cómo: Administrar conflictos de cambios](how-to-manage-change-conflicts.md)
