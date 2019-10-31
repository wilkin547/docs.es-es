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
ms.openlocfilehash: 5be91162d5c178fc032fba32605107c3fcd4d16b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197202"
---
# <a name="error-types-visual-basic"></a>Tipos de error (Visual Basic)
En Visual Basic, los errores se dividen en una de estas tres categorías: errores de sintaxis, errores en tiempo de ejecución y errores lógicos.

## <a name="syntax-errors"></a>Errores de sintaxis
 Los *errores de sintaxis* son los que aparecen mientras se escribe código. Si usa Visual Studio, Visual Basic comprueba el código a medida que lo escribe en la ventana del **Editor de código** y le alerta Si comete un error, como la escritura incorrecta de una palabra o el uso de un elemento del lenguaje de forma incorrecta. Si se compila desde la línea de comandos, Visual Basic muestra un error del compilador con información sobre el error de sintaxis. Los errores de sintaxis son el tipo más común de errores. Puede corregirlas fácilmente en el entorno de codificación en cuanto se produzcan.

> [!NOTE]
> La instrucción `Option Explicit` es un medio para evitar errores de sintaxis. Obliga a declarar, de antemano, todas las variables que se van a usar en la aplicación. Por lo tanto, cuando esas variables se usan en el código, los errores tipográficos se detectan inmediatamente y se pueden corregir.

## <a name="run-time-errors"></a>Errores en tiempo de ejecución
 Los *errores en tiempo de ejecución* son aquellos que aparecen solo después de compilar y ejecutar el código. Estos incluyen código que puede parecer correcto en que no tiene errores de sintaxis, pero que no se ejecutará. Por ejemplo, puede escribir correctamente una línea de código para abrir un archivo. Pero si el archivo no existe, la aplicación no puede abrir el archivo y produce una excepción. Puede corregir la mayoría de los errores en tiempo de ejecución volviendo a escribir el código defectuoso o usando el [control de excepciones](../../language-reference/statements/try-catch-finally-statement.md)y, a continuación, volviendo a compilarlo y volver a ejecutarlo.
  
## <a name="logic-errors"></a>Errores lógicos
 Los *errores lógicos* son los que aparecen una vez que la aplicación está en uso. Suelen ser suposiciones defectuosas realizadas por el desarrollador o resultados no deseados o inesperados en respuesta a las acciones del usuario. Por ejemplo, una clave mal escrita podría proporcionar información incorrecta a un método, o puede suponer que siempre se suministra un valor válido a un método cuando no es el caso. Aunque los errores lógicos se pueden controlar mediante el [control de excepciones](../../language-reference/statements/try-catch-finally-statement.md) (por ejemplo, comprobando si un argumento es `Nothing` e iniciando una <xref:System.ArgumentNullException>), lo más habitual es que se solucionen corrigiendo el error en la lógica y volviendo a compilar la aplicación. .

## <a name="see-also"></a>Vea también

- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Conceptos básicos del depurador](/visualstudio/debugger/debugger-feature-tour)
