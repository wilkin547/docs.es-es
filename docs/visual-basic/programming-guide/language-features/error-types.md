---
title: "Tipos de error (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "errores [Visual Basic], lógicos"
  - "errores [Visual Basic], sintaxis"
  - "errores [Visual Basic], tipos"
  - "excepciones, tipos"
  - "errores lógicos, Visual Basic"
  - "errores en tiempo de ejecución, tipos de error"
  - "sintaxis: errores, Visual Basic"
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tipos de error (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], los errores \(también denominados *excepciones*\) se dividen en tres categorías: errores de sintaxis, errores en tiempo de ejecución y errores lógicos.  
  
## Errores de sintaxis  
 Los *errores de sintaxis* son aquellos que aparecen mientras se escribe el código.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] comprueba el código mientras se escribe en la ventana **Editor de código** y alerta si se comete un error, por ejemplo, si se escribe mal una palabra o se usa un elemento del lenguaje de forma incorrecta.  Los errores sintácticos son los errores más frecuentes.  Se pueden corregir fácilmente en el entorno de codificación en cuanto se producen.  
  
> [!NOTE]
>  La instrucción `Option Explicit` es una medida para evitar los errores de sintaxis.  Le obliga a declarar, por anticipado, todas las variables que se vayan a utilizar en la aplicación.  De este modo, cuando se utilicen las variables en el código, cualquier error tipográfico que se produzca se capturará de forma inmediata, y podrá corregirse.  
  
## Errores en tiempo de ejecución  
 Los *errores en tiempo de ejecución* son aquellos que aparecen solamente después de la compilación y la ejecución del código.  Pueden darse errores de este tipo, por ejemplo, en fragmentos de código aparentemente correctos, por no presentar errores sintácticos, pero que no se ejecutan correctamente.  Por ejemplo, podría escribir correctamente una línea de código que abre un archivo.  Pero, si el archivo está dañado, la aplicación no podrá ejecutar la función `Open` y se detendrá su ejecución.  La mayoría de los errores de este tipo pueden corregirse modificando el código que presenta errores, para después compilarlo y volver a ejecutarlo.  
  
## Errores lógicos  
 Los *errores lógicos* son aquellos que aparecen cuando la aplicación está en funcionamiento.  Son a menudo resultados no deseados o inesperados en respuesta a acciones del usuario.  Por ejemplo, una clave mal escrita u otra influencia externa podría hacer que la aplicación dejase de funcionar aún siendo correctos los parámetros, o que simplemente no funcionase.  Por lo general, los errores lógicos son los más difíciles de corregir, puesto que no siempre está claro dónde se originan.  
  
## Vea también  
 [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Conceptos básicos del depurador](/visual-studio/debugger/debugger-basics)