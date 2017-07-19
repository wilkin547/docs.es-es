---
title: "NAVIGATE (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# NAVIGATE (Entity SQL)
Navega por la relación establecida entre entidades.  
  
## Sintaxis  
  
```  
  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## Argumentos  
 `instance-expresssion`  
 Instancia de una entidad.  
  
 `relationship-type`  
 Nombre de tipo de la relación, del archivo de lenguaje de definición de esquemas conceptuales \(CSDL\).`relationship-type` se califica como \<espacio de nombres\>.\<nombre de tipo de relación\>.  
  
 `to`  
 Final de la relación.  
  
 `from`  
 Comienzo de la relación.  
  
## Valor devuelto  
 Si la cardinalidad del extremo final es 1, el valor devuelto será `Ref<T>`. Si la cardinalidad del extremo final es n, el valor devuelto será `Collection<Ref<T>>`.  
  
## Comentarios  
 Las relaciones son estructuras de primera clase en [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] \(EDM\). Se pueden establecer relaciones entre dos o más tipos de entidad y los usuarios pueden navegar en la relación de un extremo \(entidad\) al otro.`from` y `to` son condicionalmente opcionales cuando no hay ambigüedad en la resolución de nombres dentro de la relación.  
  
 NAVIGATE es válido en espacios O y C.  
  
 La forma general de una estructura de navegación es la siguiente:  
  
 navigate\(`instance-expresssion`, `relationship-type`, \[ `to-end` \[, `from-end` \] \] \)  
  
 Por ejemplo:  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 Donde OrderCustomer es el valor de `relationship`, y Customer y Order son los valores de `to-end` \(cliente\) y `from-end` \(pedido\) de la relación. Si OrderCustomer es una relación de n a 1, el tipo de resultado de la expresión navigate es Ref\<Customer\>.  
  
 Lo forma más simple de esta expresión es la siguiente:  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 De igual modo, en una consulta de la forma siguiente, la expresión navigate produce un resultado Collection\<Ref\<Order\>\>.  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 El valor de instance\-expression debe ser de tipo entidad\/referencia.  
  
## Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador NAVIGATE para navegar por la relación establecida entre los tipos de entidad Address y SalesOrderHeader. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [How to: Navigate Relationships with Navigate Operator](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)