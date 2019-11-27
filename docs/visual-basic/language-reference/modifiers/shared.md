---
title: Shared
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: 98fa25d2283408dfb80e82fbc620a1b284e5c530
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349127"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
Especifica que uno o varios elementos de programación declarados están asociados a una clase o estructura de gran tamaño, y no a una instancia específica de la clase o estructura.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="when-to-use-shared"></a>Cuándo usar Shared  
 Compartir un miembro de una clase o estructura lo pone a disposición de todas las instancias, en lugar de ser no *compartidas*, donde cada instancia conserva su propia copia. Esto resulta útil, por ejemplo, si el valor de una variable se aplica a toda la aplicación. Si declara que la variable es `Shared`, todas las instancias acceden a la misma ubicación de almacenamiento y, si una instancia cambia el valor de la variable, todas las instancias acceden al valor actualizado.  
  
 El uso compartido no modifica el nivel de acceso de un miembro. Por ejemplo, un miembro de clase puede ser compartido y privado (accesible solo desde dentro de la clase), o no compartido y público. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Reglas  
  
- **Contexto de declaración.** Solo se puede usar `Shared` en un nivel de módulo. Esto significa que el contexto de la declaración de un elemento `Shared` debe ser una clase o estructura, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.  
  
- **Modificadores combinados.** No se puede especificar `Shared` junto con [invalidaciones](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)o [static](../../../visual-basic/language-reference/modifiers/static.md) en la misma declaración.  
  
- **Acceso a.** Puede tener acceso a un elemento compartido si lo califica con su nombre de clase o estructura, no con el nombre de variable de una instancia específica de su clase o estructura. No es necesario crear una instancia de una clase o estructura para tener acceso a sus miembros compartidos.  
  
     En el ejemplo siguiente se llama al procedimiento compartido <xref:System.Double.IsNaN%2A> expuesto por la estructura <xref:System.Double>.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
- **Uso compartido implícito.** No se puede usar el modificador `Shared` en una [instrucción const](../../../visual-basic/language-reference/statements/const-statement.md), pero las constantes se comparten implícitamente. Del mismo modo, no puede declarar un miembro de un módulo o una interfaz que se `Shared`, pero se comparten implícitamente.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Discos.** Una variable o evento compartido se almacena en la memoria solo una vez, independientemente del número de instancias que cree de su clase o estructura. De forma similar, un procedimiento compartido o una propiedad solo contiene un conjunto de variables locales.  
  
- **Obtener acceso a través de una variable de instancia.** Es posible obtener acceso a un elemento compartido si se califica con el nombre de una variable que contiene una instancia específica de su clase o estructura. Aunque esto suele funcionar según lo esperado, el compilador genera un mensaje de advertencia y hace que el acceso se realice a través del nombre de la clase o la estructura en lugar de la variable.  
  
- **Obtener acceso a través de una expresión de instancia.** Si obtiene acceso a un elemento compartido a través de una expresión que devuelve una instancia de su clase o estructura, el compilador realiza el acceso a través del nombre de la clase o la estructura en lugar de evaluar la expresión. Esto produce resultados inesperados si desea que la expresión realice otras acciones, así como para devolver la instancia. En el ejemplo siguiente se ilustra esto.  
  
    ```vb
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     En el ejemplo anterior, el compilador genera un mensaje de advertencia ambas veces el código tiene acceso a la variable compartida `total` a través de una instancia de. En cada caso, realiza el acceso directamente a través de la clase `shareTotal` y no hace uso de ninguna instancia. En el caso de la llamada prevista al procedimiento `returnClass`, esto significa que no genera ni siquiera una llamada a `returnClass`, por lo que no se realiza la acción adicional de mostrar "función returnClass () llamada".  
  
 El modificador `Shared` se puede utilizar en los contextos siguientes:  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Static](../../../visual-basic/language-reference/modifiers/static.md)
- [Duración en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
