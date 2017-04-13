---
title: "Literales NULL e inferencia de tipos (Entity SQL) | Microsoft Docs"
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
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Literales NULL e inferencia de tipos (Entity SQL)
Los literales null son compatibles con cualquier tipo del sistema de tipos [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  Sin embargo, para que el tipo de un literal null se infiera correctamente, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] impone determinadas restricciones sobre dónde se puede utilizar un literal null.  
  
## Valores null con tipo  
 Los valores null con tipo se pueden utilizar en cualquier lugar.  La inferencia de tipos no es necesaria para los valores null con tipo porque el tipo es conocido.  Por ejemplo, puede crear un valor null de tipo Int16 con la siguiente construcción [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
 `(cast(null as Int16))`  
  
## Literales null flotantes  
 Los literales null flotantes se pueden utilizar en los siguientes contextos.  
  
-   Como un argumento para una expresión CAST o TREAT.  Esta es la forma que se recomienda para generar una expresión null con tipo.  
  
-   Como un argumento para un método o una función.  Se aplican las reglas estándar de sobrecarga.  
  
-   Como uno de los argumentos de una expresión aritmética, como \+, \- o \/.  El resto de argumentos no pueden ser literales null; si fuera el caso, no es posible la inferencia de tipos.  
  
-   Como cualquiera de los argumentos de una expresión lógica \(AND, OR o NOT\).  Todos los argumentos se conocen como que son del tipo Boolean.  
  
-   Como el argumento a una expresión IS NULL o IS NOT NULL.  
  
-   Como uno o más de los argumentos de una expresión LIKE.  Se espera que todos los argumentos sean cadenas.  
  
-   Como uno o más de los argumentos de un constructor de tipo con nombre.  
  
-   Como uno o más de los argumentos de un constructor multiset.  Al menos uno de los argumentos de un constructor multiset debe ser una expresión que no sea un literal null.  
  
-   Como uno o más de los argumentos de una expresión THEN o ELSE en una expresión CASE.  Al menos una de las expresiones THEN o ELSE en la expresión CASE debe ser una expresión distinta a una literal null.  
  
 Los literales null flotantes no se pueden utilizar en otros escenarios.  Por ejemplo, no se puede utilizar como argumentos para un constructor row.  
  
## Vea también  
 [Información general de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)