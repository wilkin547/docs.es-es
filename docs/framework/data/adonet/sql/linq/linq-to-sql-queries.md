---
title: "Consultas en LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Consultas en LINQ to SQL
Las consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se definen utilizando la misma sintaxis que utilizaría en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  La única diferencia es que los objetos a los que se hace referencia en las consultas se asignan a elementos de una base de datos.  Para obtener más información, consulte [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte las consultas que se escriben en consultas SQL equivalentes y las envía al servidor para su procesamiento. Más específicamente, la aplicación utiliza la API de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para solicitar la ejecución de la consulta.  Después, el proveedor [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] transforma la consulta en texto SQL y delega la ejecución al proveedor ADO. El proveedor ADO devuelve los resultados de la consulta como `DataReader`.  El proveedor [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte los resultados de ADO en una colección <xref:System.Linq.IQueryable> de objetos de usuario.  
  
> [!NOTE]
>  La mayoría de los métodos y operadores de los tipos integrados de [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] tienen equivalentes directos en SQL.  Los que [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] no puede convertir generan excepciones en tiempo de ejecución.  Para obtener más información, consulte [Correspondencia de tipos SQL\-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 La tabla siguiente muestra las similitudes y diferencias entre los elementos de las consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Item|Consulta LINQ|Consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|-------------------|-------------------------------------------------------------------------|  
|Tipo de valor devuelto de la variable local que contiene la consulta \(para las consultas que devuelven secuencias\)|`IEnumerable` genérico|`IQueryable` genérico|  
|Especificar el origen de datos|Utiliza la cláusula `From` \([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\) o `from` \(C\#\)|Igual|  
|Filtrado|Utiliza la cláusula `Where`\/`where`|Igual|  
|Agrupar|Utiliza la cláusula `Group…By`\/`groupby`|Igual|  
|Seleccionar \(proyectar\)|Utiliza la cláusula `Select`\/`select`|Igual|  
|Ejecución diferida frente a ejecución inmediata|Vea [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)|Igual|  
|Implementar combinaciones|Utiliza la cláusula `Join`\/`join`|Puede utilizar la cláusula `Join`\/`join`, pero utiliza el atributo <xref:System.Data.Linq.Mapping.AssociationAttribute> más eficazmente.  Para obtener más información, vea [Realizar consultas en varias relaciones](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Ejecución remota frente a ejecución local||Para obtener más información, vea [Ejecución remota y ejecución local](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md).|  
|Consultas con transmisión por frecuencias frente a consultas con almacenamiento en caché|No aplicable en un escenario de memoria local||  
  
## Vea también  
 [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)   
 [Basic LINQ Query Operations](../Topic/Basic%20LINQ%20Query%20Operations%20\(C%23\).md)   
 [Type Relationships in LINQ Query Operations](../Topic/Type%20Relationships%20in%20LINQ%20Query%20Operations%20\(C%23\).md)   
 [Conceptos de consulta](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)