---
title: Variable &quot;&lt;variablename&gt;&quot; se utiliza antes de que se le ha asignado un valor | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
dev_langs:
- VB
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7ad1f392fae2f90e366277b7b531d96011648866
ms.lasthandoff: 03/13/2017

---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>Variable '&lt;variablename&gt;' se utiliza antes de que se le ha asignado un valor
Variable '\<variablename >' se utiliza antes de que se le ha asignado un valor. Podría producirse una excepción de referencia nula en tiempo de ejecución.  
  
 Una aplicación tiene al menos una ruta posible en su código que lee una variable antes de que se asigne cualquier valor a él.  
  
 Si nunca se ha asignado un valor a una variable, contiene el valor predeterminado para su tipo de datos. Para un tipo de datos de referencia, el valor predeterminado es [nada](../../../visual-basic/language-reference/nothing.md). Leer una variable de referencia que tiene un valor de `Nothing` puede provocar un <xref:System.NullReferenceException>en algunas circunstancias.</xref:System.NullReferenceException>  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o tratar las advertencias como errores, vea [configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** bc42104 del  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe la lógica del flujo de control y asegúrese de que la variable tiene un valor válido antes de que el control se transfiere a cualquier instrucción que lo lee.  
  
-   Una manera de garantizar que la variable siempre tiene un valor válido es inicializarla como parte de su declaración. Vea "Inicialización" en [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="see-also"></a>Vea también  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Declaración de variable](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Solución de problemas de variables](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
