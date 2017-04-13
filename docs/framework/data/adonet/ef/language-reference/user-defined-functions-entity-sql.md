---
title: "Funciones definidas por el usuario (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Funciones definidas por el usuario (Entity SQL)
Entity SQL admite llamadas a funciones definidas por el usuario en una consulta.  Puede definir estas funciones insertadas en la consulta \(vea [How to: Call a User\-Defined Function](http://msdn.microsoft.com/es-es/ad131b86-8b4e-4747-8605-d4fc64fb9d02)\) o como parte del modelo conceptual \(vea [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/es-es/0dad7b8b-58f6-4271-b238-f34810d68e5f).  Las funciones del modelo conceptual se definen como un comando de Entity SQL en el elemento [DefiningExpression](http://msdn.microsoft.com/es-es/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) de un elemento [Function](http://msdn.microsoft.com/es-es/dc3beca7-55cf-4977-8db0-5064cdbab134) del modelo conceptual.  
  
 Entity SQL le permite definir las funciones en el propio comando de consulta.  El operador [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) define las funciones Inline.  Puede definir varias funciones con el mismo nombre en un único comando, siempre que sus firmas sean únicas.  Para obtener más información, consulta [Resolución de la sobrecarga de funciones](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## Vea también  
 [Funciones](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)