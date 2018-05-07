---
title: Variable &#39; &lt;variablename&gt; &#39; se usa antes de que se le ha asignado un valor
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: d314f952bd6e11adaac642ba63ed292f48cda805
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>Variable &#39; &lt;variablename&gt; &#39; se usa antes de que se le ha asignado un valor
Variable '\<variablename >' se utiliza antes de que se le ha asignado un valor. Podría producirse una excepción de referencia nula en tiempo de ejecución.  
  
 Una aplicación tiene al menos una ruta posible en el código que lee una variable antes de asignar cualquier valor a él.  
  
 Si nunca se ha asignado un valor a una variable, contiene el valor predeterminado para su tipo de datos. Para un tipo de datos de referencia, el valor predeterminado es [nada](../../../visual-basic/language-reference/nothing.md). Leer una variable de referencia que tiene un valor de `Nothing` puede producir una excepción <xref:System.NullReferenceException> en algunas circunstancias.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** bc42104 del  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe la lógica de flujo de control y asegúrese de que la variable tiene un valor válido antes de que el control se transfiere a cualquier instrucción que lo lee.  
  
-   Una manera de garantizar que la variable siempre tiene un valor válido es inicializarla como parte de su declaración. Vea "Inicialización" en [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="see-also"></a>Vea también  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Declaración de variables](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Solución de problemas de variables](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
