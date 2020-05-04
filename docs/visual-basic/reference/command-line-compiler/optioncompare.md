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
ms.openlocfilehash: ac385880f8c13c23dffff67fc2a1ecc5609fd189
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581414"
---
# <a name="-optioncompare"></a><span data-ttu-id="ccf02-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="ccf02-102">-optioncompare</span></span>

<span data-ttu-id="ccf02-103">Especifica la forma en que se realizan las comparaciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="ccf02-103">Specifies how string comparisons are made.</span></span>

## <a name="syntax"></a><span data-ttu-id="ccf02-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccf02-104">Syntax</span></span>

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a><span data-ttu-id="ccf02-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ccf02-105">Remarks</span></span>

<span data-ttu-id="ccf02-106">Puede especificar `-optioncompare` de una de las dos formas siguientes: `-optioncompare:binary` para usar comparaciones de cadenas binarias y `-optioncompare:text` para usar comparaciones de cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="ccf02-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="ccf02-107">De forma predeterminada, el compilador utiliza `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="ccf02-107">By default, the compiler uses `-optioncompare:binary`.</span></span>

<span data-ttu-id="ccf02-108">En Microsoft Windows, la página de códigos actual determina el criterio de ordenación binario.</span><span class="sxs-lookup"><span data-stu-id="ccf02-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="ccf02-109">Un criterio de ordenación binario típico es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="ccf02-109">A typical binary sort order is as follows:</span></span>

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

<span data-ttu-id="ccf02-110">Las comparaciones de cadenas basadas en texto siguen un criterio de ordenación de texto sin distinción de mayúsculas y minúsculas determinado por la configuración regional del sistema.</span><span class="sxs-lookup"><span data-stu-id="ccf02-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="ccf02-111">Un criterio de ordenación de texto típico es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="ccf02-111">A typical text sort order is as follows:</span></span>

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="ccf02-112">Para establecer -optioncompare en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ccf02-112">To set -optioncompare in the Visual Studio IDE</span></span>

1. <span data-ttu-id="ccf02-113">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="ccf02-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ccf02-114">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ccf02-114">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="ccf02-115">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="ccf02-115">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="ccf02-116">Modifique el valor del cuadro **Option Compare**.</span><span class="sxs-lookup"><span data-stu-id="ccf02-116">Modify the value in the **Option Compare** box.</span></span>

### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="ccf02-117">Para establecer -optioncompare mediante programación</span><span class="sxs-lookup"><span data-stu-id="ccf02-117">To set -optioncompare programmatically</span></span>

<span data-ttu-id="ccf02-118">Consulte [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md)</span><span class="sxs-lookup"><span data-stu-id="ccf02-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="ccf02-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccf02-119">Example</span></span>

<span data-ttu-id="ccf02-120">El código siguiente compila `ProjFile.vb` y utiliza comparaciones de cadenas binarias.</span><span class="sxs-lookup"><span data-stu-id="ccf02-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a><span data-ttu-id="ccf02-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccf02-121">See also</span></span>

- [<span data-ttu-id="ccf02-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ccf02-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ccf02-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="ccf02-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="ccf02-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="ccf02-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="ccf02-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="ccf02-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="ccf02-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccf02-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="ccf02-127">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ccf02-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="ccf02-128">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="ccf02-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
