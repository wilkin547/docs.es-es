---
title: Procedimiento para recuperar información de conflictos de entidades
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: e8c548ac632454d9c488ebd5f7b471f6759418fb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155879"
---
# <a name="how-to-retrieve-entity-conflict-information"></a>Procedimiento para recuperar información de conflictos de entidades

Puede utilizar objetos de la clase <xref:System.Data.Linq.ObjectChangeConflict> para proporcionar información sobre los conflictos que revelan las excepciones <xref:System.Data.Linq.ChangeConflictException>. Para obtener más información, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se recorre en iteración una lista de conflictos acumulados.  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para administrar conflictos de cambios](how-to-manage-change-conflicts.md)
