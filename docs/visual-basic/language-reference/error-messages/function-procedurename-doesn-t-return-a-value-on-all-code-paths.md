---
title: "Función &quot;&lt;nombreProcedimiento&gt;&quot; no devuelve un valor en todas las rutas de código | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
dev_langs:
- VB
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
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
ms.openlocfilehash: 288fdf7c4845b20283681d9eb3504ac314f1ddd2
ms.lasthandoff: 03/13/2017

---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Función '&lt;nombreProcedimiento&gt;' no devuelve un valor en todas las rutas de código
Función '\<nombreProcedimiento >' no devuelve un valor en todas las rutas de código. ¿Falta una instrucción 'Return'?  
  
 Un `Function` procedimiento tiene al menos una ruta posible en el código que no devuelve un valor.  
  
 Puede devolver un valor desde un `Function` procedimiento en cualquiera de las maneras siguientes:  
  
-   Incluya el valor en un [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Asigne el valor a la `Function` procedimiento el nombre y, a continuación, realizar una `Exit Function` instrucción.  
  
-   Asigne el valor a la `Function` procedimiento el nombre y, a continuación, realizar la `End Function` instrucción.  
  
 Si el control se transfiere a `Exit Function` o `End Function` y no ha asignado ningún valor para el nombre del procedimiento, el procedimiento devuelve el valor predeterminado del tipo de datos devuelto. Para obtener más información, vea "Comportamiento" en [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o tratar las advertencias como errores, vea [configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42105  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe la lógica del flujo de control y asegúrese de que asignar un valor antes de cada instrucción que genera un valor devuelto.  
  
     Es más fácil garantizar que cada retorno del procedimiento devuelve un valor si siempre utiliza el `Return` instrucción. Si lo hace, la última instrucción antes de `End Function` debe ser un `Return` instrucción.  
  
## <a name="see-also"></a>Vea también  
 [Function (procedimientos)](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Página Compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
