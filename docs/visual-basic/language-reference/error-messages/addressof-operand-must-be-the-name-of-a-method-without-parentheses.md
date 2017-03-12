---
title: "El operando &#39;AddressOf&#39; debe ser el nombre de un m&#233;todo (sin par&#233;ntesis) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30577"
  - "bc30577"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30577"
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# El operando &#39;AddressOf&#39; debe ser el nombre de un m&#233;todo (sin par&#233;ntesis)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El operador `AddressOf` crea una instancia de delegado de procedimiento que hace referencia a un procedimiento específico.  La sintaxis es la siguiente.  
  
 `AddressOf` `procedurename`  
  
 Ha puesto paréntesis alrededor del argumento que sigue a `AddressOf`, cuando no son necesarios.  
  
 **Identificador de error:** BC30577  
  
### Para corregir este error  
  
1.  Quite los paréntesis alrededor del argumento que sigue a `AddressOf`.  
  
2.  Asegúrese de que el argumento es un nombre de método.  
  
## Vea también  
 [AddressOf \(Operador\)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)