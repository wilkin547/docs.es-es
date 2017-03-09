---
title: "AddressOf (Operador) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "AddressOf"
  - "vb.AddressOf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "direcciones, pasar a procedimientos de la API"
  - "AddressOf (operador)"
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# AddressOf (Operador) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Crea una instancia de delegado del procedimiento que hace referencia al procedimiento específico.  
  
## Sintaxis  
  
```  
  
AddressOf procedurename  
```  
  
## Elementos  
 `procedurename`  
 Obligatorio.  Especifica el procedimiento al que va a hacer referencia el delegado de procedimiento recientemente creado.  
  
## Comentarios  
 El operador `AddressOf` crea una función delegada que apunta a la función especificada por `procedurename`.  Cuando el procedimiento especificado es un método de instancia, la función delegada hace referencia tanto a la instancia como al método.  A continuación, cuando se invoca la función delegada, se llama al método especificado de la instancia especificada.  
  
 El operador `AddressOf` puede utilizarse como operando de un constructor delegado o bien emplearse en un contexto en el cual sea posible determinar el tipo del delegado a través del compilador.  
  
## Ejemplo  
 Este ejemplo usa el operador `AddressOf` para designar un delegado que controle el evento `Click` de un botón.  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/addressof-operator_1.vb)]  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza el operador `AddressOf` para designar la función de inicio de un subproceso.  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/addressof-operator_2.vb)]  
  
## Vea también  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)