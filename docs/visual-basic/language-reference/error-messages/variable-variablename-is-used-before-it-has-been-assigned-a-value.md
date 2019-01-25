---
title: Variable &#39; &lt;variablename&gt; &#39; se usa antes de que se le ha asignado un valor
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: f91343e850600c9e5f4b4b4eb2126798baf3d980
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647028"
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>Variable &#39; &lt;variablename&gt; &#39; se usa antes de que se le ha asignado un valor
Variable '\<NombreDeVariable >' se utiliza antes de que se le ha asignado un valor. Podría producirse una excepción de referencia nula en tiempo de ejecución.  
  
 Una aplicación tiene al menos una ruta de acceso posibles a través de su código que lee una variable antes de asignar cualquier valor a él.  
  
 Si nunca se ha asignado un valor a una variable, contiene el valor predeterminado para su tipo de datos. Para un tipo de datos de referencia, el valor predeterminado es [Nothing](../../../visual-basic/language-reference/nothing.md). Leer una variable de referencia que tiene un valor de `Nothing` puede producir una excepción <xref:System.NullReferenceException> en algunas circunstancias.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42104  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe la lógica del flujo de control y asegúrese de que la variable tiene un valor válido antes de que el control pasa a cualquier instrucción que lo lee.  
  
-   Una manera de garantizar que la variable siempre tiene un valor válido es inicializarla como parte de su declaración. Consulte "Inicialización" en [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="see-also"></a>Vea también
- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Declaración de variables](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Solución de problemas de variables](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
