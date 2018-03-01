---
title: /optioninfer
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2df7fa743e72d12dcef1aa9be5ea43d24ef43cee
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="optioninfer"></a><span data-ttu-id="53363-102">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="53363-102">/optioninfer</span></span>
<span data-ttu-id="53363-103">Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.</span><span class="sxs-lookup"><span data-stu-id="53363-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53363-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53363-104">Syntax</span></span>  
  
```  
/optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="53363-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="53363-105">Arguments</span></span>  
  
|<span data-ttu-id="53363-106">Término</span><span class="sxs-lookup"><span data-stu-id="53363-106">Term</span></span>|<span data-ttu-id="53363-107">Definición</span><span class="sxs-lookup"><span data-stu-id="53363-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="53363-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="53363-108">`+` &#124; `-`</span></span>|<span data-ttu-id="53363-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="53363-109">Optional.</span></span> <span data-ttu-id="53363-110">Especifique `/optioninfer+` para habilitar la inferencia de tipo de variable local o `/optioninfer-` para bloquearla.</span><span class="sxs-lookup"><span data-stu-id="53363-110">Specify `/optioninfer+` to enable local type inference, or `/optioninfer-` to block it.</span></span> <span data-ttu-id="53363-111">La opción `/optioninfer`, sin ningún valor especificado, es igual a `/optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="53363-111">The `/optioninfer` option, with no value specified, is the same as `/optioninfer+`.</span></span> <span data-ttu-id="53363-112">El valor predeterminado cuando el modificador `/optioninfer` no está presente también es `/optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="53363-112">The default value when the `/optioninfer` switch is not present is also `/optioninfer+`.</span></span> <span data-ttu-id="53363-113">El valor predeterminado se establece en el archivo de respuesta vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="53363-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="53363-114">Puede utilizar la opción `/noconfig` para conservar los valores predeterminados internos del compilador en lugar de los especificados en vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="53363-114">You can use the `/noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="53363-115">El valor predeterminado del compilador para esta opción es `/optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="53363-115">The compiler default for this option is `/optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53363-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53363-116">Remarks</span></span>  
 <span data-ttu-id="53363-117">Si el archivo de código fuente contiene un [Option Infer instrucción](../../../visual-basic/language-reference/statements/option-infer-statement.md), la instrucción anula la `/optioninfer` configuración del compilador de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="53363-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `/optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set-optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="53363-118">Cómo establecer /optioninfer en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="53363-118">To set /optioninfer in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="53363-119">Seleccione un proyecto en **el Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="53363-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="53363-120">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="53363-120">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="53363-121">En el **compilar** ficha, modifique el valor en el **Option infer** cuadro.</span><span class="sxs-lookup"><span data-stu-id="53363-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53363-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53363-122">Example</span></span>  
 <span data-ttu-id="53363-123">El siguiente código compila `test.vb` con la inferencia de tipo de variable local habilitada.</span><span class="sxs-lookup"><span data-stu-id="53363-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="53363-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="53363-124">See Also</span></span>  
 [<span data-ttu-id="53363-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53363-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="53363-126">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="53363-126">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="53363-127">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="53363-127">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="53363-128">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="53363-128">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="53363-129">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="53363-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="53363-130">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="53363-130">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="53363-131">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="53363-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="53363-132">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="53363-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [<span data-ttu-id="53363-133">Página Compilación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53363-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [<span data-ttu-id="53363-134">/noconfig</span><span class="sxs-lookup"><span data-stu-id="53363-134">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="53363-135">Compilación desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="53363-135">Building from the Command Line</span></span>](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
