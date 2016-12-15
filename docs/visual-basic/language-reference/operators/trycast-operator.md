---
title: "TryCast (Operador) (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.trycast"
  - "trycast"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "TryCast (palabra clave)"
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# TryCast (Operador) (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Introduce una operación de conversión de tipos que no produce una excepción.  
  
## Comentarios  
 Si se produce un error al intentar llevar a cabo una conversión, `CType` y `DirectCast` producen un error <xref:System.InvalidCastException>.  Este atributo puede afectar negativamente al rendimiento de la aplicación.  `TryCast` devuelve [Nothing](../../../visual-basic/language-reference/nothing.md), por lo que en lugar de tener que controlar una posible excepción, solo necesita comprobar el valor devuelto con `Nothing`.  
  
 Utilice la palabra clave `TryCast` del mismo modo que utiliza las palabras clave [CType \(Función\)](../../../visual-basic/language-reference/functions/ctype-function.md) y [DirectCast \(Operador\)](../../../visual-basic/language-reference/operators/directcast-operator.md).  Proporcione una expresión como primer argumento y el tipo al que se va a convertir como segundo argumento.  `TryCast` solo funciona en tipos de referencia, como clases e interfaces.  Requiere que exista una relación de herencia o implementación entre los dos tipos.  Esto significa que un tipo debe heredarse del otro o implementar al otro.  
  
## Errores  
 `TryCast` genera un error del compilador si detecta que no existe ninguna relación de herencia o implementación.  Sin embargo, la ausencia de un compilador no garantiza que la conversión se realice correctamente.  Si la conversión deseada es de restricción, puede producirse un error en tiempo de ejecución.  Si esto ocurre, `TryCast` devuelve [Nothing](../../../visual-basic/language-reference/nothing.md).  
  
## Palabras clave para conversiones  
 A continuación se incluye una comparación de las palabras clave de conversión de tipos.  
  
|||||  
|-|-|-|-|  
|Palabra clave|Tipos de datos|Relación de argumentos|Error en tiempo de ejecución|  
|[CType \(Función\)](../../../visual-basic/language-reference/functions/ctype-function.md)|Cualquier tipo de datos|La conversión de ampliación o restricción debe definirse entre dos tipos de datos|Produce <xref:System.InvalidCastException>|  
|[DirectCast \(Operador\)](../../../visual-basic/language-reference/operators/directcast-operator.md)|Cualquier tipo de datos|Un tipo debe heredarse del otro tipo o implementarlo|Produce <xref:System.InvalidCastException>|  
|`TryCast`|Sólo tipos de referencia|Un tipo debe heredarse del otro tipo o implementarlo|Devuelve [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## Vea también  
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)