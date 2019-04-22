---
title: Tipos de error (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: 07db963ac3cf9d1c0d17c420480189d362cdaf2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831571"
---
# <a name="error-types-visual-basic"></a>Tipos de error (Visual Basic)
En Visual Basic, los errores (también denominado *excepciones*) se dividen en tres categorías: errores de sintaxis, errores de tiempo de ejecución y errores lógicos.  
  
## <a name="syntax-errors"></a>Errores de sintaxis  
 *Errores de sintaxis* son aquellos que aparecen mientras se escribe código. Visual Basic comprueba el código a medida que escribe en el **Editor de código** ventana y le avisa si comete un error, como escribir mal una palabra o uso incorrecto de un elemento del lenguaje. Errores de sintaxis son el tipo más común de errores. Puede corregir fácilmente en el entorno de codificación en cuanto se producen.  
  
> [!NOTE]
>  El `Option Explicit` instrucción es una forma de evitar errores de sintaxis. Nos vemos obligados a declarar por anticipado, todas las variables que se usará en la aplicación. Por lo tanto, cuando esas variables se utilizan en el código, cualquier error tipográfico se detecta inmediatamente y se puede corregir.  
  
## <a name="run-time-errors"></a>Errores de tiempo de ejecución  
 *Errores de tiempo de ejecución* son aquellos que aparecen después de compilar y ejecutar el código. Fragmentos de código que parece estar correcto en que no tiene ningún error de sintaxis, pero que no se ejecutará. Por ejemplo, podría escribir correctamente una línea de código para abrir un archivo. Pero si el archivo está dañado, la aplicación no se puede llevar a cabo la `Open` función y se detiene la ejecución. Puede corregir la mayoría de los errores de tiempo de ejecución por volver a escribir el código defectuoso y, a continuación, volver a compilar y volver a ejecutarlo.  
  
## <a name="logic-errors"></a>Errores lógicos  
 *Errores lógicos* son aquellos que aparecen cuando la aplicación está en uso. Son la mayoría de los resultados inesperada o no deseada a menudo en respuesta a las acciones del usuario. Por ejemplo, una clave mal escrita u otra influencia externa podría hacer que la aplicación deje de funcionar en los parámetros esperados, o por completo. Errores lógicos suelen ser el tipo más difícil de corregir, ya que no siempre está claro dónde se originan.  
  
## <a name="see-also"></a>Vea también

- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Conceptos básicos del depurador](/visualstudio/debugger/debugger-basics)
