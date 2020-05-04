---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 37ccd14dae0ebba2535185f2646e312d9bb70390
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266734"
---
# <a name="-optionexplicit"></a><span data-ttu-id="443ea-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="443ea-102">-optionexplicit</span></span>
<span data-ttu-id="443ea-103">Hace que el compilador notifique errores si las variables no se declaran antes de usarlas.</span><span class="sxs-lookup"><span data-stu-id="443ea-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="443ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="443ea-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="443ea-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="443ea-105">Arguments</span></span>  
 <span data-ttu-id="443ea-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="443ea-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="443ea-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="443ea-107">Optional.</span></span> <span data-ttu-id="443ea-108">Especifique `-optionexplicit+` para requerir la declaración explícita de variables.</span><span class="sxs-lookup"><span data-stu-id="443ea-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="443ea-109">La opción `-optionexplicit+` es el valor predeterminado y es igual a `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="443ea-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="443ea-110">La opción `-optionexplicit-` habilita la declaración implícita de variables.</span><span class="sxs-lookup"><span data-stu-id="443ea-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="443ea-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="443ea-111">Remarks</span></span>  
 <span data-ttu-id="443ea-112">Si el archivo de código fuente contiene una [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), la declaración reemplaza el valor `-optionexplicit` del compilador de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="443ea-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="443ea-113">Para establecer -optionexplicit en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="443ea-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="443ea-114">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="443ea-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="443ea-115">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="443ea-115">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="443ea-116">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="443ea-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="443ea-117">Modifique el valor del cuadro **Option Explicit**.</span><span class="sxs-lookup"><span data-stu-id="443ea-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="443ea-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="443ea-118">Example</span></span>  
 <span data-ttu-id="443ea-119">El código siguiente se compila cuando se usa `-optionexplicit-`.</span><span class="sxs-lookup"><span data-stu-id="443ea-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="443ea-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="443ea-120">See also</span></span>

- [<span data-ttu-id="443ea-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="443ea-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="443ea-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="443ea-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="443ea-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="443ea-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="443ea-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="443ea-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="443ea-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="443ea-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="443ea-126">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="443ea-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="443ea-127">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="443ea-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
