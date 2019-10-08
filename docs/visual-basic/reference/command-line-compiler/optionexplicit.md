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
ms.openlocfilehash: 5c0946b94bfe02d797d1a484088869375703eb6a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005311"
---
# <a name="-optionexplicit"></a><span data-ttu-id="25951-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="25951-102">-optionexplicit</span></span>
<span data-ttu-id="25951-103">Hace que el compilador notifique errores si las variables no se declaran antes de usarse.</span><span class="sxs-lookup"><span data-stu-id="25951-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25951-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25951-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="25951-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="25951-105">Arguments</span></span>  
 <span data-ttu-id="25951-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="25951-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="25951-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="25951-107">Optional.</span></span> <span data-ttu-id="25951-108">Especifique `-optionexplicit+` para requerir la declaración explícita de variables.</span><span class="sxs-lookup"><span data-stu-id="25951-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="25951-109">La opción `-optionexplicit+` es el valor predeterminado y es igual que `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="25951-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="25951-110">La opción `-optionexplicit-` habilita la declaración implícita de variables.</span><span class="sxs-lookup"><span data-stu-id="25951-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25951-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25951-111">Remarks</span></span>  
 <span data-ttu-id="25951-112">Si el archivo de código fuente contiene una [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), la instrucción reemplaza la configuración del compilador de línea de comandos `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="25951-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="25951-113">Para Set-OptionExplicit en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="25951-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="25951-114">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="25951-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="25951-115">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="25951-115">On the **Project** menu, click **Properties**.</span></span>   
  
2. <span data-ttu-id="25951-116">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="25951-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="25951-117">Modifique el valor en el cuadro **Option Explicit** .</span><span class="sxs-lookup"><span data-stu-id="25951-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25951-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25951-118">Example</span></span>  
 <span data-ttu-id="25951-119">El siguiente código se compila cuando se usa `-optionexplicit-`.</span><span class="sxs-lookup"><span data-stu-id="25951-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="25951-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="25951-120">See also</span></span>

- [<span data-ttu-id="25951-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25951-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="25951-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="25951-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="25951-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="25951-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="25951-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="25951-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="25951-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="25951-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="25951-126">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="25951-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="25951-127">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="25951-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
