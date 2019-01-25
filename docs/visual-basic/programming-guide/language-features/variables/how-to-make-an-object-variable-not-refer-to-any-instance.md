---
title: Procedimiento Crea un objeto de Variable no hacen referencia a cualquier instancia (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 1199fa4e126c3d15e56a6c895aecf6afcae17f0b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678517"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Procedimiento Crea un objeto de Variable no hacen referencia a cualquier instancia (Visual Basic)
Puede desasociar una variable de objeto de cualquier instancia de objeto si se establece en [nada](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Para desasociar una variable de objeto de cualquier instancia de objeto  
  
-   Establezca la variable en `Nothing` en una instrucción de asignación.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Programación sólida  
 Si el código intenta tener acceso a un miembro de una variable de objeto que se ha establecido en `Nothing`, un <xref:System.NullReferenceException> se produce. Si establece una variable de objeto en `Nothing` con frecuencia, o si es posible que la variable no se ha inicializado, es una buena idea incluir accesos de miembros en un `Try...Catch...Finally` bloque.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Si usa una variable de objeto para objetos que contienen datos confidenciales, puede establecer la variable `Nothing` cuando no activamente trabaja con uno de esos objetos. Esto reduce la posibilidad de programas malintencionados obtengan acceso a los datos.  
  
## <a name="see-also"></a>Vea también
- <xref:System.NullReferenceException>
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Try...Catch...Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Solucionar problemas de excepciones: System.NullReferenceException](https://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
