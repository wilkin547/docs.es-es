---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: 4848dec148bc528e7a30940643e3364f1bb5f805
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939197"
---
# <a name="-optioninfer"></a><span data-ttu-id="1790d-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="1790d-102">-optioninfer</span></span>
<span data-ttu-id="1790d-103">Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.</span><span class="sxs-lookup"><span data-stu-id="1790d-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1790d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1790d-104">Syntax</span></span>  
  
```  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1790d-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1790d-105">Arguments</span></span>  
  
|<span data-ttu-id="1790d-106">Término</span><span class="sxs-lookup"><span data-stu-id="1790d-106">Term</span></span>|<span data-ttu-id="1790d-107">Definición</span><span class="sxs-lookup"><span data-stu-id="1790d-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="1790d-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1790d-108">`+` &#124; `-`</span></span>|<span data-ttu-id="1790d-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1790d-109">Optional.</span></span> <span data-ttu-id="1790d-110">Especifique `-optioninfer+` para habilitar la inferencia de tipo de variable local o `-optioninfer-` para bloquearla.</span><span class="sxs-lookup"><span data-stu-id="1790d-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="1790d-111">La opción `-optioninfer`, sin ningún valor especificado, es igual a `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="1790d-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="1790d-112">El valor predeterminado cuando el modificador `-optioninfer` no está presente también es `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="1790d-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="1790d-113">El valor predeterminado se establece en el archivo de respuesta vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="1790d-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="1790d-114">Puede utilizar la opción `-noconfig` para conservar los valores predeterminados internos del compilador en lugar de los especificados en vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="1790d-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="1790d-115">El valor predeterminado del compilador para esta opción es `-optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="1790d-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1790d-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1790d-116">Remarks</span></span>  
 <span data-ttu-id="1790d-117">Si el archivo de código fuente contiene una [instrucción Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md), la instrucción reemplaza la `-optioninfer` configuración del compilador de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="1790d-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="1790d-118">Para Set-optioninfer (en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1790d-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="1790d-119">Seleccione un proyecto en **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="1790d-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="1790d-120">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1790d-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="1790d-121">En la pestaña compilar, modifique el valor del cuadro **Option Infer** .</span><span class="sxs-lookup"><span data-stu-id="1790d-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1790d-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1790d-122">Example</span></span>  
 <span data-ttu-id="1790d-123">El siguiente código compila `test.vb` con la inferencia de tipo de variable local habilitada.</span><span class="sxs-lookup"><span data-stu-id="1790d-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1790d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1790d-124">See also</span></span>

- [<span data-ttu-id="1790d-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1790d-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1790d-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="1790d-126">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="1790d-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="1790d-127">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="1790d-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="1790d-128">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="1790d-129">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1790d-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="1790d-130">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1790d-130">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="1790d-131">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="1790d-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="1790d-132">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="1790d-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="1790d-133">Página Compilación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1790d-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="1790d-134">/noconfig</span><span class="sxs-lookup"><span data-stu-id="1790d-134">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="1790d-135">Compilación desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="1790d-135">Building from the Command Line</span></span>](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
