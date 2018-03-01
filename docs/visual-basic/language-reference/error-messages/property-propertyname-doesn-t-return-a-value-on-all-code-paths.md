---
title: "Propiedad &#39; &lt;propertyname&gt;&#39; &#39; t devuelve un valor en todas las rutas de acceso de código"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c9ef5b2ac62412f5684cbc78ab6bebf6bc7b6752
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Propiedad &#39; &lt;propertyname&gt;&#39; &#39; t devuelve un valor en todas las rutas de acceso de código
Propiedad '\<propertyname >' no devuelve un valor en todas las rutas de código. Podría producirse una excepción de referencia nula en tiempo de ejecución al usar el resultado.  
  
 Una propiedad `Get` procedimiento tiene al menos una ruta posible en el código que no devuelve un valor.  
  
 Puede devolver un valor de una propiedad `Get` procedimiento en cualquiera de las maneras siguientes:  
  
-   Asigne el valor al nombre de propiedad y, a continuación, realizar un `Exit Property` instrucción.  
  
-   Asigne el valor al nombre de propiedad y, a continuación, realizar la `End Get` instrucción.  
  
-   Incluya el valor en un [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Si el control se transfiere a `Exit Property` o `End Get` y no ha asignado ningún valor al nombre de propiedad, el `Get` procedimiento devuelve el valor predeterminado del tipo de datos de la propiedad. Para obtener más información, vea "Comportamiento" en [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42107  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe la lógica de flujo de control y asegúrese de que asignar un valor antes de cada instrucción que genera un valor devuelto.  
  
     Es más fácil garantizar que todos los valores devueltos desde el procedimiento devuelve un valor si siempre utiliza el `Return` instrucción. Si lo hace, la última instrucción antes de `End Get` debe ser un `Return` instrucción.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)
