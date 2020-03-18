---
title: Procedimiento para crear ensamblados de confianza sin firmar
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: f8fec064507553b8208083578165965de2303a33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352433"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a><span data-ttu-id="d4f2a-102">Procedimiento para crear ensamblados de confianza sin firmar</span><span class="sxs-lookup"><span data-stu-id="d4f2a-102">How to: Create unsigned friend assemblies</span></span>

<span data-ttu-id="d4f2a-103">En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados sin firmar.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>

## <a name="create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="d4f2a-104">Creación de un ensamblado y un ensamblado de confianza</span><span class="sxs-lookup"><span data-stu-id="d4f2a-104">Create an assembly and a friend assembly</span></span>

1. <span data-ttu-id="d4f2a-105">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-105">Open a command prompt.</span></span>

2. <span data-ttu-id="d4f2a-106">Cree un archivo de C# o de Visual Basic denominado *friend_unsigned_A* que contenga el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-106">Create a C# or Visual Basic file named *friend_unsigned_A* that contains the following code.</span></span> <span data-ttu-id="d4f2a-107">El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar *friend_unsigned_B* como un ensamblado de confianza.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_unsigned_B* as a friend assembly.</span></span>

   ```csharp
   // friend_unsigned_A.cs
   // Compile with:
   // csc /target:library friend_unsigned_A.cs
   using System.Runtime.CompilerServices;
   using System;

   [assembly: InternalsVisibleTo("friend_unsigned_B")]

   // Type is internal by default.
   class Class1
   {
       public void Test()
       {
           Console.WriteLine("Class1.Test");
       }
   }

   // Public type with internal member.
   public class Class2
   {
       internal void Test()
       {
           Console.WriteLine("Class2.Test");
       }
   }
   ```

   ```vb
   ' friend_unsigned_A.vb
   ' Compile with:
   ' vbc -target:library friend_unsigned_A.vb
   Imports System.Runtime.CompilerServices

   <Assembly: InternalsVisibleTo("friend_unsigned_B")>

   ' Friend type.
   Friend Class Class1
       Public Sub Test()
           Console.WriteLine("Class1.Test")
       End Sub
   End Class

   ' Public type with Friend member.
   Public Class Class2
       Friend Sub Test()
           Console.WriteLine("Class2.Test")
       End Sub
   End Class
   ```

3. <span data-ttu-id="d4f2a-108">Compile y firme *friend_unsigned_A* mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d4f2a-108">Compile and sign *friend_unsigned_A* by using the following command:</span></span>

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. <span data-ttu-id="d4f2a-109">Cree un archivo de C# o de Visual Basic denominado *friend_unsigned_B* que contenga el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-109">Create a C# or Visual Basic file named *friend_unsigned_B* that contains the following code.</span></span> <span data-ttu-id="d4f2a-110">Dado que *friend_unsigned_A* especifica que *friend_unsigned_B* es un ensamblado de confianza, el código de *friend_unsigned_B* puede tener acceso a tipos y miembros de C# (`internal`) o Visual Basic (`Friend`) desde *friend_unsigned_A*.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-110">Because *friend_unsigned_A* specifies *friend_unsigned_B* as a friend assembly, the code in *friend_unsigned_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_unsigned_A*.</span></span>

   ```csharp
   // friend_unsigned_B.cs
   // Compile with:
   // csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   public class Program
   {
       static void Main()
       {
           // Access an internal type.
           Class1 inst1 = new Class1();
           inst1.Test();

           Class2 inst2 = new Class2();
           // Access an internal member of a public type.
           inst2.Test();

           System.Console.ReadLine();
       }
   }
   ```

   ```vb
   ' friend_unsigned_B.vb
   ' Compile with:
   ' vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   Module Module1
       Sub Main()
           ' Access a Friend type.
           Dim inst1 As New Class1()
           inst1.Test()

           Dim inst2 As New Class2()
           ' Access a Friend member of a public type.
           inst2.Test()

           System.Console.ReadLine()
       End Sub
   End Module
   ```

5. <span data-ttu-id="d4f2a-111">Compile *friend_unsigned_B* mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-111">Compile *friend_unsigned_B* by using the following command.</span></span>

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   <span data-ttu-id="d4f2a-112">El nombre del ensamblado que genera el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="d4f2a-113">Debe especificar explícitamente el nombre del ensamblado de salida ( *.exe* o *.dll*) mediante la opción `-out` del compilador.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-113">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="d4f2a-114">Para obtener más información, consulte [-out (Opciones del compilador de C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="d4f2a-114">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span></span>

6. <span data-ttu-id="d4f2a-115">Ejecute el archivo *friend_unsigned_B.exe*.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-115">Run the *friend_unsigned_B.exe* file.</span></span>

   <span data-ttu-id="d4f2a-116">El programa genera dos cadenas: **Class1.Test** y **Class2.Test**.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-116">The program outputs two strings: **Class1.Test** and **Class2.Test**.</span></span>

## <a name="net-security"></a><span data-ttu-id="d4f2a-117">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="d4f2a-117">.NET security</span></span>

<span data-ttu-id="d4f2a-118">Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="d4f2a-118">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="d4f2a-119">La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `internal` o `Friend` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d4f2a-119">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal`  or `Friend` (Visual Basic) types and members.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4f2a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4f2a-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="d4f2a-121">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="d4f2a-121">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="d4f2a-122">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="d4f2a-122">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="d4f2a-123">Cómo: Crear ensamblados de confianza firmados</span><span class="sxs-lookup"><span data-stu-id="d4f2a-123">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="d4f2a-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d4f2a-124">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d4f2a-125">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4f2a-125">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
