---
title: Filtrar Crear ensamblados de confianza firmados (Visual Basic)
ms.date: 03/14/2018
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
ms.openlocfilehash: 699c3de3c246be0bafdcc66ca7fd82384dc66d92
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758877"
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="916be-102">Filtrar Crear ensamblados de confianza firmados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="916be-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="916be-103">En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados que tienen nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="916be-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="916be-104">Ambos ensamblados deben tener nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="916be-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="916be-105">Aunque los dos ensamblados de este ejemplo usan las mismas claves, es posible usar claves diferentes para dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="916be-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="916be-106">Para crear un ensamblado con signo y un ensamblado de confianza</span><span class="sxs-lookup"><span data-stu-id="916be-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="916be-107">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="916be-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="916be-108">Use la siguiente secuencia de comandos con la herramienta de nombre seguro para generar un archivo de claves y mostrar su clave pública.</span><span class="sxs-lookup"><span data-stu-id="916be-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="916be-109">Para obtener más información, consulte [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="916be-109">For more information, see [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
    1.  <span data-ttu-id="916be-110">Genere una clave de nombre seguro para este ejemplo y almacénela en el archivo FriendAssemblies.snk:</span><span class="sxs-lookup"><span data-stu-id="916be-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="916be-111">Extraiga la clave pública de FriendAssemblies.snk y colóquela en FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="916be-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="916be-112">Muestre la clave pública almacenada en el archivo FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="916be-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="916be-113">Cree un archivo de Visual Basic llamado `friend_signed_A` que contiene el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="916be-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="916be-114">El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar friend_signed_B como un ensamblado de confianza.</span><span class="sxs-lookup"><span data-stu-id="916be-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="916be-115">La herramienta de nombre seguro genera una nueva clave pública cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="916be-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="916be-116">Por tanto, debe reemplazar la clave pública en el código siguiente con la clave pública que acaba de generar, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="916be-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
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
  
4.  <span data-ttu-id="916be-117">Compile y firme friend_signed_A mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="916be-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```console  
    Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  <span data-ttu-id="916be-118">Crear un archivo de Visual Basic que se denomina `friend_signed_B` y contiene el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="916be-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="916be-119">Dado que friend_signed_A especifica que friend_signed_B es un ensamblado de confianza, el código de friend_signed_B puede tener acceso a tipos `Friend` y miembros de friend_signed_A.</span><span class="sxs-lookup"><span data-stu-id="916be-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="916be-120">El archivo contiene el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="916be-120">The file contains the following code.</span></span>  
  
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
  
6.  <span data-ttu-id="916be-121">Compile y firme friend_signed_B mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="916be-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```console  
    vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="916be-122">El nombre del ensamblado generado por el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="916be-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="916be-123">Puede establecer explícitamente el ensamblado utilizando el `-out` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="916be-123">You can explicitly set the assembly by using the `-out` compiler option.</span></span> <span data-ttu-id="916be-124">Para obtener más información, consulte [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="916be-124">For more information, see [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7.  <span data-ttu-id="916be-125">Ejecute el archivo friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="916be-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="916be-126">El programa muestra la cadena "Class1.Test".</span><span class="sxs-lookup"><span data-stu-id="916be-126">The program displays the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="916be-127">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="916be-127">.NET Framework Security</span></span>  
 <span data-ttu-id="916be-128">Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="916be-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="916be-129">La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `Friend`.</span><span class="sxs-lookup"><span data-stu-id="916be-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916be-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="916be-130">See also</span></span>
- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="916be-131">Ensamblados y caché global de ensamblados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="916be-131">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [<span data-ttu-id="916be-132">Ensamblados de confianza (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="916be-132">Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)
- [<span data-ttu-id="916be-133">Cómo: Crear ensamblados de confianza sin firmar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="916be-133">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="916be-134">-keyfile</span><span class="sxs-lookup"><span data-stu-id="916be-134">-keyfile</span></span>](../../../../visual-basic/reference/command-line-compiler/keyfile.md)
- <span data-ttu-id="916be-135">[Sn.exe (herramienta de nombre seguro)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="916be-135">[Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
- [<span data-ttu-id="916be-136">Crear y utilizar ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="916be-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="916be-137">Conceptos de programación</span><span class="sxs-lookup"><span data-stu-id="916be-137">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
