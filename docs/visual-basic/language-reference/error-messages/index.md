---
title: "Mensajes de error (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "mensajes de error"
  - "errores [Visual Basic]"
  - "errores [Visual Basic], interceptables"
  - "errores interceptables"
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Mensajes de error (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando escribe, compila, o se ejecuta una aplicación de Visual Basic, los siguientes tipos de pueden producir errores:  
  
1.  Errores en tiempo de diseño, que aparecen cuando se escribe una aplicación en Visual Studio.  
  
2.  Errores en tiempo de compilación, que aparecen cuando se compila una aplicación en Visual Studio o en un símbolo del sistema.  
  
3.  Errores en tiempo de ejecución, que aparecen cuando se ejecuta una aplicación en Visual Studio o como un archivo independiente.  
  
 Para obtener información sobre cómo solucionar un error específico, vea [Recursos adicionales para programadores de Visual Basic](../../../visual-basic/getting-started/additional-resources.md).  
  
## Errores en tiempo de ejecución  
 Si los intentos de una aplicación de Visual Basic para realizar una acción que el sistema no puede ejecutar, un error en tiempo de ejecución aparecen, y los tiros de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] un objeto de `Exception` .  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] puede generar errores personalizados de cualquier tipo de datos, incluidos los objetos `Exception`, mediante la instrucción `Throw`.  Una aplicación puede identificar el error muestra el número y el mensaje de error de una excepción detectada.  Si no se captura el error, la aplicación finaliza.  
  
 El código puede interceptar y examinar errores en tiempo de ejecución.  Si agrega el código que produce el error en un bloque de `Try` , puede detectar cualquier error se produce dentro de un bloque coincidentes de `Catch` .  Para obtener información sobre cómo interceptar los errores en tiempo de ejecución y responder a ellos en el código, vea [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Errores en tiempo de compilación  
 Si el compilador de Visual Basic encuentra un problema en el código, produce un error de compilación.  En el editor de código, puede identificar qué línea de código provocó el error ya que aparece una línea ondulada debajo esa línea de código.  El mensaje de error si señala al subrayado ondulado o abra **Lista de errores**, que también muestra otros mensajes.  
  
 Si un identificador tiene un subrayado ondulado y un subrayado corto debajo del carácter derecha, puede generar un código auxiliar para la clase, el constructor, el método, la propiedad, el campo o enum.  Para obtener más información, vea [Generar a partir del uso](/visual-cpp/misc/generate-from-usage).  
  
 Resolver las advertencias del compilador de Visual Basic, es posible que pueda escribir código que se ejecuta más rápidamente y tienen menos errores.  Estas advertencias identifican código que puede producir errores cuando se ejecuta la aplicación.  Por ejemplo, el compilador advierte si intenta invocar un miembro de una variable de objeto no asignada, volver de una función sin establecer el valor devuelto, o ejecutar un bloque de `Try` con errores en la lógica para detectar excepciones.  Para obtener más información sobre las advertencias, incluso cómo activarlas y desactivarlas, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).