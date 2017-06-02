---
title: "TREAT (Entity SQL) | Microsoft Docs"
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
  - "ESQL"
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# TREAT (Entity SQL)
Trata un objeto de un tipo base determinado como un objeto del tipo derivado especificado.  
  
## Sintaxis  
  
```  
  
TREAT (expression as type)  
```  
  
## Argumentos  
 `expression`  
 Cualquier expresión de consulta válida que devuelve una entidad.  
  
> [!NOTE]
>  El tipo de la expresión especificada debe ser un subtipo del tipo de datos especificado, o el tipo de datos debe ser un subtipo del tipo de expresión.  
  
 `type`  
 Tipo de entidad. El tipo debe estar calificado por un espacio de nombres.  
  
> [!NOTE]
>  La expresión especificada debe ser un subtipo del tipo de datos especificado, o el tipo de datos debe ser un subtipo de la expresión.  
  
## Valor devuelto  
 Un valor del tipo de datos especificado.  
  
## Comentarios  
 TREAT se utiliza para realizar una conversión entre clases relacionadas. Por ejemplo, si `Employee` deriva de `Person` y p es de tipo `Person`, `TREAT(p AS NamespaceName.Employee)` convierte una instancia de `Person` genérica a `Employee`; es decir, permite tratar p como `Employee`.  
  
 TREAT se utiliza en situaciones de herencia donde se puede realizar una consulta como la siguiente:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 Este consulta convierte entidades `Person` al tipo `Employee`. Si el valor de p no es realmente de tipo `Employee`, la expresión obtiene el valor `null`.  
  
> [!NOTE]
>  La expresión```Employee```especificada debe ser un subtipo del tipo de datos `Person` especificado, o el tipo de datos debe ser un subtipo de la expresión. De lo contrario, la expresión producirá un error en tiempo de compilación.  
  
 En la tabla siguiente se muestra el comportamiento del tratamiento en algunos patrones típicos y algunos patrones menos comunes. Todas las excepciones se producen en el cliente antes de que se llame al proveedor:  
  
|Modelo|Comportamiento|  
|------------|--------------------|  
|`TREAT (null AS EntityType)`|Devuelve `DbNull`.|  
|`TREAT (null AS ComplexType)`|Inicia una excepción.|  
|`TREAT (null AS RowType)`|Produce una excepción.|  
|`TREAT (EntityType AS EntityType)`|Devuelve `EntityType` o `null`.|  
|`TREAT (ComplexType AS ComplexType)`|Inicia una excepción.|  
|`TREAT (RowType AS RowType)`|Inicia una excepción.|  
  
## Ejemplo  
 La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa el operador TREAT para convertir un objeto del tipo Course en una colección de objetos del tipo OnsiteCourse. La consulta se basa en el [modelo School](http://msdn.microsoft.com/es-es/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Tipos estructurados que aceptan valores NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)