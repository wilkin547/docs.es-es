---
title: "Cómo: Representar columnas calculadas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: eef3d12d3b0baa849d8eee1a01a87e3c6eee1c7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-computed-columns"></a>Cómo: Representar columnas calculadas
Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> propiedad en un <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para representar una columna cuyo contenido es el resultado del cálculo.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite las columnas calculadas como claves principales.  
  
### <a name="to-represent-a-computed-column"></a>Para representar una columna calculada  
  
1.  Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Asigne una representación de cadena de la fórmula a la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
## <a name="see-also"></a>Vea también  
 [El modelo de LINQ to SQL objeto](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Cómo: personalizar clases de entidad mediante el Editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
