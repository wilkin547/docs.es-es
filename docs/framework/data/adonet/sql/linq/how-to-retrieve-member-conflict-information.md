---
title: Procedimiento para recuperar información de conflictos de miembros
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 4848ef69914f0520d2365538faea7fa064c1a15c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155814"
---
# <a name="how-to-retrieve-member-conflict-information"></a>Procedimiento para recuperar información de conflictos de miembros

Puede utilizar la clase <xref:System.Data.Linq.MemberChangeConflict> para recuperar información sobre cada uno de los miembros en conflicto. En este mismo contexto, puede proporcionar el control personalizado del conflicto para cualquier miembro. Para obtener más información, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).  
  
## <a name="example"></a>Ejemplo  

 El código siguiente procesa una iteración en los objetos <xref:System.Data.Linq.ObjectChangeConflict>. Para cada objeto, procesa una iteración en los objetos <xref:System.Data.Linq.MemberChangeConflict>.  
  
> [!NOTE]
> Incluya <xref:System.Reflection> para proporcionar información de <xref:System.Data.Linq.MemberChangeConflict.Member%2A>.  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para administrar conflictos de cambios](how-to-manage-change-conflicts.md)
