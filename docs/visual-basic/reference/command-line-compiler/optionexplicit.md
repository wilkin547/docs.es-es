---
description: Mas información sobre -optionexplicit
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
ms.openlocfilehash: 4d1ab14bbf9de176de17fb5077f4bb919f5472b4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433567"
---
# <a name="-optionexplicit"></a><span data-ttu-id="30a97-103">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="30a97-103">-optionexplicit</span></span>

<span data-ttu-id="30a97-104">Hace que el compilador notifique errores si las variables no se declaran antes de usarlas.</span><span class="sxs-lookup"><span data-stu-id="30a97-104">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a97-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30a97-105">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="30a97-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="30a97-106">Arguments</span></span>  

 <span data-ttu-id="30a97-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="30a97-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="30a97-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="30a97-108">Optional.</span></span> <span data-ttu-id="30a97-109">Especifique `-optionexplicit+` para requerir la declaración explícita de variables.</span><span class="sxs-lookup"><span data-stu-id="30a97-109">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="30a97-110">La opción `-optionexplicit+` es el valor predeterminado y es igual a `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="30a97-110">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="30a97-111">La opción `-optionexplicit-` habilita la declaración implícita de variables.</span><span class="sxs-lookup"><span data-stu-id="30a97-111">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30a97-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30a97-112">Remarks</span></span>  

 <span data-ttu-id="30a97-113">Si el archivo de código fuente contiene una [instrucción Option Explicit](../../language-reference/statements/option-explicit-statement.md), la declaración reemplaza el valor `-optionexplicit` del compilador de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="30a97-113">If the source code file contains an [Option Explicit statement](../../language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="30a97-114">Para establecer -optionexplicit en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="30a97-114">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="30a97-115">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="30a97-115">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="30a97-116">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="30a97-116">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="30a97-117">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="30a97-117">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="30a97-118">Modifique el valor del cuadro **Option Explicit**.</span><span class="sxs-lookup"><span data-stu-id="30a97-118">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30a97-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30a97-119">Example</span></span>  

 <span data-ttu-id="30a97-120">El código siguiente se compila cuando se usa `-optionexplicit-`.</span><span class="sxs-lookup"><span data-stu-id="30a97-120">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="30a97-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="30a97-121">See also</span></span>

- [<span data-ttu-id="30a97-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="30a97-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="30a97-123">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="30a97-123">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="30a97-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="30a97-124">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="30a97-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="30a97-125">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="30a97-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="30a97-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="30a97-127">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="30a97-127">Option Explicit Statement</span></span>](../../language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="30a97-128">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="30a97-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
