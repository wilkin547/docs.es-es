---
title: "Variable &#39; &lt;variablename&gt;&#39; oculta una variable en un bloque de inclusión"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2af570cd002b4be4e15a7c03b0ffc2ff84ba3982
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a>Variable &#39; &lt;variablename&gt;&#39; oculta una variable en un bloque de inclusión
Una variable incluida en un bloque tiene el mismo nombre que otra variable local.  
  
 **Id. de error:** BC30616  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambiar el nombre de la variable del bloque contenedor para que no sea igual que cualquier otra variable local. Por ejemplo:  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   Una causa común de este error es el uso de `Catch e As Exception` dentro de un controlador de eventos. Si este es el caso, el nombre del `Catch` variable de bloque `ex` en lugar de `e`.  
  
-   Otra fuente común de este error es un intento para tener acceso a una variable local declarada dentro de un `Try` bloquear en otro `Catch` bloque. Para corregir este error, declare la variable fuera de la `Try...Catch...Finally` estructura.  
  
## <a name="see-also"></a>Vea también  
 [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Declaración de variables](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
