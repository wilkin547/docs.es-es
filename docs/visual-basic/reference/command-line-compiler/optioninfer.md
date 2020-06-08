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
ms.openlocfilehash: 524660fca7c56fa490cc85169898bf2bf6d1a16e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400583"
---
# <a name="-optioninfer"></a><span data-ttu-id="c6f6b-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="c6f6b-102">-optioninfer</span></span>
<span data-ttu-id="c6f6b-103">Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f6b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6f6b-104">Syntax</span></span>  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c6f6b-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c6f6b-105">Arguments</span></span>  
  
|<span data-ttu-id="c6f6b-106">Término</span><span class="sxs-lookup"><span data-stu-id="c6f6b-106">Term</span></span>|<span data-ttu-id="c6f6b-107">Definición</span><span class="sxs-lookup"><span data-stu-id="c6f6b-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="c6f6b-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c6f6b-108">`+` &#124; `-`</span></span>|<span data-ttu-id="c6f6b-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-109">Optional.</span></span> <span data-ttu-id="c6f6b-110">Especifique `-optioninfer+` para habilitar la inferencia de tipo de variable local o `-optioninfer-` para bloquearla.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="c6f6b-111">La opción `-optioninfer`, sin ningún valor especificado, es igual a `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="c6f6b-112">El valor predeterminado cuando el modificador `-optioninfer` no está presente también es `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="c6f6b-113">El valor predeterminado se establece en el archivo de respuesta vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c6f6b-114">Puede utilizar la opción `-noconfig` para conservar los valores predeterminados internos del compilador en lugar de los especificados en vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="c6f6b-115">El valor predeterminado del compilador para esta opción es `-optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6f6b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6f6b-116">Remarks</span></span>  
 <span data-ttu-id="c6f6b-117">Si el archivo de código fuente contiene una [instrucción Option Infer](../../language-reference/statements/option-infer-statement.md), la declaración reemplaza la configuración `-optioninfer` del compilador de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-117">If the source code file contains an [Option Infer Statement](../../language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="c6f6b-118">Para establecer -optioninfer en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c6f6b-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="c6f6b-119">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="c6f6b-120">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="c6f6b-121">En la pestaña **Compilar**, modifique el valor del cuadro **Option infer**.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6f6b-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6f6b-122">Example</span></span>  
 <span data-ttu-id="c6f6b-123">El siguiente código compila `test.vb` con la inferencia de tipo de variable local habilitada.</span><span class="sxs-lookup"><span data-stu-id="c6f6b-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6f6b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6f6b-124">See also</span></span>

- [<span data-ttu-id="c6f6b-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c6f6b-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c6f6b-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="c6f6b-126">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="c6f6b-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="c6f6b-127">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="c6f6b-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="c6f6b-128">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="c6f6b-129">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6f6b-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="c6f6b-130">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c6f6b-130">Option Infer Statement</span></span>](../../language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="c6f6b-131">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="c6f6b-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="c6f6b-132">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="c6f6b-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="c6f6b-133">Página Compilación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6f6b-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="c6f6b-134">-noconfig</span><span class="sxs-lookup"><span data-stu-id="c6f6b-134">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="c6f6b-135">Compilación desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="c6f6b-135">Building from the Command Line</span></span>](building-from-the-command-line.md)
