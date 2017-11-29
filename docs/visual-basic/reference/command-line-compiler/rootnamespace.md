---
title: /rootnamespace
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6b5da8e5eacacde9de5bdc54ef2d5e4d7f0d2653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="rootnamespace"></a><span data-ttu-id="83ab8-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="83ab8-102">/rootnamespace</span></span>
<span data-ttu-id="83ab8-103">Especifica un espacio de nombres para todas las declaraciones de tipos.</span><span class="sxs-lookup"><span data-stu-id="83ab8-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ab8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83ab8-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="83ab8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="83ab8-105">Arguments</span></span>  
  
|<span data-ttu-id="83ab8-106">Término</span><span class="sxs-lookup"><span data-stu-id="83ab8-106">Term</span></span>|<span data-ttu-id="83ab8-107">Definición</span><span class="sxs-lookup"><span data-stu-id="83ab8-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="83ab8-108">El nombre del espacio de nombres en el que se va a incluir todas las declaraciones de tipo para el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="83ab8-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83ab8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83ab8-109">Remarks</span></span>  
 <span data-ttu-id="83ab8-110">Si usa el archivo ejecutable de Visual Studio (Devenv.exe) para compilar un proyecto creado en el entorno de desarrollo integrado de Visual Studio, use `/rootnamespace` para especificar el valor de la <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="83ab8-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="83ab8-111">Vea [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="83ab8-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="83ab8-112">Utilizar el Desensamblador de MSIL de common language runtime (`Ildasm.exe`) para ver los nombres de espacio de nombres en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="83ab8-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="83ab8-113">Para establecer /rootnamespace en Visual Studio integra el entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="83ab8-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="83ab8-114">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="83ab8-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="83ab8-115">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="83ab8-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="83ab8-116">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="83ab8-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="83ab8-117">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="83ab8-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="83ab8-118">3.  Modifique el valor en el **raíz Namespace** cuadro.</span><span class="sxs-lookup"><span data-stu-id="83ab8-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="83ab8-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83ab8-119">Example</span></span>  
 <span data-ttu-id="83ab8-120">El siguiente código compila `In.vb` y agrega todas las declaraciones de tipo en el espacio de nombres `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="83ab8-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="83ab8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="83ab8-121">See Also</span></span>  
 [<span data-ttu-id="83ab8-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83ab8-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="83ab8-123">Ildasm.exe (Desensamblador de IL)</span><span class="sxs-lookup"><span data-stu-id="83ab8-123">Ildasm.exe (IL Disassembler)</span></span>](https://msdn.microsoft.com/library/f7dy01k1)  
 [<span data-ttu-id="83ab8-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="83ab8-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
