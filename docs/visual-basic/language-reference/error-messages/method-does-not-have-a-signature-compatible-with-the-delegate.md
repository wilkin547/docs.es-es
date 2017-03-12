---
title: "El m&#233;todo no tiene una firma compatible con el delegado | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36563"
  - "vbc36563"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36563"
ms.assetid: 3ca8b873-e98d-419b-95f2-d75bd2a9eb6c
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# El m&#233;todo no tiene una firma compatible con el delegado
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Existe una incompatibilidad entre las firmas del método y del delegado que está intentando usar.  La instrucción `Delegate` define los tipos de parámetros y los tipos devueltos de una clase de delegado.  Cualquier procedimiento que tenga parámetros coincidentes de tipos compatibles y de tipos devueltos puede servir para crear una instancia de este tipo de delegado.  
  
 **Id. de error**: BC36563  
  
## Vea también  
 [AddressOf \(Operador\)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Resolución de sobrecargas](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)