---
title: 'Cómo: crear ensamblados de confianza sin firmar (Visual Basic)'
ms.custom: ''
ms.date: 03/14/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc71a27f24c634ebadb060325df4c602b1387b0
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a><span data-ttu-id="57861-102">Cómo: crear ensamblados de confianza sin firmar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57861-102">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="57861-103">En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados sin firmar.</span><span class="sxs-lookup"><span data-stu-id="57861-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="57861-104">Para crear un ensamblado y un ensamblado de confianza</span><span class="sxs-lookup"><span data-stu-id="57861-104">To create an assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="57861-105">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="57861-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="57861-106">Cree un archivo de Visual Basic denominado `friend_signed_A.` que contiene el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="57861-106">Create a Visual Basic file named `friend_signed_A.` that contains the following code.</span></span> <span data-ttu-id="57861-107">El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar friend_signed_B como un ensamblado de confianza.</span><span class="sxs-lookup"><span data-stu-id="57861-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' vbc -target:library friend_unsigned_A.vb  
    Imports System.Runtime.CompilerServices  
    Imports System  
  
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
  
3.  <span data-ttu-id="57861-108">Compile y firme friend_signed_A mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="57861-108">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```console  
    vbc -target:library friend_unsigned_A.vb  
    ```  
  
4.  <span data-ttu-id="57861-109">Cree un archivo de Visual Basic denominado `friend_unsigned_B` que contiene el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="57861-109">Create a Visual Basic file named `friend_unsigned_B` that contains the following code.</span></span> <span data-ttu-id="57861-110">Como friend_unsigned_A especifica que friend_unsigned_B es un ensamblado de confianza, el código de friend_unsigned_B puede tener acceso a tipos `Friend` y miembros de friend_unsigned_A.</span><span class="sxs-lookup"><span data-stu-id="57861-110">Because friend_unsigned_A specifies friend_unsigned_B as a friend assembly, the code in friend_unsigned_B can access `Friend` types and members from friend_unsigned_A.</span></span>  
  
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
  
5.  <span data-ttu-id="57861-111">Compile friend_signed_B mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="57861-111">Compile friend_signed_B by using the following command.</span></span>  
  
    ```console
    vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     <span data-ttu-id="57861-112">El nombre del ensamblado que genera el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="57861-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="57861-113">Puede establecer explícitamente el ensamblado utilizando el `/out` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="57861-113">You can explicitly set the assembly by using the `/out` compiler option.</span></span>  
  
6.  <span data-ttu-id="57861-114">Ejecute el archivo friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="57861-114">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="57861-115">El programa muestra dos cadenas: "Class1.Test" y "Class2.Test".</span><span class="sxs-lookup"><span data-stu-id="57861-115">The program displays two strings: "Class1.Test" and "Class2.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="57861-116">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="57861-116">.NET Framework Security</span></span>  
 <span data-ttu-id="57861-117">Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="57861-117">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="57861-118">La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `Friend`.</span><span class="sxs-lookup"><span data-stu-id="57861-118">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57861-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="57861-119">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="57861-120">Ensamblados y caché global de ensamblados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57861-120">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="57861-121">Ensamblados de confianza (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57861-121">Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="57861-122">Cómo: crear ensamblados de confianza firmados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57861-122">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [<span data-ttu-id="57861-123">Conceptos de la Guía de programación</span><span class="sxs-lookup"><span data-stu-id="57861-123">Programming Guide Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
