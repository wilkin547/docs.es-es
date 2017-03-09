---
title: "Convenciones tipogr&#225;ficas y de c&#243;digo (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedimientos recomendados, convenciones de código"
  - "convenciones de código, Visual Basic"
  - "convenciones, documentación"
  - "convenciones, código en Visual Basic"
  - "convenciones de documentos"
  - "convenciones tipográficas"
  - "código de Visual Basic, convenciones"
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Convenciones tipogr&#225;ficas y de c&#243;digo (Visual Basic)
[!INCLUDE[vs2017banner](../../visual-basic/developing-apps/includes/vs2017banner.md)]

La documentación de Visual Basic utiliza las siguientes convenciones tipográficas y de código.  
  
## Convenciones tipográficas  
  
|Ejemplo|Descripción|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Las palabras clave específicas del lenguaje y los miembros en tiempo de ejecución se escriben con letras mayúsculas iniciales y tienen el formato que se muestra en este ejemplo.|  
|PequeñoProyecto, ColecciónDeBotones|Las letras y frases que se le pide que escriba tienen el formato que se muestra en este ejemplo.|  
|[Module \(Instrucción\)](../../visual-basic/language-reference/statements/module-statement.md)|Los vínculos que llevan a otra página de Ayuda tienen el formato que aparece en este ejemplo.|  
|*objeto*, *NombreDeVariable*, `argumentList`|Los marcadores de posición para información que proporcione tienen el formato mostrado en este ejemplo.|  
|\[ Shadows \], \[ *listaDeExpresiones* \]|En sintaxis, los elementos opcionales se encierran entre corchetes.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|En sintaxis, si hay que elegir entre dos o más elementos, éstos se encierran entre llaves, separados por barras verticales.<br /><br /> Debe elegir uno, y sólo uno, de los elementos.|  
|\[ `Protected` &#124; `Friend` \]|En sintaxis, si existe la posibilidad de elegir entre dos o más elementos, éstos se encierran entre corchetes, separados por barras verticales.<br /><br /> Puede seleccionar cualquier combinación de elementos o ningún elemento.|  
|\[{ `ByVal` &#124; `ByRef` }\]|En sintaxis, si no puede seleccionar más de un elemento, pero también puede omitir los elementos por completo, éstos se encierran entre corchetes, acotados a su vez por llaves y separados por barras verticales.|  
|*nombreDeMiembro* 1, *nombreDeMiembro*2, *nombreDeMiembro*3|Como se observa en el ejemplo, las diferentes instancias del mismo marcador de posición se distinguen por los subíndices.|  
|*nombreDeMiembro1*<br /><br /> ...<br /><br /> *nombreDeMiembroN*|En sintaxis, se usan puntos suspensivos \(...\) para indicar un número indefinido de elementos del tipo situado inmediatamente delante de los puntos suspensivos.<br /><br /> En código, los puntos suspensivos significan que se ha omitido código en favor de una mayor claridad.|  
|Esc, Entrar|Los nombres de las teclas y las secuencias de teclas en el teclado aparecen en mayúsculas.|  
|ALT\+F1|Si aparece el signo más \(\+\) entre los nombres de las teclas, debe mantener presionada una tecla mientras presiona la otra.  Por ejemplo, Alt\+F1 significa mantener presionada la tecla Alt mientras se presiona la tecla F1.|  
  
## Convenciones de código  
  
|Ejemplo|Descripción|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Los ejemplos de códigos aparecen con una fuente de punto fijo y tienen el formato que aparece en este ejemplo.|  
|La instrucción anterior establece el valor de `sampleString` en "Hello, world\!".|Los elementos de código en texto explicativo aparecen en una fuente de punto fijo, como se muestra en este ejemplo.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|Los comentarios de código se introducen mediante un apóstrofo \('\) o la palabra clave REM.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Un espacio seguido de un signo de subrayado \( \_\) al final de una línea indica que la instrucción continúa en la línea siguiente.|  
  
## Vea también  
 [Referencia del lenguaje Visual Basic](../../visual-basic/language-reference/index.md)   
 [Palabras clave](../../visual-basic/language-reference/keywords/index.md)   
 [Miembros de la biblioteca en tiempo de ejecución de Visual Basic](../../visual-basic/language-reference/runtime-library-members.md)   
 [Convenciones de nomenclatura de Visual Basic](../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Cómo: Interrumpir y combinar instrucciones en código](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)   
 [Comentarios en código](../../visual-basic/programming-guide/program-structure/comments-in-code.md)