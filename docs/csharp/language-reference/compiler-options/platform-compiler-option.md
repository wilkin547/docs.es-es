---
title: -platform (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /platform
dev_langs:
- CSharp
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
caps.latest.revision: 46
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 44d4cadbc45eb141ecb7a83345d2a7a834ce5299
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="platform-c-compiler-options"></a><span data-ttu-id="06ce6-102">/platform (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="06ce6-102">/platform (C# Compiler Options)</span></span>
<span data-ttu-id="06ce6-103">Especifica qué versión de Common Language Runtime (CLR) puede ejecutar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="06ce6-103">Specifies which version of the common language runtime (CLR) can run the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ce6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06ce6-104">Syntax</span></span>  
  
```console  
/platform:string  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06ce6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06ce6-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="06ce6-106">anycpu (valor predeterminado), anycpu32bitpreferred, ARM, x64, x86 o Itanium.</span><span class="sxs-lookup"><span data-stu-id="06ce6-106">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06ce6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06ce6-107">Remarks</span></span>  
  
-   <span data-ttu-id="06ce6-108">**anycpu** (valor predeterminado) compila el ensamblado de forma que se pueda ejecutar en cualquier plataforma.</span><span class="sxs-lookup"><span data-stu-id="06ce6-108">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="06ce6-109">La aplicación se ejecuta como un proceso de 64 bits siempre que sea posible y recurre a 32 bits solo cuando el modo está disponible.</span><span class="sxs-lookup"><span data-stu-id="06ce6-109">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>  
  
-   <span data-ttu-id="06ce6-110">**anycpu32bitpreferred** compila el ensamblado de forma que se pueda ejecutar en cualquier plataforma.</span><span class="sxs-lookup"><span data-stu-id="06ce6-110">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="06ce6-111">La aplicación se ejecuta en modo de 32 bits en sistemas que admiten aplicaciones de 64 y 32 bits.</span><span class="sxs-lookup"><span data-stu-id="06ce6-111">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="06ce6-112">Solo puede especificar esta opción para los proyectos que tienen como destino .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="06ce6-112">You can specify this option only for projects that target the .NET Framework 4.5.</span></span>  
  
-   <span data-ttu-id="06ce6-113">**ARM** compila el ensamblado de forma que pueda ejecutarse en un equipo que tenga un procesador Advanced RISC Machine (ARM).</span><span class="sxs-lookup"><span data-stu-id="06ce6-113">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>  
  
-   <span data-ttu-id="06ce6-114">**x64** compila el ensamblado de forma que Common Language Runtime de 64 bits pueda ejecutarlo en equipos compatibles con el conjunto de instrucciones AMD64 o EM64T.</span><span class="sxs-lookup"><span data-stu-id="06ce6-114">**x64** compiles your assembly to be run by the 64-bit common language runtime on a computer that supports the AMD64 or EM64T instruction set.</span></span>  
  
-   <span data-ttu-id="06ce6-115">**x86** compila el ensamblado de forma que Common Language Runtime de 32 bits compatible con x86 pueda ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="06ce6-115">**x86** compiles your assembly to be run by the 32-bit, x86-compatible common language runtime.</span></span>  
  
-   <span data-ttu-id="06ce6-116">**Itanium** compila el ensamblado de forma que Common Language Runtime de 64 bits pueda ejecutarlo en equipos con un procesador Itanium.</span><span class="sxs-lookup"><span data-stu-id="06ce6-116">**Itanium** compiles your assembly to be run by the 64-bit common language runtime on a computer with an Itanium processor.</span></span>  
  
 <span data-ttu-id="06ce6-117">En un sistema operativo de Windows de 64 bits:</span><span class="sxs-lookup"><span data-stu-id="06ce6-117">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="06ce6-118">Los ensamblados compilados con **/platform:x86** se ejecutarán en el CLR de 32 bits que se ejecuta en WOW64.</span><span class="sxs-lookup"><span data-stu-id="06ce6-118">Assemblies compiled with **/platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="06ce6-119">Un archivo DLL compilado con **/platform:anycpu** se ejecuta en el mismo CLR que el proceso en el que se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="06ce6-119">A DLL compiled with the **/platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>  
  
-   <span data-ttu-id="06ce6-120">Los archivos ejecutables que se compilan con **/platform:anycpu** se ejecutan en el CLR de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="06ce6-120">Executables that are compiled with the **/platform:anycpu** execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="06ce6-121">Los archivos ejecutables compilados con **/platform:anycpu32bitpreferred** se ejecutan en el CLR de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="06ce6-121">Executables compiled with **/platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="06ce6-122">La configuración **anycpu32bitpreferred** es válida solo para archivos ejecutables (.exe) y requiere .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="06ce6-122">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="06ce6-123">Para obtener más información sobre cómo desarrollar una aplicación para que se ejecute en un sistema operativo Windows de 64 bits, consulte [Aplicaciones de 64 bits](https://msdn.microsoft.com/library/ms241064).</span><span class="sxs-lookup"><span data-stu-id="06ce6-123">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](https://msdn.microsoft.com/library/ms241064).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="06ce6-124">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="06ce6-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="06ce6-125">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="06ce6-125">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="06ce6-126">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="06ce6-126">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="06ce6-127">Modifique la propiedad **Destino de la plataforma** y, para los proyectos que tienen como destino .NET Framework 4.5, active o desactive la casilla **Preferencia de 32 bits**.</span><span class="sxs-lookup"><span data-stu-id="06ce6-127">Modify the **Platform target** property and, for projects that target the .NET Framework 4.5, select or clear the **Prefer 32-bit** check box.</span></span>  
  
 <span data-ttu-id="06ce6-128">Tenga en cuenta que **/platform** no está disponible en el entorno de desarrollo de Visual C# Express.</span><span class="sxs-lookup"><span data-stu-id="06ce6-128">**Note /platform** is not available in the development environment in Visual C# Express.</span></span>  
  
 <span data-ttu-id="06ce6-129">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span><span class="sxs-lookup"><span data-stu-id="06ce6-129">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06ce6-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06ce6-130">Example</span></span>  
 <span data-ttu-id="06ce6-131">En el ejemplo siguiente, se muestra cómo usar la opción **/platform** para especificar que la aplicación se debe ejecutar en el CLR de 64 bits en un sistema operativo Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="06ce6-131">The following example shows how to use the **/platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>  
  
```console  
csc /platform:anycpu filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="06ce6-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="06ce6-132">See Also</span></span>  
 <span data-ttu-id="06ce6-133">[Opciones del compilador de C#](index.md) </span><span class="sxs-lookup"><span data-stu-id="06ce6-133">[C# Compiler Options](index.md) </span></span>  
 [<span data-ttu-id="06ce6-134">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="06ce6-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

