---
title: "Expresiones de consulta (Entity SQL) | Microsoft Docs"
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
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Expresiones de consulta (Entity SQL)
Una expresión de consulta combina muchos operadores de consulta diferentes en una sintaxis única.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona varios tipos de expresiones, incluidos los siguientes: [literales](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [parámetros](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [variables](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), operadores, [funciones](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md), operadores de conjuntos, etc.  Para obtener más información, consulta [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).  
  
## Cláusulas  
 Una expresión de consulta se compone de una serie de cláusulas que aplican operaciones sucesivas a una colección de objetos.  Se basan en las mismas cláusulas que se encuentran en una instrucción SELECT estándar de SQL: [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [WHERE](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md) y [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
## Ámbito  
 Los nombres que se definen en la cláusula FROM se incluyen en el ámbito de FROM en orden de aparición, de izquierda a derecha.  En la lista de JOIN, las expresiones pueden hacer referencia a los nombres que se definieron en la lista anteriormente.  Las propiedades públicas de los elementos identificados en la cláusula FROM no se agregan al ámbito de FROM. Siempre se debe hacer referencia a ellas mediante el nombre completo del alias.  Normalmente, todas las partes de la expresión SELECT se consideran dentro del ámbito de FROM.  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)