---
title: Tipos de error (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e01ed588d284a475a537a5fcf5ca506d25ca69f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="error-types-visual-basic"></a>Tipos de error (Visual Basic)
En [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], errores (también denominado *excepciones*) se dividen en tres categorías: errores de sintaxis, errores en tiempo de ejecución y errores lógicos.  
  
## <a name="syntax-errors"></a>Errores de sintaxis  
 *Errores de sintaxis* son aquellos que aparecen mientras escribe el código. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]comprueba el código mientras se escribe en el **Editor de código** ventana y le avisa si comete un error, como se ha escrito mal una palabra o uso incorrecto de un elemento del lenguaje. Errores de sintaxis son el tipo más común de errores. Puede corregir fácilmente en el entorno de codificación en cuanto se producen.  
  
> [!NOTE]
>  El `Option Explicit` instrucción es una forma de evitar errores de sintaxis. Obliga a declarar, por anticipado, todas las variables que se usará en la aplicación. Por lo tanto, cuando esas variables se utilizan en el código, cualquier error tipográfico se detecta inmediatamente y se puede corregir.  
  
## <a name="run-time-errors"></a>Errores en tiempo de ejecución  
 *Errores en tiempo de ejecución* son aquellos que aparecen después de compilar y ejecutar el código. Fragmentos de código que puede aparecer son correctos en que tiene no hay errores de sintaxis, pero que no se ejecutará. Por ejemplo, podría escribir correctamente una línea de código para abrir un archivo. Pero si el archivo está dañado, la aplicación no puede realizar la `Open` función y deje de ejecutarse. Puede corregir la mayoría de los errores de tiempo de ejecución por volver a escribir el código defectuoso y, a continuación, volver a compilar y volver a ejecutarlo.  
  
## <a name="logic-errors"></a>Errores lógicos  
 *Errores lógicos* son aquellos que aparecen cuando la aplicación está en uso. Únicamente son mayoría de los resultados inesperada o no deseada a menudo en respuesta a las acciones del usuario. Por ejemplo, una clave mal escrita u otra influencia externa podría hacer que la aplicación deje de funcionar en los parámetros previstos, o por completo. Errores lógicos generalmente son el tipo más difícil de corregir, puesto que no queda siempre claro donde se originan.  
  
## <a name="see-also"></a>Vea también  
 [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Conceptos básicos del depurador](/visualstudio/debugger/debugger-basics)
