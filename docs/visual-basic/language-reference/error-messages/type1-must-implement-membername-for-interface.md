---
title: '&lt;tipo1&gt;&#39;&lt;typename&gt; &#39; debe implementar &#39; &lt;membername&gt; &#39; para la interfaz &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 14e7bd199215764676a4b563eafc68bd6dabadc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574747"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;tipo1&gt;&#39;&lt;typename&gt; &#39; debe implementar &#39; &lt;membername&gt; &#39; para la interfaz &#39; &lt;interfacename&gt;&#39;
'\<typename >' debe implementar '\<membername >' para la interfaz '\<interfacename >'. Propiedad de implementación debe tener coincidentes 'ReadOnly' o 'WriteOnly' especificadores.  
  
 Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento, propiedad o evento definido por la interfaz. Se deben implementar todos los miembros de la interfaz.  
  
 **Identificador de error:** BC30154  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Declarar a un miembro con el mismo nombre y firma, tal como se define en la interfaz. No olvide incluir al menos el `End Function`, `End Sub`, o `End Property` instrucción.  
  
2.  Agregar un `Implements` cláusula al final de la `Function`, `Sub`, `Property`, o `Event` instrucción. Por ejemplo:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  Al implementar una propiedad, asegúrese de que `ReadOnly` o `WriteOnly` se usa en la misma forma que la definición de interfaz.  
  
4.  Al implementar una propiedad, declare `Get` y `Set` procedimientos, según corresponda.  
  
## <a name="see-also"></a>Vea también
- [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
