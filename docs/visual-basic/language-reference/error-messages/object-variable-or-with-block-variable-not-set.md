---
title: Variable de objeto o variable de bloque With no establecida | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID91
dev_langs:
- VB
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 820ef0115a6a27d77f10f4e41d95576bbd79bfa3
ms.lasthandoff: 03/13/2017

---
# <a name="object-variable-or-with-block-variable-not-set"></a>Variable de objeto o de bloque With no establecida
Se hace referencia una variable de objeto no válido.   Este error puede producirse por varias razones:  
  
-   Se ha declarado una variable sin especificar un tipo. Si se declara una variable sin especificar un tipo, los valores predeterminados para escribir `Object`.  
  
     Por ejemplo, una variable declarada con `Dim x` serían de tipo `Object;` una variable declarada con `Dim x As String` serían de tipo `String`.  
  
    > [!TIP]
    >  El `Option Strict` instrucción impide tipos implícitos que da como resultado un `Object` tipo. Si se omite el tipo, se producirá un error de tiempo de compilación. Consulte [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
-   Está intentando hacer referencia a un objeto que se ha establecido en`Nothing`  
  
     .  
  
-   Está intentando obtener acceso a un elemento de una variable de matriz no se declaró correctamente.  
  
     Por ejemplo, se declara una matriz como `products() As String` desencadenará el error si se intenta hacer referencia a un elemento de la matriz `products(3) = "Widget"`. La matriz no tiene elementos y se trata como un objeto.  
  
-   Está intentando código de acceso dentro de un `With...End With` bloquear antes de que se ha inicializado el bloque.   Un `With...End With` se debe inicializar ejecutando el `With` punto de entrada de la instrucción.  
  
> [!NOTE]
>  En versiones anteriores de Visual Basic o VBA, este error también se desencadenó asignando un valor a una variable sin utilizar la `Set` palabra clave (`x = "name"` en lugar de `Set x = "name"`). El `Set` ya no es válido en Visual Basic .net (palabra clave).  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Establecer `Option Strict` a `On` agregando el siguiente código al principio del archivo:  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  Si no desea habilitar `Option Strict`, busque el código para las variables que se especificaron sin tipo (`Dim x` en lugar de `Dim x As String`) y agregue el tipo deseado a la declaración.  
  
3.  Asegúrese de que no está haciendo referencia a una variable de objeto que se ha establecido en `Nothing`.  Busque el código para la palabra clave `Nothing`y revise el código para que el objeto no está establecido en `Nothing` hasta que una vez se ha hecho referencia.  
  
4.  Asegúrese de que las variables de matriz están influenciadas antes de tener acceso a ellos. Puede asignar una dimensión cuando se crea la matriz (`Dim x(5) As String` en lugar de `Dim x() As String`), o utilizar el `ReDim` (palabra clave) para establecer las dimensiones de la matriz antes de que se acceda por primera vez.  
  
5.  Asegúrese de que su `With` bloque se ha inicializado ejecutando el `With` punto de entrada de la instrucción.  
  
## <a name="see-also"></a>Vea también  
 [Declaración de Variable de objeto](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [With...End With (instrucción)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
