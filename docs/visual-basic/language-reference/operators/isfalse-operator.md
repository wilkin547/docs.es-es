---
title: "IsFalse (Operador) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.isfalse"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AndAlso (operador)"
  - "IsFalse (operador)"
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# IsFalse (Operador) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Determina si una expresión es `False`.  
  
 No puede llamar a `IsFalse` de forma explícita en su código, pero el compilador de Visual Basic puede utilizarlo para generar código de las cláusulas `AndAlso`.  Si define una clase o estructura y utiliza luego una variable de ese tipo en una cláusula `AndAlso`, debe definir `IsFalse` en esa cláusula o estructura.  
  
 El compilador tiene en cuenta los operadores `IsFalse` e `IsTrue` como un *par coincidente*.  Esto significa que si define uno de ellos, también debe definir el otro.  
  
> [!NOTE]
>  El operador `IsFalse` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando el operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo de código siguiente se define el esquema de una estructura que incluye las definiciones para los operadores `IsFalse` e `IsTrue`.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/isfalse-operator_1.vb)]  
  
## Vea también  
 [IsTrue \(Operador\)](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [AndAlso \(Operador\)](../../../visual-basic/language-reference/operators/andalso-operator.md)