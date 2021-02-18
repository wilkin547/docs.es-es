---
description: Mas información sobre -optionstrict
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: ad58c7775eaa77c1bf693629cf12cc70e4222920
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475908"
---
# <a name="-optionstrict"></a><span data-ttu-id="94b17-103">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="94b17-103">-optionstrict</span></span>

<span data-ttu-id="94b17-104">Exige la semántica estricta de tipos para restringir las conversiones implícitas de tipos.</span><span class="sxs-lookup"><span data-stu-id="94b17-104">Enforces strict type semantics to restrict implicit type conversions.</span></span>

## <a name="syntax"></a><span data-ttu-id="94b17-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94b17-105">Syntax</span></span>

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a><span data-ttu-id="94b17-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="94b17-106">Arguments</span></span>

<span data-ttu-id="94b17-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="94b17-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="94b17-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="94b17-108">Optional.</span></span> <span data-ttu-id="94b17-109">La opción `-optionstrict+` restringe la conversión de tipos implícita.</span><span class="sxs-lookup"><span data-stu-id="94b17-109">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="94b17-110">El valor predeterminado de esta opción es `-optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="94b17-110">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="94b17-111">La opción `-optionstrict+` equivale a `-optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="94b17-111">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="94b17-112">Puede usar las dos para la semántica de tipos permisiva.</span><span class="sxs-lookup"><span data-stu-id="94b17-112">You can use both for permissive type semantics.</span></span>

`custom`  
<span data-ttu-id="94b17-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="94b17-113">Required.</span></span> <span data-ttu-id="94b17-114">Advertir cuando no se respete la semántica estricta del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="94b17-114">Warn when strict language semantics are not respected.</span></span>

## <a name="remarks"></a><span data-ttu-id="94b17-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94b17-115">Remarks</span></span>

<span data-ttu-id="94b17-116">Cuando `-optionstrict+` está en vigor, solo se pueden realizar conversiones de ampliación de tipos de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="94b17-116">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="94b17-117">Las conversiones de restricción de tipos implícitas, como la asignación de un objeto de tipo `Decimal` a un objeto de tipo entero, se muestran como errores.</span><span class="sxs-lookup"><span data-stu-id="94b17-117">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>

<span data-ttu-id="94b17-118">Para generar advertencias para las conversiones de restricción de tipos implícitas, use `-optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="94b17-118">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="94b17-119">Use `-nowarn:numberlist` para omitir advertencias concretas y `-warnaserror:numberlist` para tratar las advertencias concretas como errores.</span><span class="sxs-lookup"><span data-stu-id="94b17-119">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="94b17-120">Para establecer -optionstrict en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94b17-120">To set -optionstrict in the Visual Studio IDE</span></span>

1. <span data-ttu-id="94b17-121">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="94b17-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="94b17-122">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="94b17-122">On the **Project** menu, click **Properties.**</span></span>

2. <span data-ttu-id="94b17-123">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="94b17-123">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="94b17-124">Modifique el valor del cuadro **Option Strict**.</span><span class="sxs-lookup"><span data-stu-id="94b17-124">Modify the value in the **Option Strict** box.</span></span>

### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="94b17-125">Para establecer -optionstrict mediante programación</span><span class="sxs-lookup"><span data-stu-id="94b17-125">To set -optionstrict programmatically</span></span>

<span data-ttu-id="94b17-126">Vea [Option Strict (instrucción)](../../language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="94b17-126">See [Option Strict Statement](../../language-reference/statements/option-strict-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="94b17-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94b17-127">Example</span></span>

<span data-ttu-id="94b17-128">El código siguiente compila `Test.vb` mediante la semántica estricta de tipos.</span><span class="sxs-lookup"><span data-stu-id="94b17-128">The following code compiles `Test.vb` using strict type semantics.</span></span>

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a><span data-ttu-id="94b17-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="94b17-129">See also</span></span>

- [<span data-ttu-id="94b17-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94b17-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="94b17-131">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="94b17-131">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="94b17-132">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="94b17-132">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="94b17-133">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="94b17-133">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="94b17-134">-nowarn</span><span class="sxs-lookup"><span data-stu-id="94b17-134">-nowarn</span></span>](nowarn.md)
- [<span data-ttu-id="94b17-135">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94b17-135">-warnaserror (Visual Basic)</span></span>](warnaserror.md)
- [<span data-ttu-id="94b17-136">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="94b17-136">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="94b17-137">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="94b17-137">Option Strict Statement</span></span>](../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="94b17-138">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="94b17-138">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
