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
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "89140846"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="eb7ab-103">-unsafe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="eb7ab-103">-unsafe (C# Compiler Options)</span></span>

<span data-ttu-id="eb7ab-104">La opción del compilador **-unsafe** permite la compilación de código en el que se usa la palabra clave [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="eb7ab-104">The **-unsafe** compiler option allows code that uses the [unsafe](../keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb7ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb7ab-105">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="eb7ab-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eb7ab-106">Remarks</span></span>

<span data-ttu-id="eb7ab-107">Para obtener más información sobre el código no seguro, vea [Código no seguro y punteros](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="eb7ab-107">For more information about unsafe code, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="eb7ab-108">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eb7ab-108">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="eb7ab-109">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-109">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="eb7ab-110">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-110">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="eb7ab-111">Active la casilla **Permitir código no seguro**.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-111">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="eb7ab-112">Para agregar esta opción en un archivo csproj</span><span class="sxs-lookup"><span data-stu-id="eb7ab-112">To add this option in a csproj file</span></span>

<span data-ttu-id="eb7ab-113">Abra el archivo .csproj de un proyecto y agregue los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="eb7ab-113">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="eb7ab-114">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-114">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb7ab-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb7ab-115">Example</span></span>

<span data-ttu-id="eb7ab-116">Compile `in.cs` para el modo no seguro:</span><span class="sxs-lookup"><span data-stu-id="eb7ab-116">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb7ab-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb7ab-117">See also</span></span>

- [<span data-ttu-id="eb7ab-118">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="eb7ab-118">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="eb7ab-119">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="eb7ab-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
