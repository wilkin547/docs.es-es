---
description: -unsafe (Opciones del compilador de C#)
title: -unsafe (Opciones del compilador de C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 0f6d94dd25a020d96430746c4b5e7aefd0f679da
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89140846"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="d28bd-103">-unsafe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="d28bd-103">-unsafe (C# Compiler Options)</span></span>

<span data-ttu-id="d28bd-104">La opción del compilador **-unsafe** permite la compilación de código en el que se usa la palabra clave [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="d28bd-104">The **-unsafe** compiler option allows code that uses the [unsafe](../keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d28bd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d28bd-105">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="d28bd-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d28bd-106">Remarks</span></span>

<span data-ttu-id="d28bd-107">Para obtener más información sobre el código no seguro, vea [Código no seguro y punteros](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="d28bd-107">For more information about unsafe code, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="d28bd-108">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d28bd-108">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="d28bd-109">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d28bd-109">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="d28bd-110">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="d28bd-110">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="d28bd-111">Active la casilla **Permitir código no seguro**.</span><span class="sxs-lookup"><span data-stu-id="d28bd-111">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="d28bd-112">Para agregar esta opción en un archivo csproj</span><span class="sxs-lookup"><span data-stu-id="d28bd-112">To add this option in a csproj file</span></span>

<span data-ttu-id="d28bd-113">Abra el archivo .csproj de un proyecto y agregue los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="d28bd-113">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="d28bd-114">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="d28bd-114">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d28bd-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d28bd-115">Example</span></span>

<span data-ttu-id="d28bd-116">Compile `in.cs` para el modo no seguro:</span><span class="sxs-lookup"><span data-stu-id="d28bd-116">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="d28bd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d28bd-117">See also</span></span>

- [<span data-ttu-id="d28bd-118">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="d28bd-118">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="d28bd-119">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="d28bd-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
