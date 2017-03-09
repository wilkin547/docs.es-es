---
title: "IsTrue (Operador) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.istrue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IsTrue (operador)"
  - "OrElse (operador) [Visual Basic]"
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# IsTrue (Operador) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Determina si una expresión es `True`.  
  
 No puede llamar a `IsTrue` de forma explícita en su código, pero el compilador de Visual Basic puede utilizarlo para generar código de las cláusulas `OrElse`.  Si define una clase o estructura y utiliza luego una variable de ese tipo en una cláusula `OrElse`, debe definir `IsTrue` en esa cláusula o estructura.  
  
 El compilador tiene en cuenta los operadores `IsTrue` e `IsFalse` como un *par coincidente*.  Esto significa que si define uno de ellos, también debe definir el otro.  
  
## Uso de IsTrue del compilador  
 Una vez que ha definido una clase o estructura, puede utilizar una variable de ese tipo en una instrucción `For`, `If`, `Else` `If` o `While` o en una cláusula `When`.  Si lo hace, el compilador requiere un operador que convierta el tipo en un valor `Boolean` para que pueda probar una condición.  El compilador busca un operador conveniente en el orden siguiente:  
  
1.  Un operador de conversión de ampliación de la clase o estructura a `Boolean`.  
  
2.  Un operador de conversión de ampliación de la clase o estructura a `Boolean?`.  
  
3.  El operador `IsTrue` de la clase o estructura.  
  
4.  Una conversión de restricción a `Boolean?` que no implique una conversión de `Boolean` a `Boolean?`.  
  
5.  Un operador de conversión de restricción de la clase o estructura a `Boolean`.  
  
 Si no se ha definido ninguna conversión a `Boolean` ni un operador `IsTrue`, el compilador indica un error.  
  
> [!NOTE]
>  El operador `IsTrue` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando el operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo de código siguiente se define el esquema de una estructura que incluye las definiciones para los operadores `IsFalse` e `IsTrue`.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/istrue-operator_1.vb)]  
  
## Vea también  
 [IsFalse \(Operador\)](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [OrElse \(Operador\)](../../../visual-basic/language-reference/operators/orelse-operator.md)