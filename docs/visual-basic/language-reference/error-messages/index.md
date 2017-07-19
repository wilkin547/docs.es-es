---
title: Mensajes de error (Visual Basic) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- errors [Visual Basic]
- error messages
- trappable errors
- errors [Visual Basic], trappable
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 9f1cb93d5aaf7f90fc332594a2ca2a7cfc0c9c2f
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---
# <a name="error-messages-visual-basic"></a>Mensajes de error (Visual Basic)
Al escribir, compilar o ejecutar una aplicación de Visual Basic, pueden producirse los siguientes tipos de errores:  
  
1.  Errores en tiempo de diseño, que se producen al escribir una aplicación en Visual Studio.  
  
2.  Errores en tiempo de compilación, que se producen cuando se compila una aplicación en Visual Studio o en un símbolo del sistema.  
  
3.  Errores en tiempo de ejecución, que se producen al ejecutar una aplicación en Visual Studio o como un archivo ejecutable independiente.  
  
 Para obtener información sobre cómo solucionar un error específico, vea [Recursos adicionales para programadores de Visual Basic](../../../visual-basic/getting-started/additional-resources.md).  
  
## <a name="run-time-errors"></a>Errores en tiempo de ejecución  
 Si una aplicación de Visual Basic intenta realizar una acción que el sistema no puede ejecutar, se produce un error en tiempo de ejecución, y [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] produce un objeto `Exception`. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] puede generar errores personalizados de cualquier tipo de datos, incluidos objetos `Exception`, con el uso de la instrucción `Throw`. Una aplicación puede identificar el error y mostrar el número de error y el mensaje de una excepción detectada. Si no se detecta ningún error, la aplicación finaliza.  
  
 El código puede capturar y examinar los errores en tiempo de ejecución. Si se incluye el código que produce el error en un bloque `Try`, puede capturar cualquier error producido dentro de un bloque `Catch` coincidente. Para obtener información sobre cómo capturar errores en tiempo de ejecución y responder a ellos en el código, vea [Instrucción Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="compile-time-errors"></a>Errores en tiempo de compilación  
 Si el compilador de Visual Basic encuentra un problema en el código, se produce un error en tiempo de compilación. En el Editor de código, puede identificar fácilmente qué línea de código provocó el error porque aparece una línea ondulada debajo de la línea de código. Aparece el mensaje de error si selecciona la línea ondulada o abre la **lista de errores**, en la que también se muestran otros mensajes.  
  
 Si un identificador tiene un subrayado ondulado y aparece un subrayado corto debajo del carácter situado más a la derecha, puede generar un código auxiliar para la clase, el constructor, el método, la propiedad, el campo o la enumeración. Para más información, vea [Generar a partir del uso](https://docs.microsoft.com/visualstudio/ide/visual-csharp-intellisense#generate-from-usage).
  
 Si resuelve las advertencias del compilador de Visual Basic, puede escribir código que se ejecuta con mayor rapidez y con menos errores. Estas advertencias identifican código que puede producir errores cuando se ejecuta la aplicación. Por ejemplo, el compilador generará una advertencia cuando intente invocar un miembro de una variable de objeto sin asignar, volver de una función sin establecer el valor devuelto o ejecutar un bloque `Try` con errores en la lógica para detectar excepciones. Para más información sobre advertencias, incluidas las formas de activarlas y desactivarlas, vea [Configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).

