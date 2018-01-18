---
title: "Cómo: Recuperar información de conflictos de miembros"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fab9111bb14b41244fab3bcd9c2ea0b0f91d72ce
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
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
