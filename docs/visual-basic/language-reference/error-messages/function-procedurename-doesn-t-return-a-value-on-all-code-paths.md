---
title: "Función &#39; &lt;nombreProcedimiento&gt;&#39; &#39; t devuelve un valor en todas las rutas de acceso de código"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5244d97a79f2450f44fe05f63510369914375912
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Función &#39; &lt;nombreProcedimiento&gt;&#39; &#39; t devuelve un valor en todas las rutas de acceso de código
Función '\<nombreProcedimiento >' no devuelve un valor en todas las rutas de código. ¿Falta una instrucción 'Return'?  
  
 A `Function` procedimiento tiene al menos una ruta posible en el código que no devuelve un valor.  
  
 Puede devolver un valor desde un `Function` procedimiento en cualquiera de las maneras siguientes:  
  
-   Incluya el valor en un [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Asigne el valor para el `Function` procedimiento asigne un nombre y, a continuación, realizar un `Exit Function` instrucción.  
  
-   Asigne el valor para el `Function` procedimiento asigne un nombre y, a continuación, realizar la `End Function` instrucción.  
  
 Si el control se transfiere a `Exit Function` o `End Function` y no ha asignado ningún valor para el nombre del procedimiento, el procedimiento devuelve el valor predeterminado del tipo de datos devuelto. Para obtener más información, vea "Comportamiento" en [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42105  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe la lógica de flujo de control y asegúrese de que asignar un valor antes de cada instrucción que genera un valor devuelto.  
  
     Es más fácil garantizar que todos los valores devueltos desde el procedimiento devuelve un valor si siempre utiliza el `Return` instrucción. Si lo hace, la última instrucción antes de `End Function` debe ser un `Return` instrucción.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de función](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Página Compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
