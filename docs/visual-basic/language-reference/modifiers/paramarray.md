---
title: "ParamArray (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ParamArray"
  - "ParamArray"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ParamArray (palabra clave)"
  - "ParamArray (palabra clave), sintaxis"
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# ParamArray (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que un parámetro de procedimiento toma una matriz opcional de elementos del tipo de especificado.  `ParamArray` solo se puede utilizar en el último parámetro de una lista de parámetros.  
  
## Comentarios  
 `ParamArray` permite pasar al procedimiento un número arbitrario de argumentos.  Un parámetro `ParamArray` siempre se declara mediante [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
 Puede proporcionar uno o más argumentos en un parámetro `ParamArray` pasando una matriz del tipo de datos adecuado, una lista de valores separados por comas o nada en absoluto.  Para obtener más detalles, vea "Llamar a un lista de parámetros" en [Matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
>  Si se trabaja con matrices cuyo tamaño es excesivamente grande, existe el riesgo de sobrecargar alguna capacidad interna de la aplicación.  Si acepta un matriz de parámetros desde el código de llamada, debe comprobar su longitud y seguir los pasos adecuados si es demasiado grande para la aplicación.  
  
 El modificador `ParamArray` se puede utilizar en estos contextos:  
  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)   
 [Matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)