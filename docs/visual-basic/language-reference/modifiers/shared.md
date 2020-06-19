---
title: Compartido
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
ms.openlocfilehash: b51c88e1af3a720912af8ba6aaf8ae4016af9cfa
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990189"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)

Especifica que uno o varios elementos de programación declarados están asociados a una clase o estructura de gran tamaño, y no a una instancia específica de la clase o estructura.

## <a name="when-to-use-shared"></a>Cuándo usar Shared

Compartir un miembro de una clase o estructura lo pone a disposición de todas las instancias, en lugar de *no compartidas*, donde cada instancia conserva su propia copia. El uso compartido es útil, por ejemplo, si el valor de una variable se aplica a toda la aplicación. Si declara que esa variable es `Shared` , todas las instancias acceden a la misma ubicación de almacenamiento y, si una instancia cambia el valor de la variable, todas las instancias acceden al valor actualizado.

El uso compartido no modifica el nivel de acceso de un miembro. Por ejemplo, un miembro de clase puede ser compartido y privado (accesible solo desde dentro de la clase), o no compartido y público. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Solo se puede usar `Shared` en un nivel de módulo. Esto significa que el contexto de la declaración de un `Shared` elemento debe ser una clase o estructura, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.

- **Modificadores combinados.** No se puede especificar `Shared` junto con [invalidaciones](overrides.md), [Overridable](overridable.md), [NotOverridable](notoverridable.md), [MustOverride](mustoverride.md)o [static](static.md) en la misma declaración.

- **Acceso a.** Puede tener acceso a un elemento compartido si lo califica con su nombre de clase o estructura, no con el nombre de variable de una instancia específica de su clase o estructura. No es necesario crear una instancia de una clase o estructura para tener acceso a sus miembros compartidos.

     En el ejemplo siguiente se llama al procedimiento compartido <xref:System.Double.IsNaN%2A> expuesto por la <xref:System.Double> estructura.

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- **Uso compartido implícito.** No se puede usar el `Shared` modificador en una [instrucción const](../statements/const-statement.md), pero las constantes se comparten implícitamente. Del mismo modo, no puede declarar un miembro de un módulo o una interfaz para que sea `Shared` , pero se comparten implícitamente.

## <a name="behavior"></a>Comportamiento

- **Discos.** Una variable o evento compartido se almacena en la memoria solo una vez, independientemente del número de instancias que cree de su clase o estructura. De forma similar, un procedimiento compartido o una propiedad solo contiene un conjunto de variables locales.

- **Obtener acceso a través de una variable de instancia.** Es posible obtener acceso a un elemento compartido si se califica con el nombre de una variable que contiene una instancia específica de su clase o estructura. Aunque esto suele funcionar según lo esperado, el compilador genera un mensaje de advertencia y hace que el acceso se realice a través del nombre de la clase o la estructura en lugar de la variable.

- **Obtener acceso a través de una expresión de instancia.** Si obtiene acceso a un elemento compartido a través de una expresión que devuelve una instancia de su clase o estructura, el compilador realiza el acceso a través del nombre de la clase o la estructura en lugar de evaluar la expresión. Este acceso produce resultados inesperados si desea que la expresión realice otras acciones, así como para devolver la instancia. En el ejemplo siguiente se muestra esta situación.
  
    ```vb
    Sub Main()
        ' The following line is the preferred way to access Total.
        ShareTotal.Total = 10

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of through
        ' the variable instanceVar. This works as expected and adds
        ' 100 to Total.
        Dim instanceVar As New ShareTotal
        instanceVar.Total += 100

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of calling
        ' ReturnClass(). This adds 1000 to total but does not work as
        ' expected, because the WriteLine in ReturnClass() does not run.
        Console.WriteLine("Value of total is " & CStr(ShareTotal.Total))
        ReturnClass().Total += 1000
    End Sub

    Public Function ReturnClass() As ShareTotal
        Console.WriteLine("Function ReturnClass() called")
        Return New ShareTotal
    End Function

    Public Class ShareTotal
        Public Shared Property Total As Integer
    End Class
    ```

     En el ejemplo anterior, el compilador genera un mensaje de advertencia ambas veces el código tiene acceso a la propiedad compartida `Total` a través de una instancia de. En cada caso, realiza el acceso directamente a través de la clase `ShareTotal` y no hace uso de ninguna instancia. En el caso de la llamada prevista al procedimiento `ReturnClass` , esto significa que no genera ni siquiera una llamada a `ReturnClass` , por lo que no se realiza la acción adicional de mostrar "función ReturnClass () llamada".

El modificador `Shared` se puede utilizar en los contextos siguientes:

- [Instrucción Dim](../statements/dim-statement.md)
- [Event (Instrucción)](../statements/event-statement.md)
- [Instrucción Function](../statements/function-statement.md)
- [Operator Statement](../statements/operator-statement.md)
- [Property Statement](../statements/property-statement.md)
- [Instrucción Sub](../statements/sub-statement.md)
  
## <a name="see-also"></a>Consulte también

- [Shadows](shadows.md)
- [Estática](static.md)
- [Período de duración en Visual Basic](../../programming-guide/language-features/declared-elements/lifetime.md)
- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
