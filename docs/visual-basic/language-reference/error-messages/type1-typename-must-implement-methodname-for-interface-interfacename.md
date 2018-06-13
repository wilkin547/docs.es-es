---
title: '&lt;tipo1&gt;&#39;&lt;typename&gt; &#39; debe implementar &#39; &lt;methodname&gt; &#39; para la interfaz de &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: daeeab853f6a7f582542fa15ffc09ce749731d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594388"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;tipo1&gt;&#39;&lt;typename&gt; &#39; debe implementar &#39; &lt;methodname&gt; &#39; para la interfaz de &#39; &lt;interfacename&gt;&#39;
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
