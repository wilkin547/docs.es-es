---
title: -filealign (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /filealign
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
ms.openlocfilehash: 3437b0f90593eed2900829212866cf689ff54e8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660182"
---
# <a name="-filealign-c-compiler-options"></a><span data-ttu-id="e0d58-102">-filealign (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="e0d58-102">-filealign (C# Compiler Options)</span></span>
<span data-ttu-id="e0d58-103">La opción **-filealign** permite especificar el tamaño de las secciones en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="e0d58-103">The **-filealign** option lets you specify the size of sections in your output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0d58-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0d58-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="e0d58-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e0d58-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="e0d58-106">Un valor que especifica el tamaño de las secciones del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="e0d58-106">A value that specifies the size of sections in the output file.</span></span> <span data-ttu-id="e0d58-107">Los valores válidos son 512, 1024, 2048, 4096 y 8192.</span><span class="sxs-lookup"><span data-stu-id="e0d58-107">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="e0d58-108">Estos valores están en bytes.</span><span class="sxs-lookup"><span data-stu-id="e0d58-108">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0d58-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0d58-109">Remarks</span></span>  
 <span data-ttu-id="e0d58-110">Cada sección se alineará en un límite que es un múltiplo del valor **-filealign**.</span><span class="sxs-lookup"><span data-stu-id="e0d58-110">Each section will be aligned on a boundary that is a multiple of the **-filealign** value.</span></span> <span data-ttu-id="e0d58-111">No hay ningún valor predeterminado fijo.</span><span class="sxs-lookup"><span data-stu-id="e0d58-111">There is no fixed default.</span></span> <span data-ttu-id="e0d58-112">Si no se especifica **-filealign**, Common Language Runtime elige un valor predeterminado en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="e0d58-112">If **-filealign** is not specified, the common language runtime picks a default at compile time.</span></span>  
  
 <span data-ttu-id="e0d58-113">Al especificar el tamaño de la sección, el tamaño del archivo de salida se ve afectado.</span><span class="sxs-lookup"><span data-stu-id="e0d58-113">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="e0d58-114">Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="e0d58-114">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
 <span data-ttu-id="e0d58-115">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) para ver información sobre las secciones en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="e0d58-115">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e0d58-116">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0d58-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="e0d58-117">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0d58-117">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="e0d58-118">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="e0d58-118">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="e0d58-119">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="e0d58-119">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="e0d58-120">Modifique la propiedad **Alineación de archivo**.</span><span class="sxs-lookup"><span data-stu-id="e0d58-120">Modify the **File Alignment** property.</span></span>  
  
 <span data-ttu-id="e0d58-121">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0d58-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d58-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0d58-122">See also</span></span>

- [<span data-ttu-id="e0d58-123">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="e0d58-123">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="e0d58-124">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="e0d58-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
