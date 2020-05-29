---
title: Ensamblados de confianza
description: Un ensamblado de confianza es un ensamblado .NET que puede acceder a los tipos y miembros internos (C#) o de confianza (Visual Basic) de otro ensamblado.
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: 105621da2bd418c6294fa2bbec474809599cb6a5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378930"
---
# <a name="friend-assemblies"></a>Ensamblados de confianza

Un *ensamblado de confianza* puede acceder a los tipos y miembros [internal](../../csharp/language-reference/keywords/internal.md) (C#) o [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) de otro ensamblado. Si identifica un ensamblado como ensamblado de confianza, ya no hay que marcar los tipos y miembros como públicos para que otros ensamblados accedan a ellos. Esto resulta especialmente útil en los siguientes escenarios:

- Durante las pruebas unitarias, cuando se ejecuta código de prueba en un ensamblado independiente que requiere acceso a miembros del ensamblado en pruebas marcados como `internal` en C# o `Friend` en Visual Basic.

- Cuando desarrolla una biblioteca de clases y las adiciones a la biblioteca se incluyen en ensamblados independientes que requieren acceso a miembros de ensamblados existentes marcados como `internal` en C# o `Friend` en Visual Basic.

## <a name="remarks"></a>Comentarios

Puede usar el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para identificar uno o más ensamblados de confianza para un ensamblado determinado. En el ejemplo siguiente se usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> en *Assembly A* y se especifica el ensamblado *AssemblyB* como un ensamblado de confianza. Esto proporciona al ensamblado *AssemblyB* acceso a todos los tipos y miembros del ensamblado *Assembly A* marcados como `internal` en C# o `Friend` en Visual Basic.

> [!NOTE]
> Cuando se compila un ensamblado como *AssemblyB*, que accederá a tipos o miembros internos de otro ensamblado (como *Assembly A*), hay que especificar explícitamente el nombre del archivo de salida ( *.exe* o *.dll*) mediante la opción **-out** del compilador. Esto es necesario porque el compilador no ha generado aún el nombre del ensamblado que está creando en el momento en que se enlaza a referencias externas. Para obtener más información, consulte [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

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

```vb
Imports System.Runtime.CompilerServices
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

Solo los ensamblados que se especifiquen explícitamente como de confianza pueden acceder a tipos y miembros `internal` (C#) o `Friend` (Visual Basic). Por ejemplo, si el ensamblado *AssemblyB* es de confianza para *Assembly A* y el ensamblado *Assembly C* hace referencia a *AssemblyB*, *Assembly C* no tiene acceso a tipos `internal` (C#) o `Friend` (Visual Basic) en *Assembly A*.

El compilador realiza una validación básica del nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Si *Assembly A* declara a *AssemblyB* como ensamblado de confianza, las reglas de validación son las siguientes:

- Si *Assembly A* tiene un nombre seguro, *AssemblyB* también debe tener un nombre seguro. El nombre de ensamblado de confianza que se pasa al atributo debe estar formado por el nombre del ensamblado y la clave pública de la clave de nombre seguro que se usa para firmar el ensamblado *AssemblyB*.

     El nombre de ensamblado de confianza que se pasa al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> no puede ser el nombre seguro de *AssemblyB*. No incluya la versión, la referencia cultural, la arquitectura o el token de clave pública del ensamblado.

- Si el ensamblado *Assembly A* no tiene nombre seguro, el nombre de ensamblado de confianza solo debe consistir en el nombre del ensamblado. Para obtener más información, vea [Cómo: Crear ensamblados de confianza sin firmar](create-unsigned-friend.md).

- Si *AssemblyB* tiene un nombre seguro, hay que especificar la clave de nombre seguro de *AssemblyB* mediante la configuración del proyecto o la opción `/keyfile` de la línea de comandos del compilador. Para obtener más información, vea [Cómo: Crear ensamblados de confianza firmados](create-signed-friend.md).

 La clase <xref:System.Security.Permissions.StrongNameIdentityPermission> también proporciona la capacidad de compartir tipos, con las siguientes diferencias:

- <xref:System.Security.Permissions.StrongNameIdentityPermission> se aplica a un tipo individual, mientras que un ensamblado de confianza se aplica al ensamblado completo.

- Si hay cientos de tipos en *Assembly A* que quiere compartir con *AssemblyB*, tiene que agregar <xref:System.Security.Permissions.StrongNameIdentityPermission> a todos. Si usa un ensamblado de confianza, solo tiene que declarar una vez la relación de confianza.

- Si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, los tipos que quiere compartir tienen que declararse como públicos. Si usa un ensamblado de confianza, los tipos compartidos se declaran como `internal` (C#) o `Friend` (Visual Basic).

Para obtener información sobre cómo acceder a los tipos y métodos `internal` (C#) o `Friend` (Visual Basic) de un ensamblado desde un archivo de módulo (un archivo con la extensión *.netmodule*), consulte [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) o [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [Cómo: Crear ensamblados de confianza sin firmar](create-unsigned-friend.md)
- [Cómo: Crear ensamblados de confianza firmados](create-signed-friend.md)
- [Ensamblados de .NET](index.md)
- [Guía de programación de C#](../../csharp/programming-guide/index.md)
- [Conceptos de programación (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
