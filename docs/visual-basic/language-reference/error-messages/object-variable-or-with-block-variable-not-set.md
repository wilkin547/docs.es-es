---
title: Variable de objeto o de bloque With no establecida
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e1f587e194acf744b6ec9b8f1bede3acef7b753
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Variable de objeto o de bloque With no establecida
Hace referencia a una variable de objeto no válido.   Este error puede producirse por varias razones:  
  
-   Se declaró una variable sin especificar un tipo. Si se declara una variable sin especificar un tipo, el valor predeterminado es al tipo `Object`.  
  
     Por ejemplo, una variable declarada con `Dim x` serían de tipo `Object;` una variable declarada con `Dim x As String` serían de tipo `String`.  
  
    > [!TIP]
    >  El `Option Strict` no permite la declaración de tipos implícitos que da como resultado un `Object` tipo. Si se omite el tipo, se producirá un error de tiempo de compilación. Vea [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
-   Está intentando hacer referencia a un objeto que se ha establecido en`Nothing`  
  
     .  
  
-   Está intentando obtener acceso a un elemento de una variable de matriz no se declaró correctamente.  
  
     Por ejemplo, se declara una matriz como `products() As String` desencadenará el error si intenta hacer referencia a un elemento de la matriz `products(3) = "Widget"`. La matriz no tiene ningún elemento y es tratada como un objeto.  
  
-   Estás intentando tener acceso a código en un `With...End With` bloquear antes de que el bloque se ha inicializado.   A `With...End With` bloque debe inicializarse mediante la ejecución de la `With` punto de entrada de la instrucción.  
  
> [!NOTE]
>  En versiones anteriores de Visual Basic o VBA este error también se desencadena mediante la asignación de un valor a una variable sin utilizar la `Set` palabra clave (`x = "name"` en lugar de `Set x = "name"`). El `Set` palabra clave ya no es válido en Visual Basic. NET.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Establecer `Option Strict` a `On` agregando el código siguiente al principio del archivo:  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  Si no desea habilitar `Option Strict`, busque el código para las variables que se especificaron sin tipo (`Dim x` en lugar de `Dim x As String`) y agregue el tipo deseado a la declaración.  
  
3.  Asegúrese de que no se hace referencia a una variable de objeto que se ha establecido en `Nothing`.  Busque el código para la palabra clave `Nothing`y revise el código para que el objeto no está establecido en `Nothing` hasta que una vez se ha hecho referencia.  
  
4.  Asegúrese de que las variables de matriz están influenciadas antes de tener acceso a ellos. Puede asignar una dimensión cuando se crea la matriz (`Dim x(5) As String` en lugar de `Dim x() As String`), o usar el `ReDim` palabra clave que se va a establecer las dimensiones de la matriz antes de que se acceda por primera vez.  
  
5.  Asegúrese de que su `With` bloque se ha inicializado ejecutando el `With` punto de entrada de la instrucción.  
  
## <a name="see-also"></a>Vea también  
 [Declaración de variables de objeto](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [With...End With (instrucción)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
