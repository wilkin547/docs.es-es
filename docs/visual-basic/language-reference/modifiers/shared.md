---
title: Shared (Visual Basic)
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
ms.openlocfilehash: b76d999bfe3f7ae5205cb9486e040c1d6191b78c
ms.sourcegitcommit: dc02d7d95f1e3efcc7166eaf431b0ec0dc9d8dca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2018
ms.locfileid: "37143536"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
Especifica que uno o varios elementos de programación declarados están asociados con una clase o estructura en general y no con una instancia específica de la clase o estructura.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="when-to-use-shared"></a>Cuándo usar compartido  
 Compartir un miembro de una clase o estructura pone a disposición de todas las instancias, en lugar de *no compartido*, donde cada instancia mantiene su propia copia. Esto es útil, por ejemplo, si el valor de una variable se aplica a toda la aplicación. Si esa variable se declara `Shared`y, a continuación, todas las instancias a la misma ubicación de almacenamiento y, si una instancia cambia el valor de la variable, todas las instancias de tener acceso al valor actualizado.  
  
 Uso compartido no modifica el nivel de acceso de un miembro. Por ejemplo, se puede compartir un miembro de clase y privado (accesible únicamente desde dentro de la clase), o no compartido y público. Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de declaración.** Solo se puede usar `Shared` en un nivel de módulo. Esto significa que el contexto de declaración de un `Shared` elemento debe ser una clase o estructura y no puede ser un archivo de código fuente, el espacio de nombres o el procedimiento.  
  
-   **Modificadores combinados.** No puede especificar `Shared` junto con [invalida](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), o [ Estático](../../../visual-basic/language-reference/modifiers/static.md) en la misma declaración.  
  
-   **Acceso a.** Tener acceso a un elemento compartido calificando con su nombre de clase o estructura, no con el nombre de variable de una instancia específica de su clase o estructura. Incluso no es necesario crear una instancia de una clase o estructura para tener acceso a sus miembros compartidos.  
  
     En el ejemplo siguiente se llama al procedimiento compartido <xref:System.Double.IsNaN%2A> expuestos por el <xref:System.Double> estructura.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **Uso compartido implícito.** No puede usar el `Shared` modificador en un [instrucción Const](../../../visual-basic/language-reference/statements/const-statement.md), pero las constantes se comparten de forma implícita. De forma similar, no se puede declarar un miembro de un módulo o una interfaz como `Shared`, pero se compartían de forma implícita.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Almacenamiento.** Una variable compartida o un evento se almacena en memoria solo una vez, independientemente del número de instancias que cree de su clase o estructura. De forma similar, un procedimiento compartido o una propiedad contiene sólo un conjunto de variables locales.  
  
-   **Acceso mediante una Variable de instancia.** Es posible tener acceso a un elemento compartido calificando el nombre de una variable que contiene una instancia específica de su clase o estructura. Aunque esto suele funcionar según lo esperado, el compilador genera un mensaje de advertencia y hace que el acceso a través del nombre de clase o estructura en lugar de la variable.  
  
-   **Acceso mediante una expresión de instancia.** Si tiene acceso a un elemento compartido a través de una expresión que devuelve una instancia de su clase o estructura, el compilador hace que el acceso a través del nombre de clase o estructura en lugar de evaluar la expresión. Esto produce resultados inesperados si va a usar la expresión para realizar otras acciones, así como devolver la instancia. Esto se ilustra en el siguiente ejemplo:  
  
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
  
     En el ejemplo anterior, el compilador genera un mensaje de advertencia dos veces el código tiene acceso a la variable compartida `total` a través de una instancia. En cada caso, obtiene acceso directamente a través de la clase `shareTotal` y no hacer uso de cualquier instancia. En el caso de la llamada al procedimiento prevista `returnClass`, esto significa que incluso no generar una llamada a `returnClass`, por lo que no se realiza la acción adicional de mostrar "Function returnClass() called".  
  
 El modificador `Shared` se puede utilizar en los contextos siguientes:  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Static](../../../visual-basic/language-reference/modifiers/static.md)  
 [Duración en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
