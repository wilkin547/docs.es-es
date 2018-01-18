---
title: "Cómo: Representar claves principales"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c832b7c54ecbd1f4c4a3bebcbf7f293b9a45e46c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-represent-primary-keys"></a>Cómo: Representar claves principales
Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar una propiedad o campo para representar la clave principal para una columna de base de datos.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite las columnas calculadas como claves principales.  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a>Para designar una propiedad o un campo como clave principal  
  
1.  Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Especifique el valor como `true`.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Personalización de clases de entidades con el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
