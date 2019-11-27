---
title: 'Cómo: Declarar una estructura'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 41d2d03064dea703909218de56feb863526c220b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350008"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Cómo: Declarar una estructura (Visual Basic)
Una declaración de estructura se inicia con la [instrucción Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)y finaliza con la instrucción `End Structure`. Entre estas dos instrucciones debe declarar al menos un *elemento*. Los elementos pueden ser de cualquier tipo de datos, pero al menos uno debe ser una variable no compartida o un evento no personalizado no compartido.  
  
 No se puede inicializar ninguno de los elementos de la estructura en la declaración de la estructura. Cuando se declara una variable para que sea de un tipo de estructura, se asignan valores a los elementos accediendo a ellas a través de la variable.  
  
 Para obtener una explicación de las diferencias entre las estructuras y las clases, vea [estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Para fines de demostración, considere una situación en la que desea realizar un seguimiento del nombre de un empleado, la extensión de teléfono y el salario. Una estructura le permite hacer esto en una sola variable.  
  
### <a name="to-declare-a-structure"></a>Para declarar una estructura  
  
1. Cree las instrucciones de inicio y finalización de la estructura.  
  
     Puede especificar el nivel de acceso de una estructura mediante la palabra clave [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)o [Private](../../../../visual-basic/language-reference/modifiers/private.md) , o puede dejar que se `Public`de forma predeterminada.  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. Agregue elementos al cuerpo de la estructura.  
  
     Una estructura debe tener al menos un elemento. Debe declarar cada elemento y especificar un nivel de acceso para él. Si usa la [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) sin palabras clave, el valor predeterminado de accesibilidad es `Public`.  
  
    ```vb  
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
  
     El campo `salary` del ejemplo anterior es `Private`, lo que significa que es inaccesible fuera de la estructura, incluso desde la clase contenedora. Sin embargo, el procedimiento `giveRaise` es `Public`, por lo que se puede llamar desde fuera de la estructura. Del mismo modo, puede generar el evento `salaryReviewTime` desde fuera de la estructura.  
  
     Además de las variables, los procedimientos de `Sub` y los eventos, también puede definir constantes, procedimientos de `Function` y propiedades en una estructura. Puede designar como máximo una propiedad como la *propiedad predeterminada*, siempre que tome al menos un argumento. Puede controlar un evento con un procedimiento [compartido](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub`. Para obtener más información, vea [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
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
