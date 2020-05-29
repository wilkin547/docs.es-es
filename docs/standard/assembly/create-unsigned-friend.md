---
title: Procedimiento para crear ensamblados de confianza sin firmar
description: En este artículo se muestra cómo usar ensamblados de confianza con ensamblados sin firmar. Se incluye información sobre la seguridad de .NET.
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: 8d3e13669c36048759fedeb3df1bfb59fd476317
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378971"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a><span data-ttu-id="f734a-104">Procedimiento para crear ensamblados de confianza sin firmar</span><span class="sxs-lookup"><span data-stu-id="f734a-104">How to: Create unsigned friend assemblies</span></span>

<span data-ttu-id="f734a-105">En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados sin firmar.</span><span class="sxs-lookup"><span data-stu-id="f734a-105">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>

## <a name="create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="f734a-106">Creación de un ensamblado y un ensamblado de confianza</span><span class="sxs-lookup"><span data-stu-id="f734a-106">Create an assembly and a friend assembly</span></span>

1. <span data-ttu-id="f734a-107">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="f734a-107">Open a command prompt.</span></span>

2. <span data-ttu-id="f734a-108">Cree un archivo de C# o de Visual Basic denominado *friend_unsigned_A* que contenga el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f734a-108">Create a C# or Visual Basic file named *friend_unsigned_A* that contains the following code.</span></span> <span data-ttu-id="f734a-109">El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar *friend_unsigned_B* como un ensamblado de confianza.</span><span class="sxs-lookup"><span data-stu-id="f734a-109">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_unsigned_B* as a friend assembly.</span></span>

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

3. <span data-ttu-id="f734a-110">Compile y firme *friend_unsigned_A* mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f734a-110">Compile and sign *friend_unsigned_A* by using the following command:</span></span>

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. <span data-ttu-id="f734a-111">Cree un archivo de C# o de Visual Basic denominado *friend_unsigned_B* que contenga el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f734a-111">Create a C# or Visual Basic file named *friend_unsigned_B* that contains the following code.</span></span> <span data-ttu-id="f734a-112">Dado que *friend_unsigned_A* especifica que *friend_unsigned_B* es un ensamblado de confianza, el código de *friend_unsigned_B* puede tener acceso a tipos y miembros de C# (`internal`) o Visual Basic (`Friend`) desde *friend_unsigned_A*.</span><span class="sxs-lookup"><span data-stu-id="f734a-112">Because *friend_unsigned_A* specifies *friend_unsigned_B* as a friend assembly, the code in *friend_unsigned_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_unsigned_A*.</span></span>

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

5. <span data-ttu-id="f734a-113">Compile *friend_unsigned_B* mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="f734a-113">Compile *friend_unsigned_B* by using the following command.</span></span>

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   <span data-ttu-id="f734a-114">El nombre del ensamblado que genera el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f734a-114">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="f734a-115">Debe especificar explícitamente el nombre del ensamblado de salida ( *.exe* o *.dll*) mediante la opción `-out` del compilador.</span><span class="sxs-lookup"><span data-stu-id="f734a-115">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="f734a-116">Para obtener más información, consulte [-out (Opciones del compilador de C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="f734a-116">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span></span>

6. <span data-ttu-id="f734a-117">Ejecute el archivo *friend_unsigned_B.exe*.</span><span class="sxs-lookup"><span data-stu-id="f734a-117">Run the *friend_unsigned_B.exe* file.</span></span>

   <span data-ttu-id="f734a-118">El programa genera dos cadenas: **Class1.Test** y **Class2.Test**.</span><span class="sxs-lookup"><span data-stu-id="f734a-118">The program outputs two strings: **Class1.Test** and **Class2.Test**.</span></span>

## <a name="net-security"></a><span data-ttu-id="f734a-119">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="f734a-119">.NET security</span></span>

<span data-ttu-id="f734a-120">Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="f734a-120">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="f734a-121">La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `internal` o `Friend` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="f734a-121">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal`  or `Friend` (Visual Basic) types and members.</span></span>

## <a name="see-also"></a><span data-ttu-id="f734a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f734a-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="f734a-123">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="f734a-123">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="f734a-124">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="f734a-124">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="f734a-125">Cómo: Crear ensamblados de confianza firmados</span><span class="sxs-lookup"><span data-stu-id="f734a-125">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="f734a-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f734a-126">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f734a-127">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f734a-127">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
