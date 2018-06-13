---
title: 'Cómo: Recuperar información de conflictos de miembros'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 5d0788daac6c1be8dd7670c330d1efc36b074c2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354386"
---
# <a name="how-to-retrieve-member-conflict-information"></a>Cómo: Recuperar información de conflictos de miembros
Puede utilizar la clase <xref:System.Data.Linq.MemberChangeConflict> para recuperar información sobre cada uno de los miembros en conflicto. En este mismo contexto, puede proporcionar el control personalizado del conflicto para cualquier miembro. Para obtener más información, consulte [simultaneidad optimista: información general sobre](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente procesa una iteración en los objetos <xref:System.Data.Linq.ObjectChangeConflict>. Para cada objeto, procesa una iteración en los objetos <xref:System.Data.Linq.MemberChangeConflict>.  
  
> [!NOTE]
>  Incluya <xref:System.Reflection> para proporcionar información de <xref:System.Data.Linq.MemberChangeConflict.Member%2A>.  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Administración de conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
