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
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583072"
---
# <a name="-optionstrict"></a><span data-ttu-id="16298-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="16298-102">-optionstrict</span></span>

<span data-ttu-id="16298-103">Exige la semántica estricta de tipos para restringir las conversiones implícitas de tipos.</span><span class="sxs-lookup"><span data-stu-id="16298-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>

## <a name="syntax"></a><span data-ttu-id="16298-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16298-104">Syntax</span></span>

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a><span data-ttu-id="16298-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="16298-105">Arguments</span></span>

<span data-ttu-id="16298-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="16298-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="16298-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="16298-107">Optional.</span></span> <span data-ttu-id="16298-108">La opción `-optionstrict+` restringe la conversión de tipos implícita.</span><span class="sxs-lookup"><span data-stu-id="16298-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="16298-109">El valor predeterminado de esta opción es `-optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="16298-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="16298-110">La opción `-optionstrict+` equivale a `-optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="16298-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="16298-111">Puede usar las dos para la semántica de tipos permisiva.</span><span class="sxs-lookup"><span data-stu-id="16298-111">You can use both for permissive type semantics.</span></span>

`custom`  
<span data-ttu-id="16298-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="16298-112">Required.</span></span> <span data-ttu-id="16298-113">Advertir cuando no se respete la semántica estricta del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="16298-113">Warn when strict language semantics are not respected.</span></span>

## <a name="remarks"></a><span data-ttu-id="16298-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16298-114">Remarks</span></span>

<span data-ttu-id="16298-115">Cuando `-optionstrict+` está en vigor, solo se pueden realizar conversiones de ampliación de tipos de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="16298-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="16298-116">Las conversiones de restricción de tipos implícitas, como la asignación de un objeto de tipo `Decimal` a un objeto de tipo entero, se muestran como errores.</span><span class="sxs-lookup"><span data-stu-id="16298-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>

<span data-ttu-id="16298-117">Para generar advertencias para las conversiones de restricción de tipos implícitas, use `-optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="16298-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="16298-118">Use `-nowarn:numberlist` para omitir advertencias concretas y `-warnaserror:numberlist` para tratar las advertencias concretas como errores.</span><span class="sxs-lookup"><span data-stu-id="16298-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="16298-119">Para establecer -optionstrict en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="16298-119">To set -optionstrict in the Visual Studio IDE</span></span>

1. <span data-ttu-id="16298-120">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="16298-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="16298-121">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="16298-121">On the **Project** menu, click **Properties.**</span></span>

2. <span data-ttu-id="16298-122">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="16298-122">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="16298-123">Modifique el valor del cuadro **Option Strict**.</span><span class="sxs-lookup"><span data-stu-id="16298-123">Modify the value in the **Option Strict** box.</span></span>

### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="16298-124">Para establecer -optionstrict mediante programación</span><span class="sxs-lookup"><span data-stu-id="16298-124">To set -optionstrict programmatically</span></span>

<span data-ttu-id="16298-125">Vea [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="16298-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="16298-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16298-126">Example</span></span>

<span data-ttu-id="16298-127">El código siguiente compila `Test.vb` mediante la semántica estricta de tipos.</span><span class="sxs-lookup"><span data-stu-id="16298-127">The following code compiles `Test.vb` using strict type semantics.</span></span>

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a><span data-ttu-id="16298-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="16298-128">See also</span></span>

- [<span data-ttu-id="16298-129">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16298-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="16298-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="16298-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="16298-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="16298-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="16298-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="16298-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="16298-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="16298-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="16298-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16298-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="16298-135">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="16298-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="16298-136">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="16298-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="16298-137">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="16298-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
