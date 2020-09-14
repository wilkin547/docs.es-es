---
description: -platform (Opciones del compilador de C#)
title: -platform (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: 3fdb030dfc141b011f5faa827a4e4bb45ae38d19
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466019"
---
# <a name="-platform-c-compiler-options"></a><span data-ttu-id="7810d-103">-platform (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="7810d-103">-platform (C# Compiler Options)</span></span>

<span data-ttu-id="7810d-104">Especifica qué versión de Common Language Runtime (CLR) puede ejecutar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7810d-104">Specifies which version of the Common Language Runtime (CLR) can run the assembly.</span></span>

## <a name="syntax"></a><span data-ttu-id="7810d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7810d-105">Syntax</span></span>

```console
-platform:string
```

## <a name="parameters"></a><span data-ttu-id="7810d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7810d-106">Parameters</span></span>

`string` \
<span data-ttu-id="7810d-107">anycpu (valor predeterminado), anycpu32bitpreferred, ARM, x64, x86 o Itanium.</span><span class="sxs-lookup"><span data-stu-id="7810d-107">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>

## <a name="remarks"></a><span data-ttu-id="7810d-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7810d-108">Remarks</span></span>

- <span data-ttu-id="7810d-109">**anycpu** (valor predeterminado) compila el ensamblado de forma que se pueda ejecutar en cualquier plataforma.</span><span class="sxs-lookup"><span data-stu-id="7810d-109">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="7810d-110">La aplicación se ejecuta como un proceso de 64 bits siempre que sea posible y recurre a 32 bits solo cuando el modo está disponible.</span><span class="sxs-lookup"><span data-stu-id="7810d-110">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>

- <span data-ttu-id="7810d-111">**anycpu32bitpreferred** compila el ensamblado de forma que se pueda ejecutar en cualquier plataforma.</span><span class="sxs-lookup"><span data-stu-id="7810d-111">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="7810d-112">La aplicación se ejecuta en modo de 32 bits en sistemas que admiten aplicaciones de 64 y 32 bits.</span><span class="sxs-lookup"><span data-stu-id="7810d-112">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="7810d-113">Solo puede especificar esta opción para los proyectos que tienen como destino .NET Framework 4.5 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="7810d-113">You can specify this option only for projects that target .NET Framework 4.5 or later.</span></span>

- <span data-ttu-id="7810d-114">**ARM** compila el ensamblado de forma que pueda ejecutarse en un equipo que tenga un procesador Advanced RISC Machine (ARM).</span><span class="sxs-lookup"><span data-stu-id="7810d-114">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>

- <span data-ttu-id="7810d-115">**ARM64** compila el ensamblado que se va a ejecutar mediante el CLR de 64 bits en un equipo que tiene un procesador Advanced RISC Machine (ARM) que admite el conjunto de instrucciones A64.</span><span class="sxs-lookup"><span data-stu-id="7810d-115">**ARM64** compiles your assembly to run by the 64-bit CLR on a computer that has an Advanced RISC Machine (ARM) processor that supports the A64 instruction set.</span></span>

- <span data-ttu-id="7810d-116">**x64** compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en equipos compatibles con el conjunto de instrucciones AMD64 o EM64T.</span><span class="sxs-lookup"><span data-stu-id="7810d-116">**x64** compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>

- <span data-ttu-id="7810d-117">**x86** compila el ensamblado de forma que el CLR de 32 bits compatible con x86 pueda ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="7810d-117">**x86** compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>

- <span data-ttu-id="7810d-118">**Itanium** compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en un equipo con un procesador Itanium.</span><span class="sxs-lookup"><span data-stu-id="7810d-118">**Itanium** compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>

<span data-ttu-id="7810d-119">En un sistema operativo de Windows de 64 bits:</span><span class="sxs-lookup"><span data-stu-id="7810d-119">On a 64-bit Windows operating system:</span></span>

- <span data-ttu-id="7810d-120">Los ensamblados compilados con **-platform:x86** se ejecutarán en el CLR de 32 bits que se ejecuta en WOW64.</span><span class="sxs-lookup"><span data-stu-id="7810d-120">Assemblies compiled with **-platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>

- <span data-ttu-id="7810d-121">Un archivo DLL compilado con **-platform:anycpu** se ejecuta en el mismo CLR que el proceso en el que se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="7810d-121">A DLL compiled with the **-platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>

- <span data-ttu-id="7810d-122">Los archivos ejecutables que se compilan con **-platform:anycpu** se ejecutan en el CLR de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7810d-122">Executables that are compiled with the **-platform:anycpu** execute on the 64-bit CLR.</span></span>

- <span data-ttu-id="7810d-123">Los archivos ejecutables compilados con **-platform:anycpu32bitpreferred** se ejecutan en el CLR de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="7810d-123">Executables compiled with **-platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>

<span data-ttu-id="7810d-124">El valor **anycpu32bitpreferred** solo es válido para archivos ejecutables (.EXE) y requiere .NET Framework 4.5 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="7810d-124">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires .NET Framework 4.5 or later.</span></span>

<span data-ttu-id="7810d-125">Para obtener más información sobre cómo desarrollar una aplicación para que se ejecute en un sistema operativo Windows de 64 bits, consulte [Aplicaciones de 64 bits](../../../framework/64-bit-apps.md).</span><span class="sxs-lookup"><span data-stu-id="7810d-125">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="7810d-126">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7810d-126">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="7810d-127">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7810d-127">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="7810d-128">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="7810d-128">Click the **Build** property page.</span></span>

3. <span data-ttu-id="7810d-129">Modifique la propiedad **Destino de la plataforma** y, para los proyectos que tienen como destino .NET Framework 4.5 o una versión posterior, active o desactive la casilla **Preferencia de 32 bits**.</span><span class="sxs-lookup"><span data-stu-id="7810d-129">Modify the **Platform target** property and, for projects that target .NET Framework 4.5 or later, select or clear the **Prefer 32-bit** check box.</span></span>

> [!NOTE]
> <span data-ttu-id="7810d-130">`-platform` no está disponible en el entorno de desarrollo de Visual C# Express.</span><span class="sxs-lookup"><span data-stu-id="7810d-130">`-platform` is not available in the development environment in Visual C# Express.</span></span>

<span data-ttu-id="7810d-131">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span><span class="sxs-lookup"><span data-stu-id="7810d-131">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>

## <a name="example"></a><span data-ttu-id="7810d-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7810d-132">Example</span></span>

<span data-ttu-id="7810d-133">En el ejemplo siguiente, se muestra cómo usar la opción **-platform** para especificar que la aplicación se debe ejecutar en el CLR de 64 bits en un sistema operativo Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7810d-133">The following example shows how to use the **-platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>

```console
csc -platform:anycpu filename.cs
```

## <a name="see-also"></a><span data-ttu-id="7810d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7810d-134">See also</span></span>

- [<span data-ttu-id="7810d-135">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="7810d-135">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="7810d-136">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="7810d-136">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
