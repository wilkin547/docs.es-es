---
title: '&lt;tipo1&gt;&#39;&lt; TypeName&gt;&#39; debe implementar &#39;&lt; MethodName&gt;&#39; para la interfaz &#39;&lt; InterfaceName&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords: BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e803ec7d0054f2fa1b9ed2a731fd30c9c3060468
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;tipo1&gt;&#39;&lt; TypeName&gt;&#39; debe implementar &#39;&lt; MethodName&gt;&#39; para la interfaz &#39;&lt; InterfaceName&gt;&#39;
Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento definido por la interfaz. Se deben implementar todos los miembros de la interfaz.  
  
 **Id. de error:** BC30149  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Declare un procedimiento con el mismo nombre y firma, tal como se define en la interfaz. No olvide incluir al menos la `End Function` o `End Sub` instrucción.  
  
2.  Agregar un `Implements` cláusula al final de la `Function` o `Sub` instrucción. Por ejemplo:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
