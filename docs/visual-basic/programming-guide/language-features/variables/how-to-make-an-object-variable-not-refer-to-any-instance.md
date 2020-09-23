---
title: Procedimiento para crear una variable de objeto que no haga referencia a ninguna instancia
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 61bb06401ebd1e479c9256a80a12d87240831063
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080260"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Cómo: Crear una variable de objeto que no haga referencia a ninguna instancia (Visual Basic)

Puede desasociar una variable de objeto de cualquier instancia de objeto estableciéndolo en [Nothing](../../../language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Para desasociar una variable de objeto de cualquier instancia de objeto  
  
- Establezca la variable `Nothing` en en una instrucción de asignación.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Programación sólida  

 Si el código intenta obtener acceso a un miembro de una variable de objeto que se ha establecido en `Nothing` , <xref:System.NullReferenceException> se produce una. Si establece una variable de objeto con `Nothing` frecuencia, o si es posible, la variable no se inicializa, es aconsejable incluir los accesos de los miembros en un `Try...Catch...Finally` bloque.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  

 Si usa una variable de objeto para los objetos que contienen datos confidenciales o confidenciales, puede establecer la variable en `Nothing` cuando no esté tratando activamente con uno de esos objetos. Esto reduce la posibilidad de que el código malintencionado obtenga acceso a los datos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.NullReferenceException>
- [Variables de objeto](object-variables.md)
- [Asignación de variables de objeto](object-variable-assignment.md)
- [Nothing](../../../language-reference/nothing.md)
- [Try... Detectar... Finally (instrucción)](../../../language-reference/statements/try-catch-finally-statement.md)
