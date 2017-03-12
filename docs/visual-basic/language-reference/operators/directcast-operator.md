---
title: "DirectCast (Operador) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.directCast"
  - "directCast"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DirectCast (palabra clave)"
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# DirectCast (Operador) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Introduce una operación de conversión de tipos basada en la herencia o la implementación.  
  
## Comentarios  
 `DirectCast` no utiliza rutinas auxiliares para conversión de Visual Basic en tiempo de ejecución, por lo que puede proporcionar un mejor rendimiento que `CType` para convertir al tipos de datos `Object` y desde él.  
  
 Se utiliza la palabra clave `DirectCast` de manera similar a como se utiliza la palabra clave [CType \(Función\)](../../../visual-basic/language-reference/functions/ctype-function.md) y [TryCast \(Operador\)](../../../visual-basic/language-reference/operators/trycast-operator.md).  Proporcione una expresión como primer argumento y el tipo al que se va a convertir como segundo argumento.  `DirectCast`necesita que exista una relación de herencia o implementación entre los dos tipos de datos de los dos argumentos.  Esto significa que un tipo debe heredarse del otro o implementar al otro.  
  
## Errores  
 `DirectCast` genera un error del compilador si detecta que no existe ninguna relación herencia o de implementación.  Sin embargo, la ausencia de un compilador no garantiza que la conversión se realice correctamente.  Si la conversión deseada es de restricción, puede producirse un error en tiempo de ejecución.  Si es así, el tiempo de ejecución produce un error <xref:System.InvalidCastException>.  
  
## Palabras clave para conversiones  
 A continuación se incluye una comparación de las palabras clave de conversión de tipos.  
  
|||||  
|-|-|-|-|  
|Palabra clave|Tipos de datos|Relación de argumentos|Error en tiempo de ejecución|  
|[CType \(Función\)](../../../visual-basic/language-reference/functions/ctype-function.md)|Cualquier tipo de datos|La conversión de ampliación o restricción debe definirse entre dos tipos de datos|Produce <xref:System.InvalidCastException>|  
|`DirectCast`|Cualquier tipo de datos|Un tipo debe heredarse del otro tipo o implementarlo|Produce <xref:System.InvalidCastException>|  
|[TryCast \(Operador\)](../../../visual-basic/language-reference/operators/trycast-operator.md)|Sólo tipos de referencia|Un tipo debe heredarse del otro tipo o implementarlo|Devuelve [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## Ejemplo  
 El ejemplo siguiente muestra dos usos de `DirectCast`, uno con un resultado satisfactorio en tiempo de ejecución y otro que no lo tiene.  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/visualbasic/directcast-operator_1.vb)]  
  
 En el ejemplo anterior, el tipo en tiempo de ejecución de `q` es `Double`.  `CType` tiene un resultado satisfactorio porque `Double` puede convertirse en `Integer`.  No obstante, el primer `DirectCast` no tiene un resultado satisfactorio porque el tipo en tiempo de ejecución de `Double` no tiene relación de herencia con `Integer`, aunque existe una conversión.  El segundo `DirectCast` tiene un resultado satisfactorio porque convierte del tipo <xref:System.Windows.Forms.Form> al tipo <xref:System.Windows.Forms.Control> del que <xref:System.Windows.Forms.Form> hereda.  
  
## Vea también  
 <xref:System.Convert.ChangeType%2A?displayProperty=fullName>   
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)