---
title: '&lt;tipo1&gt;&#39;&lt; TypeName&gt;&#39; debe implementar &#39;&lt; MemberName&gt;&#39; para la interfaz &#39;&lt; InterfaceName&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords: BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05e0229d0259c519d4db265c017a5040b425c79a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;tipo1&gt;&#39;&lt; TypeName&gt;&#39; debe implementar &#39;&lt; MemberName&gt;&#39; para la interfaz &#39;&lt; InterfaceName&gt;&#39;
'\<typename >' debe implementar '\<nombreDeMiembro >' para la interfaz '\<interfacename >'. Propiedad de implementación debe tener coincidente 'ReadOnly' o 'WriteOnly' especificadores.  
  
 Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento, propiedad o evento definido por la interfaz. Se deben implementar todos los miembros de la interfaz.  
  
 **Id. de error:** BC30154  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Declarar a un miembro con el mismo nombre y firma, tal como se define en la interfaz. No olvide incluir al menos la `End Function`, `End Sub`, o `End Property` instrucción.  
  
2.  Agregar un `Implements` cláusula al final de la `Function`, `Sub`, `Property`, o `Event` instrucción. Por ejemplo:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  Al implementar una propiedad, asegúrese de que `ReadOnly` o `WriteOnly` se utiliza en la misma manera que en la definición de interfaz.  
  
4.  Al implementar una propiedad, declare `Get` y `Set` procedimientos, según corresponda.  
  
## <a name="see-also"></a>Vea también  
 [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
