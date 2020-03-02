---
title: Procedimiento para crear ensamblados de confianza firmados
ms.date: 08/19/2019
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
dev_langs:
- csharp
- vb
ms.openlocfilehash: 9912fa70014a8828e994cf528644aaa7cb351fea
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159499"
---
# <a name="how-to-create-signed-friend-assemblies"></a><span data-ttu-id="afc39-102">Procedimiento para crear ensamblados de confianza firmados</span><span class="sxs-lookup"><span data-stu-id="afc39-102">How to: Create signed friend assemblies</span></span>
<span data-ttu-id="afc39-103">En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados que tienen nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="afc39-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="afc39-104">Ambos ensamblados deben tener nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="afc39-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="afc39-105">Aunque los dos ensamblados de este ejemplo usan las mismas claves, es posible usar claves diferentes para dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="afc39-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
## <a name="create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="afc39-106">Creación de un ensamblado firmado y un ensamblado de confianza</span><span class="sxs-lookup"><span data-stu-id="afc39-106">Create a signed assembly and a friend assembly</span></span>  
  
1. <span data-ttu-id="afc39-107">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="afc39-107">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="afc39-108">Use la siguiente secuencia de comandos con la herramienta de nombre seguro para generar un archivo de claves y mostrar su clave pública.</span><span class="sxs-lookup"><span data-stu-id="afc39-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="afc39-109">Para obtener más información, vea [Sn.exe (herramienta de nombre seguro)](../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="afc39-109">For more information, see [Sn.exe (Strong Name tool)](../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
    1. <span data-ttu-id="afc39-110">Genere una clave de nombre seguro para este ejemplo y almacénela en el archivo *FriendAssemblies.snk*:</span><span class="sxs-lookup"><span data-stu-id="afc39-110">Generate a strong-name key for this example and store it in the file *FriendAssemblies.snk*:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2. <span data-ttu-id="afc39-111">Extraiga la clave pública de *FriendAssemblies.snk* y colóquela en *FriendAssemblies.publickey*:</span><span class="sxs-lookup"><span data-stu-id="afc39-111">Extract the public key from *FriendAssemblies.snk* and put it into *FriendAssemblies.publickey*:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. <span data-ttu-id="afc39-112">Muestre la clave pública almacenada en el archivo *FriendAssemblies.publickey*:</span><span class="sxs-lookup"><span data-stu-id="afc39-112">Display the public key stored in the file *FriendAssemblies.publickey*:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. <span data-ttu-id="afc39-113">Cree un archivo de C# o de Visual Basic denominado *friend_signed_A* que contenga el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="afc39-113">Create a C# or Visual Basic file named *friend_signed_A* that contains the following code.</span></span> <span data-ttu-id="afc39-114">El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar *friend_signed_B* como un ensamblado de confianza.</span><span class="sxs-lookup"><span data-stu-id="afc39-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_signed_B* as a friend assembly.</span></span>  

   <span data-ttu-id="afc39-115">La herramienta de nombre seguro genera una nueva clave pública cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="afc39-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="afc39-116">Por tanto, debe reemplazar la clave pública en el código siguiente con la clave pública que acaba de generar, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="afc39-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  

   ```csharp  
   // friend_signed_A.cs  
   // Compile with:
   // csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   using System.Runtime.CompilerServices;  

   [assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")]  
   class Class1  
   {  
       public void Test()  
       {  
           System.Console.WriteLine("Class1.Test");  
           System.Console.ReadLine();  
       }  
   }  
   ```  

   ```vb  
   ' friend_signed_A.vb  
   ' Compile with:
   ' Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   Imports System.Runtime.CompilerServices  

   <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>
   Public Class Class1  
       Public Sub Test()  
           System.Console.WriteLine("Class1.Test")  
           System.Console.ReadLine()  
       End Sub  
   End Class  
   ```  

