---
title: -unsafe (Opciones del compilador de C#)
ms.date: 04/25/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 35868923ed2f34587c66f04395324489e8b36538
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="ff81f-102">-unsafe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="ff81f-102">-unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="ff81f-103">La opción del compilador **-unsafe** permite la compilación de código en el que se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="ff81f-103">The **-unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff81f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff81f-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="ff81f-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff81f-105">Remarks</span></span>  
 <span data-ttu-id="ff81f-106">Para obtener más información sobre el código no seguro, vea [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff81f-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ff81f-107">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ff81f-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="ff81f-108">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ff81f-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="ff81f-109">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="ff81f-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="ff81f-110">Active la casilla **Permitir código no seguro**.</span><span class="sxs-lookup"><span data-stu-id="ff81f-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="ff81f-111">Para agregar esta opción en un archivo csproj</span><span class="sxs-lookup"><span data-stu-id="ff81f-111">To add this option in a csproj file</span></span>

<span data-ttu-id="ff81f-112">Abra el archivo .csproj de un proyecto y agregue los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="ff81f-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="ff81f-113">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff81f-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff81f-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff81f-114">Example</span></span>  
 <span data-ttu-id="ff81f-115">Compile `in.cs` para el modo no seguro:</span><span class="sxs-lookup"><span data-stu-id="ff81f-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff81f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff81f-116">See Also</span></span>  
 [<span data-ttu-id="ff81f-117">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="ff81f-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="ff81f-118">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="ff81f-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
