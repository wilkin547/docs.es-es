---
title: Procedimiento Declaración de estructuras
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: bffdc5974eff6b71e0abc4780a61aa300769eed6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058552"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Cómo: Declarar una estructura (Visual Basic)

Comienza una declaración de estructura con la [instrucción Structure](../../../language-reference/statements/structure-statement.md)y la finaliza con la `End Structure` instrucción. Entre estas dos instrucciones debe declarar al menos un *elemento*. Los elementos pueden ser de cualquier tipo de datos, pero al menos uno debe ser una variable no compartida o un evento no personalizado no compartido.  
  
 No se puede inicializar ninguno de los elementos de la estructura en la declaración de la estructura. Cuando se declara una variable para que sea de un tipo de estructura, se asignan valores a los elementos accediendo a ellas a través de la variable.  
  
 Para obtener una explicación de las diferencias entre las estructuras y las clases, vea [estructuras y clases](structures-and-classes.md).  
  
 Para fines de demostración, considere una situación en la que desea realizar un seguimiento del nombre de un empleado, la extensión de teléfono y el salario. Una estructura le permite hacer esto en una sola variable.  
  
### <a name="to-declare-a-structure"></a>Para declarar una estructura  
  
1. Cree las instrucciones de inicio y finalización de la estructura.  
  
     Puede especificar el nivel de acceso de una estructura mediante la palabra clave [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)o [Private](../../../language-reference/modifiers/private.md) , o puede dejar que sea el valor predeterminado `Public` .  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. Agregue elementos al cuerpo de la estructura.  
  
     Una estructura debe tener al menos un elemento. Debe declarar cada elemento y especificar un nivel de acceso para él. Si usa la [instrucción Dim](../../../language-reference/statements/dim-statement.md) sin palabras clave, el valor predeterminado de accesibilidad es `Public` .  
  
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
  
     El `salary` campo del ejemplo anterior es `Private` , lo que significa que es inaccesible fuera de la estructura, incluso desde la clase contenedora. Sin embargo, el `giveRaise` procedimiento es `Public` , por lo que se puede llamar desde fuera de la estructura. Del mismo modo, puede generar el `salaryReviewTime` evento desde fuera de la estructura.  
  
     Además de las variables, `Sub` procedimientos y eventos, también puede definir constantes, `Function` procedimientos y propiedades en una estructura. Puede designar como máximo una propiedad como la *propiedad predeterminada*, siempre que tome al menos un argumento. Puede controlar un evento con un procedimiento [compartido](../../../language-reference/modifiers/shared.md) `Sub` . Para obtener más información, vea [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](../procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Vea también

- [Tipo de datos](index.md)
- [Tipos de datos básicos](elementary-data-types.md)
- [Tipos de datos compuestos](composite-data-types.md)
- [Tipos de valor y tipos de referencia](value-types-and-reference-types.md)
- [Estructuras](structures.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Variables de estructura](structure-variables.md)
- [Estructuras y otros elementos de programación](structures-and-other-programming-elements.md)
- [Estructuras y clases](structures-and-classes.md)
- [Tipo de datos definido por el usuario](../../../language-reference/data-types/user-defined-data-type.md)
