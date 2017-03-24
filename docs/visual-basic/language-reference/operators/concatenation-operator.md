---
title: "&amp; (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.&"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "& (operador)"
  - "operador y comercial (&)"
  - "And (&) (operador)"
  - "operadores de concatenación, sintaxis"
  - "cadenas [Visual Basic], concatenar"
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# &amp; (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Genera la concatenación de cadena de dos expresiones.  
  
## Sintaxis  
  
```  
  
result = expression1 & expression2  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Cualquier variable `String` u `Object`.  
  
 `expression1`  
 Obligatorio.  Cualquier expresión con un tipo de datos que se amplíe a `String`.  
  
 `expression2`  
 Obligatorio.  Cualquier expresión con un tipo de datos que se amplíe a `String`.  
  
## Comentarios  
 Si el tipo de datos de `expression1` o `expression2` no es `String`, pero se amplía a `String`, se convertirá en `String`.  Si uno de los tipo de datos no se amplía a `String`, el compilador generará un error.  
  
 El tipo de datos de `result` será `String`.  Si una o ambas expresiones dan como resultado [Nothing](../../../visual-basic/language-reference/nothing.md) o tienen un valor <xref:System.DBNull.Value?displayProperty=fullName>, se consideran como una cadena con un valor "".  
  
> [!NOTE]
>  El operador `&` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  El carácter de la y comercial \(&\) también se puede utilizar para identificar las variables como tipo `Long`.  Para obtener más información, vea [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## Ejemplo  
 En este ejemplo se usa el operador `&` para forzar la concatenación de cadenas.  El resultado es un valor de cadena que representa la concatenación de ambos operandos.  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## Vea también  
 [&\= \(Operador\)](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores de concatenación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)