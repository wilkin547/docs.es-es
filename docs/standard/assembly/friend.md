---
title: Ensamblados de confianza
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: a74d4b74ead8492028a092e090f9281231802a87
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348177"
---
# <a name="friend-assemblies"></a><span data-ttu-id="1c98c-102">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="1c98c-102">Friend assemblies</span></span>

<span data-ttu-id="1c98c-103">Un *ensamblado de confianza* puede acceder a los tipos y miembros [internal](../../csharp/language-reference/keywords/internal.md) (C#) o [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) de otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1c98c-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../csharp/language-reference/keywords/internal.md) (C#) or [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) types and members.</span></span> <span data-ttu-id="1c98c-104">Si identifica un ensamblado como ensamblado de confianza, ya no hay que marcar los tipos y miembros como públicos para que otros ensamblados accedan a ellos.</span><span class="sxs-lookup"><span data-stu-id="1c98c-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="1c98c-105">Esto resulta especialmente útil en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="1c98c-105">This is especially convenient in the following scenarios:</span></span>

- <span data-ttu-id="1c98c-106">Durante las pruebas unitarias, cuando se ejecuta código de prueba en un ensamblado independiente que requiere acceso a miembros del ensamblado en pruebas marcados como `internal` en C# o `Friend` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1c98c-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

- <span data-ttu-id="1c98c-107">Cuando desarrolla una biblioteca de clases y las adiciones a la biblioteca se incluyen en ensamblados independientes que requieren acceso a miembros de ensamblados existentes marcados como `internal` en C# o `Friend` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1c98c-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c98c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c98c-108">Remarks</span></span>

<span data-ttu-id="1c98c-109">Puede usar el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para identificar uno o más ensamblados de confianza para un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="1c98c-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="1c98c-110">En el ejemplo siguiente se usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> en *Assembly A* y se especifica el ensamblado *AssemblyB* como un ensamblado de confianza.</span><span class="sxs-lookup"><span data-stu-id="1c98c-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in *Assembly A* and specifies assembly *AssemblyB* as a friend assembly.</span></span> <span data-ttu-id="1c98c-111">Esto proporciona al ensamblado *AssemblyB* acceso a todos los tipos y miembros del ensamblado *Assembly A* marcados como `internal` en C# o `Friend` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1c98c-111">This gives assembly *AssemblyB* access to all types and members in *Assembly A* that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

> [!NOTE]
> <span data-ttu-id="1c98c-112">Cuando se compila un ensamblado como *AssemblyB*, que accederá a tipos o miembros internos de otro ensamblado (como *Assembly A*), hay que especificar explícitamente el nombre del archivo de salida ( *.exe* o *.dll*) mediante la opción **-out** del compilador.</span><span class="sxs-lookup"><span data-stu-id="1c98c-112">When you compile an assembly like *AssemblyB* that will access internal types or internal members of another assembly like *Assembly A*, you must explicitly specify the name of the output file (*.exe* or *.dll*) by using the **-out** compiler option.</span></span> <span data-ttu-id="1c98c-113">Esto es necesario porque el compilador no ha generado aún el nombre del ensamblado que está creando en el momento en que se enlaza a referencias externas.</span><span class="sxs-lookup"><span data-stu-id="1c98c-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="1c98c-114">Para obtener más información, consulte [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="1c98c-114">For more information, see [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>

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

<span data-ttu-id="1c98c-115">Solo los ensamblados que se especifiquen explícitamente como de confianza pueden acceder a tipos y miembros `internal` (C#) o `Friend` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="1c98c-115">Only assemblies that you explicitly specify as friends can access `internal` (C#) or `Friend` (Visual Basic) types and members.</span></span> <span data-ttu-id="1c98c-116">Por ejemplo, si el ensamblado *AssemblyB* es de confianza para *Assembly A* y el ensamblado *Assembly C* hace referencia a *AssemblyB*, *Assembly C* no tiene acceso a tipos `internal` (C#) o `Friend` (Visual Basic) en *Assembly A*.</span><span class="sxs-lookup"><span data-stu-id="1c98c-116">For example, if *AssemblyB* is a friend of *Assembly A* and *Assembly C* references *AssemblyB*, *Assembly C* does not have access to `internal` (C#) or `Friend` (Visual Basic) types in *Assembly A*.</span></span>

<span data-ttu-id="1c98c-117">El compilador realiza una validación básica del nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1c98c-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="1c98c-118">Si *Assembly A* declara a *AssemblyB* como ensamblado de confianza, las reglas de validación son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c98c-118">If *Assembly A* declares *AssemblyB* as a friend assembly, the validation rules are as follows:</span></span>

- <span data-ttu-id="1c98c-119">Si *Assembly A* tiene un nombre seguro, *AssemblyB* también debe tener un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="1c98c-119">If *Assembly A* is strong named, *AssemblyB* must also be strong named.</span></span> <span data-ttu-id="1c98c-120">El nombre de ensamblado de confianza que se pasa al atributo debe estar formado por el nombre del ensamblado y la clave pública de la clave de nombre seguro que se usa para firmar el ensamblado *AssemblyB*.</span><span class="sxs-lookup"><span data-stu-id="1c98c-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign *AssemblyB*.</span></span>

     <span data-ttu-id="1c98c-121">El nombre de ensamblado de confianza que se pasa al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> no puede ser el nombre seguro de *AssemblyB*.</span><span class="sxs-lookup"><span data-stu-id="1c98c-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of *AssemblyB*.</span></span> <span data-ttu-id="1c98c-122">No incluya la versión, la referencia cultural, la arquitectura o el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1c98c-122">Don't include the assembly version, culture, architecture, or public key token.</span></span>

- <span data-ttu-id="1c98c-123">Si el ensamblado *Assembly A* no tiene nombre seguro, el nombre de ensamblado de confianza solo debe consistir en el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1c98c-123">If *Assembly A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="1c98c-124">Para obtener más información, vea [Cómo: Crear ensamblados de confianza sin firmar](create-unsigned-friend.md).</span><span class="sxs-lookup"><span data-stu-id="1c98c-124">For more information, see [How to: Create unsigned friend assemblies](create-unsigned-friend.md).</span></span>

- <span data-ttu-id="1c98c-125">Si *AssemblyB* tiene un nombre seguro, hay que especificar la clave de nombre seguro de *AssemblyB* mediante la configuración del proyecto o la opción `/keyfile` de la línea de comandos del compilador.</span><span class="sxs-lookup"><span data-stu-id="1c98c-125">If *AssemblyB* is strong named, you must specify the strong-name key for *AssemblyB* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="1c98c-126">Para obtener más información, vea [Cómo: Crear ensamblados de confianza firmados](create-signed-friend.md).</span><span class="sxs-lookup"><span data-stu-id="1c98c-126">For more information, see [How to: Create signed friend assemblies](create-signed-friend.md).</span></span>

 <span data-ttu-id="1c98c-127">La clase <xref:System.Security.Permissions.StrongNameIdentityPermission> también proporciona la capacidad de compartir tipos, con las siguientes diferencias:</span><span class="sxs-lookup"><span data-stu-id="1c98c-127">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>

- <span data-ttu-id="1c98c-128"><xref:System.Security.Permissions.StrongNameIdentityPermission> se aplica a un tipo individual, mientras que un ensamblado de confianza se aplica al ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="1c98c-128"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>

- <span data-ttu-id="1c98c-129">Si hay cientos de tipos en *Assembly A* que quiere compartir con *AssemblyB*, tiene que agregar <xref:System.Security.Permissions.StrongNameIdentityPermission> a todos.</span><span class="sxs-lookup"><span data-stu-id="1c98c-129">If there are hundreds of types in *Assembly A* that you want to share with *AssemblyB*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="1c98c-130">Si usa un ensamblado de confianza, solo tiene que declarar una vez la relación de confianza.</span><span class="sxs-lookup"><span data-stu-id="1c98c-130">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>

- <span data-ttu-id="1c98c-131">Si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, los tipos que quiere compartir tienen que declararse como públicos.</span><span class="sxs-lookup"><span data-stu-id="1c98c-131">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="1c98c-132">Si usa un ensamblado de confianza, los tipos compartidos se declaran como `internal` (C#) o `Friend` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="1c98c-132">If you use a friend assembly, the shared types are declared as `internal` (C#) or `Friend` (Visual Basic).</span></span>

<span data-ttu-id="1c98c-133">Para obtener información sobre cómo acceder a los tipos y métodos `internal` (C#) o `Friend` (Visual Basic) de un ensamblado desde un archivo de módulo (un archivo con la extensión *.netmodule*), consulte [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) o [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="1c98c-133">For information about how to access an assembly's `internal` (C#) or `Friend` (Visual Basic) types and methods from a module file (a file with the *.netmodule* extension), see [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) or [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c98c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c98c-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [<span data-ttu-id="1c98c-135">Cómo: Crear ensamblados de confianza sin firmar</span><span class="sxs-lookup"><span data-stu-id="1c98c-135">How to: Create unsigned friend assemblies</span></span>](create-unsigned-friend.md)
- [<span data-ttu-id="1c98c-136">Cómo: Crear ensamblados de confianza firmados</span><span class="sxs-lookup"><span data-stu-id="1c98c-136">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="1c98c-137">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="1c98c-137">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="1c98c-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1c98c-138">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1c98c-139">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c98c-139">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
