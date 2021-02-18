---
description: Más información sobre -rootnamespace
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
ms.openlocfilehash: 0e034999a65bf5294e63c8f9cec1a4ce4de39a4b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474088"
---
# <a name="-rootnamespace"></a><span data-ttu-id="a80ee-103">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="a80ee-103">-rootnamespace</span></span>

<span data-ttu-id="a80ee-104">Especifica un espacio de nombres para todas las declaraciones de tipos.</span><span class="sxs-lookup"><span data-stu-id="a80ee-104">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a80ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a80ee-105">Syntax</span></span>  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="a80ee-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a80ee-106">Arguments</span></span>  
  
|<span data-ttu-id="a80ee-107">Término</span><span class="sxs-lookup"><span data-stu-id="a80ee-107">Term</span></span>|<span data-ttu-id="a80ee-108">Definición</span><span class="sxs-lookup"><span data-stu-id="a80ee-108">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="a80ee-109">Nombre del espacio de nombres en el que se van a incluir todas las declaraciones de tipos para el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="a80ee-109">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a80ee-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a80ee-110">Remarks</span></span>  

 <span data-ttu-id="a80ee-111">Si usa el archivo ejecutable de Visual Studio (devenv.exe) para compilar un proyecto creado en el entorno de desarrollo integrado de Visual Studio, utilice `-rootnamespace` para especificar el valor de la propiedad <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="a80ee-111">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="a80ee-112">Para obtener más información, vea [Modificadores de línea de comandos para Devenv](/visualstudio/ide/reference/devenv-command-line-switches).</span><span class="sxs-lookup"><span data-stu-id="a80ee-112">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="a80ee-113">Use el desensamblador de MSIL de Common Language Runtime (`Ildasm.exe`) para ver los nombres de los espacios de nombres en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="a80ee-113">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="a80ee-114">Para establecer -rootnamespace en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a80ee-114">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="a80ee-115">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a80ee-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a80ee-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a80ee-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="a80ee-117">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="a80ee-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="a80ee-118">3.  Modifique el valor del cuadro **Espacio de nombres raíz**.</span><span class="sxs-lookup"><span data-stu-id="a80ee-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a80ee-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a80ee-119">Example</span></span>  

 <span data-ttu-id="a80ee-120">El código siguiente compila `In.vb` y agrega todas las declaraciones de tipos en el espacio de nombres `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="a80ee-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a80ee-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a80ee-121">See also</span></span>

- [<span data-ttu-id="a80ee-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a80ee-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a80ee-123">Ildasm.exe (Desensamblador de IL)</span><span class="sxs-lookup"><span data-stu-id="a80ee-123">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="a80ee-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a80ee-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
