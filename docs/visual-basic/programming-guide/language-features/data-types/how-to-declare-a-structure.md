---
title: Procedimiento Declarar una estructura (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: bfed5c969466cb427e6c94d39bfcc6a6e007c320
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672050"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Procedimiento Declarar una estructura (Visual Basic)
Comenzar una declaración structure con la [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md), y finaliza con la `End` `Structure` instrucción. Entre estas dos instrucciones debe declarar al menos una *elemento*. Los elementos pueden ser de cualquier tipo de datos, pero al menos uno debe ser una variable no compartida o un evento no compartido, no personalizado.  
  
 No se puede inicializar cualquiera de los elementos de estructura en la declaración de estructura. Cuando se declara una variable para que sea un tipo de estructura, asignar valores a los elementos mediante el acceso a ellos a través de la variable.  
  
 Para obtener una explicación de las diferencias entre clases y estructuras, vea [estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Para fines de demostración, considere una situación donde desea realizar un seguimiento de nombre, extensión telefónica y salario del empleado. Una estructura le permite hacer esto en una única variable.  
  
### <a name="to-declare-a-structure"></a>Para declarar una estructura  
  
1.  Cree el comienzo y finalización de instrucciones para la estructura.  
  
     Puede especificar el nivel de acceso de una estructura mediante la [pública](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave, o puede dejar de forma predeterminada `Public`.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  Agregar elementos al cuerpo de la estructura.  
  
     Una estructura debe tener al menos un elemento. Debe declarar todos los elementos y especificar un nivel de acceso para él. Si usas el [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) sin palabras clave, valores predeterminados de la accesibilidad a `Public`.  
  
    ```  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     El `salary` campo en el ejemplo anterior es `Private`, lo que significa que no es accesible fuera de la estructura, incluso desde la clase contenedora. Sin embargo, el `giveRaise` procedimiento es `Public`, por lo que se puede llamar desde fuera de la estructura. De forma similar, puede elevar la `salaryReviewTime` evento desde fuera de la estructura.  
  
     Además de las variables, `Sub` procedimientos y eventos, también puede definir constantes, `Function` procedimientos y propiedades en una estructura. Puede designar como máximo una propiedad como el *propiedad predeterminada*, siempre que tarda al menos un argumento. Puede controlar un evento con un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedimiento. Para obtener más información, vea [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Vea también
- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Variables de estructura](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Tipo de datos definido por el usuario](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
