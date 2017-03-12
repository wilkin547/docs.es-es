---
title: "Narrowing (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.narrowing"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversiones, tipo de datos"
  - "conversiones, tipo"
  - "conversión de tipos de datos"
  - "Narrowing (palabra clave)"
  - "conversión de tipos"
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Narrowing (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Indica que un operador de conversión \(`CType`\) convierte una clase o una estructura en un tipo que quizá no pueda incluir algunos de los valores posibles de la clase o la estructura original.  
  
## Convertir con la palabra clave Narrowing  
 El procedimiento de conversión debe especificar `Public Shared` además de `Narrowing`.  
  
 Las conversiones de restricción no son siempre satisfactorias en tiempo de ejecución y pueden generar errores o provocar pérdida de datos.  Ejemplos son `Long` a `Integer`, `String` a `Date` y un tipo base a un tipo derivado.  Esta última conversión es de restricción, ya que es posible que el tipo base no contenga todos los miembros del tipo derivado y no es, por tanto, una instancia del tipo derivado.  
  
 Si `Option Strict` tiene el valor `On`, el código que lo utiliza debe emplear `CType` para todas las conversiones de restricción.  
  
 La palabra clave `Narrowing` se puede utilizar en este contexto:  
  
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## Vea también  
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [CType \(Función\)](../../../visual-basic/language-reference/functions/ctype-function.md)   
 [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)