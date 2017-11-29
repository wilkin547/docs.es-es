---
title: "Conversión implícita de &#39; &lt;typename1&gt;&#39; a &#39;&lt; nombredetipo2&gt;&#39; para copiar el valor de &#39; ByRef &#39; parámetro &#39; &lt;parametername&gt;&#39; atrás en el argumento correspondiente."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords: BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e858b475a816a35d18822643de5a273abe28562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>Conversión implícita de &#39; &lt;typename1&gt;&#39; a &#39;&lt; nombredetipo2&gt;&#39; para copiar el valor de &#39; ByRef &#39; parámetro &#39; &lt;parametername&gt;&#39; atrás en el argumento correspondiente.
Se llama a un procedimiento con un [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argumento de un tipo diferente que el del parámetro correspondiente.  
  
 Si se pasa un argumento `ByRef`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia. En tal caso, cuando el procedimiento vuelve, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] debe copiar el valor de la variable local de nuevo en el argumento en el código de llamada.  
  
 Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión. Pero si los tipos son diferentes, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] se debe convertir en ambas direcciones. Dado que no se puede utilizar `CType` o cualquiera de las demás palabras clave de conversión en un argumento de procedimiento o parámetro, este tipo de conversión siempre es implícito.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC41999  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si es posible, use un argumento de llamada del mismo tipo, como el parámetro de procedimiento, por lo que [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no necesita hacer ninguna conversión.  
  
-   Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) en lugar de `ByRef`.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Argumentos y parámetros de procedimiento](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Paso de argumentos por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
