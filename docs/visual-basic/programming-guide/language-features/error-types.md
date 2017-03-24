---
title: Tipos de error (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors, Visual Basic
- run-time errors, types of errors
- syntax errors, Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d48756b74baf757f043e68124d8b65c2f613e595
ms.lasthandoff: 03/13/2017

---
# <a name="error-types-visual-basic"></a>Tipos de error (Visual Basic)
En [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], errores (también denominada *excepciones*) se dividen en tres categorías: errores de sintaxis, errores en tiempo de ejecución y errores lógicos.  
  
## <a name="syntax-errors"></a>Errores de sintaxis  
 *Errores de sintaxis* son aquellos que aparecen mientras escribe el código. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]comprueba el código mientras se escribe en el **Editor de código** ventana y le avisa si comete un error, como escribir mal una palabra o uso incorrecto de un elemento del lenguaje. Errores de sintaxis son el tipo más común de errores. Puede corregir fácilmente en el entorno de codificación en cuanto se producen.  
  
> [!NOTE]
>  El `Option Explicit` instrucción es una medida para evitar errores de sintaxis. Obliga a declarar, por anticipado, todas las variables que se utilizará en la aplicación. Por lo tanto, cuando esas variables se utilizan en el código, cualquier error tipográfico se detecta inmediatamente y se puedan solucionar.  
  
## <a name="run-time-errors"></a>Errores en tiempo de ejecución  
 *Errores en tiempo de ejecución* son aquellos que aparecen después de compilar y ejecutar el código. Fragmentos de código que parece ser correcta, ya que no tiene errores de sintaxis, pero que no se ejecutará. Por ejemplo, podría escribir correctamente una línea de código para abrir un archivo. Pero si el archivo está dañado, la aplicación no puede ejecutar el `Open` (función) y lo deja de ejecutarse. Puede corregir la mayoría de los errores de tiempo de ejecución por volver a escribir el código defectuoso y, a continuación, volver a compilar y volver a ejecutarla.  
  
## <a name="logic-errors"></a>Errores lógicos  
 *Errores lógicos* son aquellos que aparecen cuando la aplicación está en uso. Son la mayoría de los resultados inesperada o no deseada a menudo en respuesta a las acciones del usuario. Por ejemplo, una clave mal escrita u otra influencia externa podría hacer que la aplicación deje de funcionar dentro de los parámetros esperados, o por completo. Errores lógicos generalmente son el tipo más difícil de solucionar, ya que no siempre está claro dónde se originan.  
  
## <a name="see-also"></a>Vea también  
 [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Conceptos básicos del depurador](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)
