---
title: 'Cómo: Crear una variable de objeto que no haga referencia a ninguna instancia'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 320dadb61c12f3339c5328dcef31c41503892c56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352894"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Cómo: Crear una variable de objeto que no haga referencia a ninguna instancia (Visual Basic)
Puede desasociar una variable de objeto de cualquier instancia de objeto estableciéndolo en [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Para desasociar una variable de objeto de cualquier instancia de objeto  
  
- Establezca la variable en `Nothing` en una instrucción de asignación.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Programación sólida  
 Si el código intenta tener acceso a un miembro de una variable de objeto que se ha establecido en `Nothing`, se produce una <xref:System.NullReferenceException>. Si establece una variable de objeto en `Nothing` con frecuencia, o si es posible, la variable no se inicializa, es aconsejable incluir los accesos de los miembros en un bloque de `Try...Catch...Finally`.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Si usa una variable de objeto para los objetos que contienen datos confidenciales o confidenciales, puede establecer la variable en `Nothing` cuando no esté tratando activamente con uno de esos objetos. Esto reduce la posibilidad de que el código malintencionado obtenga acceso a los datos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.NullReferenceException>
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Try...Catch...Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
