---
title: ". (Acceso a miembros) (Entity SQL) | Microsoft Docs"
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
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# . (Acceso a miembros) (Entity SQL)
El operador punto \(.\) es el operador de acceso a miembros de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  El operador de acceso a miembros se usa para obtener el valor de una propiedad o un campo de una instancia de un tipo del modelo conceptual estructural.  
  
## Sintaxis  
  
```  
expression.identifier  
```  
  
## Argumentos  
 `expression`  
 Instancia de un tipo del modelo conceptual estructural.  
  
 `identifier`  
 Propiedad o campo que pertenece a una instancia de objeto.  
  
## Comentarios  
 El operador punto \(.\) se puede utilizar para extraer campos de un registro, que es similar a extraer propiedades de un tipo complejo o de entidad.  Por ejemplo, si n de tipo Name es un miembro de tipo Person y p es una instancia de tipo Person, entonces p.  n es una expresión de acceso a miembros legal que produce un valor del tipo Name.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)