---
title: "Widening (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.widening"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversiones, tipo de datos"
  - "conversiones, tipo"
  - "conversión de tipos de datos"
  - "conversión de tipos"
  - "Widening (palabra clave)"
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Widening (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Indica que un operador de conversión \(`CType`\) convierte una clase o una estructura en un tipo que puede incluir todos los valores posibles de la clase o la estructura original.  
  
## Convertir con la palabra clave Widening  
 El procedimiento de conversión debe especificar `Public Shared` además de `Widening`.  
  
 Las conversiones de ampliación son siempre satisfactorias en tiempo de ejecución y no provocan nunca pérdida de datos.  Ejemplos son `Single` a `Double`, `Char` a `String` y un tipo derivado a su tipo base.  Esta última conversión es de ampliación ya que el tipo derivado contiene todos los miembros del tipo base y es, por tanto, una instancia del tipo base.  
  
 El código que la utiliza no tiene que emplear `CType` para las conversiones de ampliación, aun cuando `Option Strict` tenga el valor `On`.  
  
 La palabra clave `Widening` se puede utilizar en este contexto:  
  
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Para obtener definiciones de ejemplo de los operadores de conversión de ampliación y restricción, vea [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## Vea también  
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [CType \(Función\)](../../../visual-basic/language-reference/functions/ctype-function.md)   
 [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)