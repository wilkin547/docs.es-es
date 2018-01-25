---
title: "-moduleassemblyname (Opción del compilador de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ef68b6a75d9f5bd65e7d549240dc061097f2d30c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="-moduleassemblyname-c-compiler-option"></a><span data-ttu-id="bbfc4-102">-moduleassemblyname (Opción del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="bbfc4-102">-moduleassemblyname (C# Compiler Option)</span></span>
<span data-ttu-id="bbfc4-103">Especifica un ensamblado con tipos no públicos a los que puede acceder un archivo .netmodule.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-103">Specifies an assembly whose non-public types a .netmodule can access.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbfc4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbfc4-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="bbfc4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bbfc4-105">Arguments</span></span>  
 `assembly_name`  
 <span data-ttu-id="bbfc4-106">El nombre del ensamblado a cuyos tipos no públicos .netmodule puede tener acceso.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-106">The name of the assembly whose non-public types the .netmodule can access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbfc4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bbfc4-107">Remarks</span></span>  
 <span data-ttu-id="bbfc4-108">Se debería usar **-moduleassemblyname** al compilar un .netmodule cuando se den las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="bbfc4-108">**-moduleassemblyname** should be used when building a .netmodule, and where the following conditions are true:</span></span>  
  
-   <span data-ttu-id="bbfc4-109">.netmodule necesita tener acceso a los tipos no públicos de un ensamblado existente.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-109">The .netmodule needs access to non-public types in an existing assembly.</span></span>  
  
-   <span data-ttu-id="bbfc4-110">Sabe el nombre del ensamblado en el que se compilará .netmodule.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-110">You know the name of the assembly into which the .netmodule will be built.</span></span>  
  
-   <span data-ttu-id="bbfc4-111">El ensamblado existente ha concedido acceso de ensamblado de confianza al ensamblado en el que se compilará .netmodule.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-111">The existing assembly has granted friend assembly access to the assembly into which the .netmodule will be built.</span></span>  
  
 <span data-ttu-id="bbfc4-112">Para más información sobre cómo compilar .netmodule, vea [-target:module (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="bbfc4-112">For more information on building a .netmodule, see [-target:module (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="bbfc4-113">Para obtener más información sobre los ensamblados de confianza, vea [Ensamblados de confianza](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="bbfc4-113">For more information on friend assemblies, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="bbfc4-114">Esta opción no está disponible en el entorno de desarrollo; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-114">This option is not available from within the development environment; it is only available when compiling from the command line.</span></span>  
  
 <span data-ttu-id="bbfc4-115">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbfc4-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbfc4-116">Example</span></span>  
 <span data-ttu-id="bbfc4-117">Este ejemplo compila un ensamblado con un tipo privado que concede acceso de ensamblado de confianza a un ensamblado llamado csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-117">This sample builds an assembly with a private type, and that gives friend assembly access to an assembly called csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: -target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class   
{  
    public void Test()   
    {   
        Console.WriteLine("An_Internal_Class.Test called");   
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="bbfc4-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbfc4-118">Example</span></span>  
 <span data-ttu-id="bbfc4-119">Este ejemplo compila un .netmodule que tiene acceso a un tipo no público del ensamblado moduleassemblyname_1.dll.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-119">This sample builds a .netmodule that accesses a non-public type in the assembly moduleassemblyname_1.dll.</span></span> <span data-ttu-id="bbfc4-120">Sabiendo que este .netmodule se integrará en un ensamblado denominado csman_an_assembly, se puede especificar **-moduleassemblyname**, lo que permite que .netmodule tenga acceso a los tipos no públicos de un ensamblado que ha concedido acceso de ensamblado de confianza a csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-120">By knowing that this .netmodule will be built into an assembly called csman_an_assembly, we can specify **-moduleassemblyname**, allowing the .netmodule to access non-public types in an assembly that has granted friend assembly access to csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: -moduleassemblyname:csman_an_assembly -target:module -reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="bbfc4-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbfc4-121">Example</span></span>  
 <span data-ttu-id="bbfc4-122">Este ejemplo de código compila el ensamblado csman_an_assembly, haciendo referencia al ensamblado compilado previamente y a .netmodule.</span><span class="sxs-lookup"><span data-stu-id="bbfc4-122">This code sample builds the assembly csman_an_assembly, referencing the previously-built assembly and .netmodule.</span></span>  
  
```csharp  
// csman_an_assembly.cs  
// compile with: -addmodule:moduleassemblyname_2.netmodule -reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
 <span data-ttu-id="bbfc4-123">**Se ha llamado a An_Internal_Class.Test**</span><span class="sxs-lookup"><span data-stu-id="bbfc4-123">**An_Internal_Class.Test called**</span></span>  
## <a name="see-also"></a><span data-ttu-id="bbfc4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbfc4-124">See Also</span></span>  
 [<span data-ttu-id="bbfc4-125">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="bbfc4-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="bbfc4-126">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="bbfc4-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
