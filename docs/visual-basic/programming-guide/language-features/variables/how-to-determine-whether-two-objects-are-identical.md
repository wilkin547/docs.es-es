---
title: "C&#243;mo: Determinar si dos objetos son id&#233;nticos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables de objeto, determinar identidad"
  - "objetos [Visual Basic], comparar"
  - "pruebas, objetos"
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# C&#243;mo: Determinar si dos objetos son id&#233;nticos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], dos referencias de variable se consideran idénticas si sus punteros son los mismos, es decir, si ambas variables señalan la misma instancia de clase en la memoria.  Por ejemplo, en una aplicación de Windows Forms, es posible que desee realizar una comparación para determinar si la instancia actual \(`Me`\) es igual que una instancia determinada, como `Form2`.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona dos operadores para comparar los punteros.  [Is \(Operador\)](../../../../visual-basic/language-reference/operators/is-operator.md) devuelve `True` si los objetos son idénticos e [IsNot \(Operador\)](../../../../visual-basic/language-reference/operators/isnot-operator.md) devuelve `True` si no lo son.  
  
## Determinar si dos objetos son idénticos  
  
#### Para determinar si dos objetos son idénticos  
  
1.  Prepare una expresión `Boolean` para probar los dos objetos.  
  
2.  En la expresión de prueba, utilice el operador `Is` con los dos objetos como operandos.  
  
     `Is` devuelve `True` si los objetos señalan a la misma instancia de clase.  
  
## Determinar si dos objetos no son idénticos  
 A veces, desea realizar una acción cuando los dos objetos no son idénticos y puede ser complicado combinar `Not` e `Is`, por ejemplo `If Not obj1 Is obj2`.  En estos casos puede utilizar el operador `IsNot`.  
  
#### Para determinar si dos objetos no son idénticos  
  
1.  Prepare una expresión `Boolean` para probar los dos objetos.  
  
2.  En la expresión de prueba, utilice el operador `IsNot` con los dos objetos como operandos.  
  
     `IsNot` devuelve `True` si los objetos no señalan a la misma instancia de clase.  
  
## Ejemplo  
 El ejemplo siguiente prueba pares de variables `Object` para ver si señalan a la misma instancia de clase.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/visualbasic/how-to-determine-whether_1_1.vb)]  
  
 El ejemplo anterior muestra el siguiente resultado.  
  
 `objA different from objB?  True`  
  
 `objA identical to objC?  True`  
  
## Vea también  
 [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Is \(Operador\)](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot \(Operador\)](../../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Cómo: Determinar si dos objetos están relacionados](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)