4. <span data-ttu-id="afc39-117">Compile y firme *friend_signed_A* mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="afc39-117">Compile and sign *friend_signed_A* by using the following command.</span></span>  

   ```csharp
   csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   ```  

   ```vb
   Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   ```  

5. <span data-ttu-id="afc39-118">Cree un archivo de C# o de Visual Basic denominado *friend_signed_B* que contenga el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="afc39-118">Create a C# or Visual Basic file named *friend_signed_B* that contains the following code.</span></span> <span data-ttu-id="afc39-119">Dado que *friend_signed_A* especifica que *friend_signed_B* es un ensamblado de confianza, el código de *friend_signed_B* puede tener acceso a tipos y miembros de C# (`internal`) o Visual Basic (`Friend`) desde *friend_signed_A*.</span><span class="sxs-lookup"><span data-stu-id="afc39-119">Because *friend_signed_A* specifies *friend_signed_B* as a friend assembly, the code in *friend_signed_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_signed_A*.</span></span> <span data-ttu-id="afc39-120">El archivo contiene el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="afc39-120">The file contains the following code.</span></span>  

   ```csharp  
   // friend_signed_B.cs  
   // Compile with:
   // csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   public class Program  
   {  
       static void Main()  
       {  
           Class1 inst = new Class1();  
           inst.Test();  
       }  
   }  
   ```  

   ```vb  
   ' friend_signed_B.vb  
   ' Compile with:
   ' Vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   Module Sample  
       Public Sub Main()  
           Dim inst As New Class1  
           inst.Test()  
       End Sub  
   End Module  
   ```  

6. <span data-ttu-id="afc39-121">Compile y firme *friend_signed_B* mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="afc39-121">Compile and sign *friend_signed_B* by using the following command.</span></span>  

   ```csharp
   csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   ```  

   ```vb
   vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   ```  

   <span data-ttu-id="afc39-122">El nombre del ensamblado generado por el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="afc39-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="afc39-123">Debe especificar explícitamente el nombre del ensamblado de salida ( *.exe* o *.dll*) mediante la opción `-out` del compilador.</span><span class="sxs-lookup"><span data-stu-id="afc39-123">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="afc39-124">Para obtener más información, consulte [-out (Opciones del compilador de C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="afc39-124">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>  

7. <span data-ttu-id="afc39-125">Ejecute el archivo *friend_signed_B.exe*.</span><span class="sxs-lookup"><span data-stu-id="afc39-125">Run the *friend_signed_B.exe* file.</span></span>  

   <span data-ttu-id="afc39-126">El programa imprime la cadena **Class1.Test**.</span><span class="sxs-lookup"><span data-stu-id="afc39-126">The program outputs the string **Class1.Test**.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="afc39-127">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="afc39-127">.NET security</span></span>  
 <span data-ttu-id="afc39-128">Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="afc39-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="afc39-129">La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `internal` (C#) o `Friend` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="afc39-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` (C#) or `Friend` (Visual Basic) types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afc39-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="afc39-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="afc39-131">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="afc39-131">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="afc39-132">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="afc39-132">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="afc39-133">Cómo: Crear ensamblados de confianza sin firmar</span><span class="sxs-lookup"><span data-stu-id="afc39-133">How to: Create unsigned friend assemblies</span></span>](create-unsigned-friend.md)
- [<span data-ttu-id="afc39-134">-keyfile (C#)</span><span class="sxs-lookup"><span data-stu-id="afc39-134">-keyfile (C#)</span></span>](../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [<span data-ttu-id="afc39-135">-keyfile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afc39-135">-keyfile (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="afc39-136">Sn.exe (herramienta de nombre seguro)</span><span class="sxs-lookup"><span data-stu-id="afc39-136">Sn.exe (Strong Name tool)</span></span>](../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="afc39-137">Creación y uso de ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="afc39-137">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="afc39-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="afc39-138">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="afc39-139">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afc39-139">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
