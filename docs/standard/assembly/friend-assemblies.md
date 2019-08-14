---
title: Ensamblados de confianza (C#)
ms.date: 03/03/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
ms.openlocfilehash: 770eb70a5350d7d26e03cb4e605b442100da2a53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "68671200"
---
# <a name="friend-assemblies"></a>Ensamblados de confianza

Un *ensamblado de confianza* puede acceder a los tipos y miembros [internal](../../csharp/language-reference/keywords/internal.md) de otro ensamblado (en C# o [Friend](../../visual-basic/language-reference/modifiers/friend.md) en Visual Basic). Si identifica un ensamblado como ensamblado de confianza, ya no hay que marcar los tipos y miembros como públicos para que otros ensamblados accedan a ellos. Esto resulta especialmente útil en los siguientes escenarios:

- Durante las pruebas unitarias, cuando se ejecuta código de prueba en un ensamblado independiente que requiere acceso a miembros del ensamblado en pruebas marcados como `internal` en C# o `Friend` en Visual Basic.

- Cuando desarrolla una biblioteca de clases y las adiciones a la biblioteca se incluyen en ensamblados independientes que requieren acceso a miembros de ensamblados existentes marcados como `internal` en C# o `Friend` en Visual Basic.

## <a name="remarks"></a>Comentarios

Puede usar el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para identificar uno o más ensamblados de confianza para un ensamblado determinado. En el ejemplo siguiente se usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> en el ensamblado A y se especifica el ensamblado `AssemblyB` como un ensamblado de confianza. Esto proporciona al ensamblado `AssemblyB` acceso a todos los tipos y miembros del ensamblado A marcados como `internal` en C# o `Friend` en Visual Basic.

> [!NOTE]
> Cuando se compila un ensamblado (ensamblado `AssemblyB`) que accederá a tipos o miembros internos de otro ensamblado (ensamblado *A*), hay que especificar explícitamente el nombre del archivo de salida (.exe o .dll) mediante la opción **/out** del compilador. Esto es necesario porque el compilador no ha generado aún el nombre del ensamblado que está creando en el momento en que se enlaza a referencias externas. Para más información, consulte [/out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [/out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

```csharp
using System.Runtime.CompilerServices;
using System;

[assembly: InternalsVisibleTo("AssemblyB")]

// The class is internal by default.
class FriendClass
{
    public void Test()
    {
        Console.WriteLine("Sample Class");
    }
}

// Public class that has an internal method.
public class ClassWithFriendMethod
{
    internal void Test()
    {
        Console.WriteLine("Sample Method");
    }

}
```

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

```vb
Imports System.Runtime.CompilerServices
Imports System
<Assembly: InternalsVisibleTo("AssemblyB")>

' Friend class.
Friend Class FriendClass
    Public Sub Test()
        Console.WriteLine("Sample Class")
    End Sub
End Class

' Public class with a Friend method.
Public Class ClassWithFriendMethod
    Friend Sub Test()
        Console.WriteLine("Sample Method")
    End Sub
End Class
```

---

Solo los ensamblados que se especifiquen explícitamente como de confianza pueden acceder a tipos y miembros `internal` (en C# o `Friend` en Visual Basic). Por ejemplo, si el ensamblado B es de confianza para el ensamblado A y el ensamblado C hace referencia al ensamblado B, C no tiene acceso a tipos `internal` (en C# o `Friend` en Visual Basic) en A.

El compilador realiza una validación básica del nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Si el ensamblado *A* declara a *B* como ensamblado de confianza, las reglas de validación son las siguientes:

- Si el ensamblado *A* tiene un nombre seguro, el ensamblado *B* también deben tener un nombre seguro. El nombre de ensamblado de confianza que se pasa al atributo debe estar formado por el nombre del ensamblado y la clave pública de la clave de nombre seguro que se usa para firmar el ensamblado *B*.

     El nombre de ensamblado de confianza que se pasa al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> no puede ser el nombre seguro del ensamblado *B*: no se incluyen la versión del ensamblado, la referencia cultural, la arquitectura o el token de clave pública.

- Si el ensamblado *A* no tiene nombre seguro, el nombre de ensamblado de confianza solo debe consistir en el nombre del ensamblado. Para obtener más información, vea [Cómo: Procedimiento Crear ensamblados de confianza sin firmar (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) o [Procedimiento Crear ensamblados de confianza sin firmar (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).

- Si el ensamblado *B* tiene nombre seguro, hay que especificar la clave de nombre seguro del ensamblado *B* mediante la configuración del proyecto o la opción `/keyfile` de línea de comandos del compilador. Para obtener más información, vea [Cómo: Procedimiento Crear ensamblados de confianza firmados (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) o [Procedimiento Crear ensamblados de confianza firmados (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).

 La clase <xref:System.Security.Permissions.StrongNameIdentityPermission> también proporciona la capacidad de compartir tipos, con las siguientes diferencias:

- <xref:System.Security.Permissions.StrongNameIdentityPermission> se aplica a un tipo individual, mientras que un ensamblado de confianza se aplica al ensamblado completo.

- Si hay cientos de tipos en el ensamblado *A* que quiere compartir con el ensamblado *B*, tiene que agregarles <xref:System.Security.Permissions.StrongNameIdentityPermission> a todos. Si usa un ensamblado de confianza, solo tiene que declarar una vez la relación de confianza.

- Si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, los tipos que quiere compartir tienen que declararse como públicos. Si usa un ensamblado de confianza, los tipos compartidos se declaran como `internal` (en C# o `Friend` en Visual Basic).

Para información sobre cómo acceder a los tipos y métodos `internal` (en C# o `Friend` en Visual Basic) de un ensamblado desde un archivo de módulo (un archivo con la extensión .netmodule), consulte [/moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) o [/moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [Cómo: Crear ensamblados de confianza sin firmar (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [Cómo: Crear ensamblados de confianza sin firmar (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [Cómo: Crear ensamblados de confianza firmados (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Cómo: Crear ensamblados de confianza firmados (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Ensamblados de .NET](index.md)
- [Guía de programación de C#](../../csharp/programming-guide/index.md)
- [Conceptos de programación](../../visual-basic/programming-guide/concepts/index.md)
