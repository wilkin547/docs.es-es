---
title: Conversión implícita de &#39; &lt;typename1&gt; &#39; a &#39; &lt;typename2&gt; &#39; copiar el valor de &#39;ByRef&#39; parámetro &#39; &lt; ParameterName&gt; &#39; en el argumento correspondiente.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 9f05a5fbcbef828b4ffa920d8cade475cedb64d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537248"
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>Conversión implícita de &#39; &lt;typename1&gt; &#39; a &#39; &lt;typename2&gt; &#39; copiar el valor de &#39;ByRef&#39; parámetro &#39; &lt; ParameterName&gt; &#39; en el argumento correspondiente.
Se llama a un procedimiento con un [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argumento de un tipo diferente del parámetro correspondiente.  
  
 Si se pasa un argumento `ByRef`, Visual Basic a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia. En tal caso, cuando el procedimiento vuelve, Visual Basic debe, a continuación, copiar el valor de la variable local en el argumento en el código de llamada.  
  
 Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión. Pero si los tipos son diferentes, Visual Basic debe convertir en ambas direcciones. Dado que no se puede usar `CType` o cualquiera de las otras palabras clave de conversión en un argumento de procedimiento o parámetro, dicha conversión siempre es implícito.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC41999  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si es posible, utilice un argumento de llamada del mismo tipo como el parámetro de procedimiento, por lo que no es necesario realizar ninguna conversión de Visual Basic.  
  
-   Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) en lugar de `ByRef`.  
  
## <a name="see-also"></a>Vea también
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Argumentos y parámetros de procedimiento](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Paso de argumentos por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
