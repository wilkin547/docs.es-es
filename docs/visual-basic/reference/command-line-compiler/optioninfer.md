---
description: Mas información sobre -optioninfer
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: d45761914612a28788cc5c1a848d92238f05c162
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475921"
---
# <a name="-optioninfer"></a><span data-ttu-id="e8a1b-103">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="e8a1b-103">-optioninfer</span></span>

<span data-ttu-id="e8a1b-104">Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-104">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8a1b-105">Syntax</span></span>  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e8a1b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e8a1b-106">Arguments</span></span>  
  
|<span data-ttu-id="e8a1b-107">Término</span><span class="sxs-lookup"><span data-stu-id="e8a1b-107">Term</span></span>|<span data-ttu-id="e8a1b-108">Definición</span><span class="sxs-lookup"><span data-stu-id="e8a1b-108">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="e8a1b-109">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e8a1b-109">`+` &#124; `-`</span></span>|<span data-ttu-id="e8a1b-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-110">Optional.</span></span> <span data-ttu-id="e8a1b-111">Especifique `-optioninfer+` para habilitar la inferencia de tipo de variable local o `-optioninfer-` para bloquearla.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-111">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="e8a1b-112">La opción `-optioninfer`, sin ningún valor especificado, es igual a `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-112">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="e8a1b-113">El valor predeterminado cuando el modificador `-optioninfer` no está presente también es `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-113">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="e8a1b-114">El valor predeterminado se establece en el archivo de respuesta vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-114">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="e8a1b-115">Puede utilizar la opción `-noconfig` para conservar los valores predeterminados internos del compilador en lugar de los especificados en vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-115">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="e8a1b-116">El valor predeterminado del compilador para esta opción es `-optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-116">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8a1b-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8a1b-117">Remarks</span></span>  

 <span data-ttu-id="e8a1b-118">Si el archivo de código fuente contiene una [instrucción Option Infer](../../language-reference/statements/option-infer-statement.md), la declaración reemplaza la configuración `-optioninfer` del compilador de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-118">If the source code file contains an [Option Infer Statement](../../language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="e8a1b-119">Para establecer -optioninfer en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e8a1b-119">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="e8a1b-120">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-120">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="e8a1b-121">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-121">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="e8a1b-122">En la pestaña **Compilar**, modifique el valor del cuadro **Option infer**.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-122">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8a1b-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8a1b-123">Example</span></span>  

 <span data-ttu-id="e8a1b-124">El siguiente código compila `test.vb` con la inferencia de tipo de variable local habilitada.</span><span class="sxs-lookup"><span data-stu-id="e8a1b-124">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8a1b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8a1b-125">See also</span></span>

- [<span data-ttu-id="e8a1b-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8a1b-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e8a1b-127">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="e8a1b-127">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="e8a1b-128">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="e8a1b-128">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="e8a1b-129">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="e8a1b-129">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="e8a1b-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8a1b-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="e8a1b-131">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e8a1b-131">Option Infer Statement</span></span>](../../language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="e8a1b-132">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="e8a1b-132">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="e8a1b-133">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="e8a1b-133">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="e8a1b-134">Página Compilación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8a1b-134">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="e8a1b-135">-noconfig</span><span class="sxs-lookup"><span data-stu-id="e8a1b-135">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="e8a1b-136">Compilación desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="e8a1b-136">Building from the Command Line</span></span>](building-from-the-command-line.md)
