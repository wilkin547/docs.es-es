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
ms.openlocfilehash: 469e22aef9d746fc55e04ba884d17d60d8baa85a
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583072"
---
# <a name="-optionstrict"></a><span data-ttu-id="a3b12-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="a3b12-102">-optionstrict</span></span>

<span data-ttu-id="a3b12-103">Aplica la semántica estricta de tipos para restringir las conversiones de tipos implícitas.</span><span class="sxs-lookup"><span data-stu-id="a3b12-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>

## <a name="syntax"></a><span data-ttu-id="a3b12-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3b12-104">Syntax</span></span>

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a><span data-ttu-id="a3b12-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a3b12-105">Arguments</span></span>

<span data-ttu-id="a3b12-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a3b12-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="a3b12-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a3b12-107">Optional.</span></span> <span data-ttu-id="a3b12-108">La opción `-optionstrict+` restringe la conversión implícita de tipos.</span><span class="sxs-lookup"><span data-stu-id="a3b12-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="a3b12-109">El valor predeterminado para esta opción es `-optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="a3b12-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="a3b12-110">La opción `-optionstrict+` es la misma que la `-optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="a3b12-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="a3b12-111">Puede usar ambos para la semántica de tipos permisiva.</span><span class="sxs-lookup"><span data-stu-id="a3b12-111">You can use both for permissive type semantics.</span></span>

`custom`  
<span data-ttu-id="a3b12-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="a3b12-112">Required.</span></span> <span data-ttu-id="a3b12-113">Advertir cuando no se respete la semántica estricta del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="a3b12-113">Warn when strict language semantics are not respected.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3b12-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3b12-114">Remarks</span></span>

<span data-ttu-id="a3b12-115">Cuando `-optionstrict+` está en vigor, solo se pueden realizar implícitamente conversiones de tipos de ampliación.</span><span class="sxs-lookup"><span data-stu-id="a3b12-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="a3b12-116">Las conversiones de tipos de restricción implícitas, como la asignación de un objeto de tipo `Decimal` a un objeto de tipo entero, se muestran como errores.</span><span class="sxs-lookup"><span data-stu-id="a3b12-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>

<span data-ttu-id="a3b12-117">Para generar advertencias para las conversiones de tipos de restricción implícitas, use `-optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="a3b12-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="a3b12-118">Use `-nowarn:numberlist` para omitir advertencias concretas y `-warnaserror:numberlist` para tratar advertencias concretas como errores.</span><span class="sxs-lookup"><span data-stu-id="a3b12-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="a3b12-119">Para Set-OptionStrict en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a3b12-119">To set -optionstrict in the Visual Studio IDE</span></span>

1. <span data-ttu-id="a3b12-120">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a3b12-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a3b12-121">En el menú **proyecto** , haga clic en **propiedades.**</span><span class="sxs-lookup"><span data-stu-id="a3b12-121">On the **Project** menu, click **Properties.**</span></span>

2. <span data-ttu-id="a3b12-122">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="a3b12-122">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="a3b12-123">Modifique el valor en el cuadro **Option Strict** .</span><span class="sxs-lookup"><span data-stu-id="a3b12-123">Modify the value in the **Option Strict** box.</span></span>

### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="a3b12-124">Para establecer-OptionStrict mediante programación</span><span class="sxs-lookup"><span data-stu-id="a3b12-124">To set -optionstrict programmatically</span></span>

<span data-ttu-id="a3b12-125">Consulte [Option Strict (instrucción](../../../visual-basic/language-reference/statements/option-strict-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="a3b12-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="a3b12-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3b12-126">Example</span></span>

<span data-ttu-id="a3b12-127">El código siguiente compila `Test.vb` mediante la semántica estricta de tipos.</span><span class="sxs-lookup"><span data-stu-id="a3b12-127">The following code compiles `Test.vb` using strict type semantics.</span></span>

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a><span data-ttu-id="a3b12-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3b12-128">See also</span></span>

- [<span data-ttu-id="a3b12-129">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3b12-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a3b12-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="a3b12-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="a3b12-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="a3b12-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="a3b12-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="a3b12-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="a3b12-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="a3b12-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="a3b12-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3b12-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="a3b12-135">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3b12-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="a3b12-136">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a3b12-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="a3b12-137">Valores predeterminados de Visual Basic, Proyectos, Cuadro de diálogo Opciones</span><span class="sxs-lookup"><span data-stu-id="a3b12-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
