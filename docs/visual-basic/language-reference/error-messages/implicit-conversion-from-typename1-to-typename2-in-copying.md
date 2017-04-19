---
title: "Conversión implícita de &quot;&lt;NombreTipo1&gt;&quot;to&quot;&lt;en NombreTipo2&gt;&quot;en copiar el valor del parámetro &quot;ByRef&quot; &quot;&lt;parametername&gt;&quot; en el argumento correspondiente. | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
dev_langs:
- VB
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
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
ms.openlocfilehash: e397241aab78e17ea4efde0ea682d0e237fb8f8a
ms.lasthandoff: 03/13/2017

---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>Conversión implícita de '&lt;NombreTipo1&gt;'to'&lt;en NombreTipo2&gt;'en copiar el valor del parámetro 'ByRef' '&lt;parametername&gt;' en el argumento correspondiente.
Se llama a un procedimiento con un [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argumento de un tipo diferente de su parámetro correspondiente.  
  
 Si se pasa un argumento `ByRef`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia. En tal caso, cuando el procedimiento vuelve, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] , a continuación, debe copiar el valor de la variable local en el argumento en el código de llamada.  
  
 Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión. Pero si los tipos son diferentes, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] debe convertir en ambas direcciones. Dado que no se puede utilizar `CType` o cualquiera de las demás palabras clave de conversión en un argumento de procedimiento o parámetro, dicha conversión siempre es implícito.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC41999  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si es posible, utilice un argumento de llamada del mismo tipo como el parámetro de procedimiento, por lo que [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no es necesario realizar ninguna conversión.  
  
-   Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) en lugar de `ByRef`.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Pasar argumentos por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
