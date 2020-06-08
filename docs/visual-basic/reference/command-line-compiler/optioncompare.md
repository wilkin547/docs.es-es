---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: ed9adc7cddd9eb204937b9819e4eeff176821e95
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400568"
---
# <a name="-optioncompare"></a><span data-ttu-id="2ba7d-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="2ba7d-102">-optioncompare</span></span>

<span data-ttu-id="2ba7d-103">Especifica la forma en que se realizan las comparaciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="2ba7d-103">Specifies how string comparisons are made.</span></span>

## <a name="syntax"></a><span data-ttu-id="2ba7d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ba7d-104">Syntax</span></span>

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a><span data-ttu-id="2ba7d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ba7d-105">Remarks</span></span>

<span data-ttu-id="2ba7d-106">Puede especificar `-optioncompare` de una de las dos formas siguientes: `-optioncompare:binary` para usar comparaciones de cadenas binarias y `-optioncompare:text` para usar comparaciones de cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="2ba7d-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="2ba7d-107">De forma predeterminada, el compilador utiliza `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="2ba7d-107">By default, the compiler uses `-optioncompare:binary`.</span></span>

<span data-ttu-id="2ba7d-108">En Microsoft Windows, la página de códigos actual determina el criterio de ordenación binario.</span><span class="sxs-lookup"><span data-stu-id="2ba7d-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="2ba7d-109">Un criterio de ordenación binario típico es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ba7d-109">A typical binary sort order is as follows:</span></span>

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

<span data-ttu-id="2ba7d-110">Las comparaciones de cadenas basadas en texto siguen un criterio de ordenación de texto sin distinción de mayúsculas y minúsculas determinado por la configuración regional del sistema.</span><span class="sxs-lookup"><span data-stu-id="2ba7d-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="2ba7d-111">Un criterio de ordenación de texto típico es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ba7d-111">A typical text sort order is as follows:</span></span>

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="2ba7d-112">Para establecer -optioncompare en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2ba7d-112">To set -optioncompare in the Visual Studio IDE</span></span>

1. <span data-ttu-id="2ba7d-113">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="2ba7d-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2ba7d-114">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2ba7d-114">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="2ba7d-115">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="2ba7d-115">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="2ba7d-116">Modifique el valor del cuadro **Option Compare**.</span><span class="sxs-lookup"><span data-stu-id="2ba7d-116">Modify the value in the **Option Compare** box.</span></span>

### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="2ba7d-117">Para establecer -optioncompare mediante programación</span><span class="sxs-lookup"><span data-stu-id="2ba7d-117">To set -optioncompare programmatically</span></span>

<span data-ttu-id="2ba7d-118">Consulte [Option Compare (instrucción)](../../language-reference/statements/option-compare-statement.md)</span><span class="sxs-lookup"><span data-stu-id="2ba7d-118">See [Option Compare Statement](../../language-reference/statements/option-compare-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="2ba7d-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ba7d-119">Example</span></span>

<span data-ttu-id="2ba7d-120">El código siguiente compila `ProjFile.vb` y utiliza comparaciones de cadenas binarias.</span><span class="sxs-lookup"><span data-stu-id="2ba7d-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a><span data-ttu-id="2ba7d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ba7d-121">See also</span></span>

- [<span data-ttu-id="2ba7d-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ba7d-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="2ba7d-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="2ba7d-123">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="2ba7d-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="2ba7d-124">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="2ba7d-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="2ba7d-125">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="2ba7d-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ba7d-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="2ba7d-127">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2ba7d-127">Option Compare Statement</span></span>](../../language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="2ba7d-128">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="2ba7d-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
