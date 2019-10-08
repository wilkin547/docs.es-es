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
ms.openlocfilehash: 4df4e74fc13c922f51f5b74c3c152bdea28b4431
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005210"
---
# <a name="-rootnamespace"></a><span data-ttu-id="73a97-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="73a97-102">-rootnamespace</span></span>
<span data-ttu-id="73a97-103">Especifica un espacio de nombres para todas las declaraciones de tipos.</span><span class="sxs-lookup"><span data-stu-id="73a97-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73a97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73a97-104">Syntax</span></span>  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="73a97-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="73a97-105">Arguments</span></span>  
  
|<span data-ttu-id="73a97-106">Término</span><span class="sxs-lookup"><span data-stu-id="73a97-106">Term</span></span>|<span data-ttu-id="73a97-107">Definición</span><span class="sxs-lookup"><span data-stu-id="73a97-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="73a97-108">Nombre del espacio de nombres en el que se deben incluir todas las declaraciones de tipos para el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="73a97-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73a97-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73a97-109">Remarks</span></span>  
 <span data-ttu-id="73a97-110">Si usa el archivo ejecutable de Visual Studio (devenv. exe) para compilar un proyecto creado en el entorno de desarrollo integrado de Visual Studio, use `-rootnamespace` para especificar el valor de la propiedad <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="73a97-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="73a97-111">Para obtener más información, vea [Modificadores](/visualstudio/ide/reference/devenv-command-line-switches) de la línea de comandos de devenv.</span><span class="sxs-lookup"><span data-stu-id="73a97-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="73a97-112">Use el Common Language Runtime desensamblador de MSIL (`Ildasm.exe`) para ver los nombres de los espacios de nombres en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="73a97-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="73a97-113">Para establecer-RootNamespace en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73a97-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="73a97-114">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="73a97-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="73a97-115">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="73a97-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="73a97-116">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="73a97-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="73a97-117">3.  Modifique el valor en el cuadro **espacio de nombres raíz** .</span><span class="sxs-lookup"><span data-stu-id="73a97-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73a97-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73a97-118">Example</span></span>  
 <span data-ttu-id="73a97-119">En el código siguiente se compila `In.vb` y se encierran todas las declaraciones de tipos en el espacio de nombres `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="73a97-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="73a97-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="73a97-120">See also</span></span>

- [<span data-ttu-id="73a97-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73a97-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="73a97-122">Ildasm.exe (Desensamblador de IL)</span><span class="sxs-lookup"><span data-stu-id="73a97-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="73a97-123">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="73a97-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
