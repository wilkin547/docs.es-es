---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: b6a2f3ba0772d8f8c8c6a762a1be01703d21b778
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403140"
---
# <a name="-rootnamespace"></a><span data-ttu-id="d8ed6-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="d8ed6-102">-rootnamespace</span></span>
<span data-ttu-id="d8ed6-103">Especifica un espacio de nombres para todas las declaraciones de tipos.</span><span class="sxs-lookup"><span data-stu-id="d8ed6-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ed6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8ed6-104">Syntax</span></span>  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="d8ed6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d8ed6-105">Arguments</span></span>  
  
|<span data-ttu-id="d8ed6-106">Término</span><span class="sxs-lookup"><span data-stu-id="d8ed6-106">Term</span></span>|<span data-ttu-id="d8ed6-107">Definición</span><span class="sxs-lookup"><span data-stu-id="d8ed6-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="d8ed6-108">Nombre del espacio de nombres en el que se van a incluir todas las declaraciones de tipos para el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="d8ed6-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8ed6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8ed6-109">Remarks</span></span>  
 <span data-ttu-id="d8ed6-110">Si usa el archivo ejecutable de Visual Studio (devenv.exe) para compilar un proyecto creado en el entorno de desarrollo integrado de Visual Studio, utilice `-rootnamespace` para especificar el valor de la propiedad <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ed6-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="d8ed6-111">Para obtener más información, vea [Modificadores de línea de comandos para Devenv](/visualstudio/ide/reference/devenv-command-line-switches).</span><span class="sxs-lookup"><span data-stu-id="d8ed6-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="d8ed6-112">Use el desensamblador de MSIL de Common Language Runtime (`Ildasm.exe`) para ver los nombres de los espacios de nombres en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="d8ed6-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="d8ed6-113">Para establecer -rootnamespace en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d8ed6-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d8ed6-114">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="d8ed6-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d8ed6-115">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d8ed6-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d8ed6-116">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="d8ed6-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="d8ed6-117">3.  Modifique el valor del cuadro **Espacio de nombres raíz**.</span><span class="sxs-lookup"><span data-stu-id="d8ed6-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d8ed6-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8ed6-118">Example</span></span>  
 <span data-ttu-id="d8ed6-119">El código siguiente compila `In.vb` y agrega todas las declaraciones de tipos en el espacio de nombres `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="d8ed6-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8ed6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8ed6-120">See also</span></span>

- [<span data-ttu-id="d8ed6-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8ed6-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="d8ed6-122">Ildasm.exe (Desensamblador de IL)</span><span class="sxs-lookup"><span data-stu-id="d8ed6-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="d8ed6-123">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8ed6-123">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
