---
title: "Propiedad &quot;&lt;propertyname&gt;&quot; no devuelve un valor en todas las rutas de código | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
dev_langs:
- VB
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
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
ms.openlocfilehash: e7c94d827761ad26d517b44a06734c5db4480a62
ms.lasthandoff: 03/13/2017

---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Propiedad '&lt;propertyname&gt;' no devuelve un valor en todas las rutas de código
Propiedad '\<propertyname >' no devuelve un valor en todas las rutas de código. Podría producirse una excepción de referencia nula en tiempo de ejecución al usar el resultado.  
  
 Una propiedad `Get` procedimiento tiene al menos una ruta posible en el código que no devuelve un valor.  
  
 Puede devolver un valor de una propiedad `Get` procedimiento en cualquiera de las maneras siguientes:  
  
-   Asigne el valor al nombre de propiedad y, a continuación, realizar una `Exit Property` instrucción.  
  
-   Asigne el valor al nombre de propiedad y, a continuación, realizar la `End Get` instrucción.  
  
-   Incluya el valor en un [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Si el control se transfiere a `Exit Property` o `End Get` y no ha asignado ningún valor al nombre de propiedad, el `Get` procedimiento devuelve el valor predeterminado de la propiedad tipo de datos. Para obtener más información, vea "Comportamiento" en [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o tratar las advertencias como errores, vea [configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42107  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe la lógica del flujo de control y asegúrese de que asignar un valor antes de cada instrucción que genera un valor devuelto.  
  
     Es más fácil garantizar que cada retorno del procedimiento devuelve un valor si siempre utiliza el `Return` instrucción. Si lo hace, la última instrucción antes de `End Get` debe ser un `Return` instrucción.  
  
## <a name="see-also"></a>Vea también  
 [Property (procedimientos)](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)
