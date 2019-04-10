---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: e18fe451ea4a80ac959ed61b66394920f8bf177f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336088"
---
# <a name="-optionstrict"></a><span data-ttu-id="4d630-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="4d630-102">-optionstrict</span></span>
<span data-ttu-id="4d630-103">Exige la semántica estricta de tipos para restringir las conversiones implícitas.</span><span class="sxs-lookup"><span data-stu-id="4d630-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d630-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d630-104">Syntax</span></span>  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4d630-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4d630-105">Arguments</span></span>  
 `+` <span data-ttu-id="4d630-106">&#124;</span><span class="sxs-lookup"><span data-stu-id="4d630-106">&#124;</span></span> `-`  
 <span data-ttu-id="4d630-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4d630-107">Optional.</span></span> <span data-ttu-id="4d630-108">El `-optionstrict+` opción restringe la conversión de tipos implícita.</span><span class="sxs-lookup"><span data-stu-id="4d630-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="4d630-109">El valor predeterminado para esta opción es `-optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="4d630-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="4d630-110">El `-optionstrict+` opción es igual a `-optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="4d630-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="4d630-111">Puede usar tanto para la semántica de tipos permisiva.</span><span class="sxs-lookup"><span data-stu-id="4d630-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="4d630-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4d630-112">Required.</span></span> <span data-ttu-id="4d630-113">Advertir cuando no se respete la semántica estricta del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="4d630-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d630-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d630-114">Remarks</span></span>  
 <span data-ttu-id="4d630-115">Cuando `-optionstrict+` está en vigor, se pueden realizar solo las conversiones de tipo de ampliación implícitamente.</span><span class="sxs-lookup"><span data-stu-id="4d630-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="4d630-116">Conversiones de tipos, como la asignación de restricción implícitas un `Decimal` tipo object para un objeto de tipo entero, se notifican como errores.</span><span class="sxs-lookup"><span data-stu-id="4d630-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="4d630-117">Para generar advertencias para las conversiones de tipo de restricción implícitas, use `-optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="4d630-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="4d630-118">Use `-nowarn:numberlist` para ignorar las advertencias determinadas y `-warnaserror:numberlist` para tratar determinadas advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="4d630-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="4d630-119">Para establecer - optionstrict en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4d630-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="4d630-120">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="4d630-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4d630-121">En el **proyecto** menú, haga clic en **propiedades.**</span><span class="sxs-lookup"><span data-stu-id="4d630-121">On the **Project** menu, click **Properties.**</span></span>   
  
2. <span data-ttu-id="4d630-122">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="4d630-122">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="4d630-123">Modifique el valor en el **Option Strict** cuadro.</span><span class="sxs-lookup"><span data-stu-id="4d630-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="4d630-124">Para establecer mediante programación - optionstrict</span><span class="sxs-lookup"><span data-stu-id="4d630-124">To set -optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="4d630-125">Consulte [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4d630-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d630-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d630-126">Example</span></span>  
 <span data-ttu-id="4d630-127">El siguiente código compila `Test.vb` utilizando la semántica estricta de tipos.</span><span class="sxs-lookup"><span data-stu-id="4d630-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d630-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d630-128">See also</span></span>

- [<span data-ttu-id="4d630-129">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d630-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4d630-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="4d630-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="4d630-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="4d630-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="4d630-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="4d630-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="4d630-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="4d630-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="4d630-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d630-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="4d630-135">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d630-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="4d630-136">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="4d630-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="4d630-137">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="4d630-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
