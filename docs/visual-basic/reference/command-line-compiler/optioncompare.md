---
description: Mas información sobre -optioncompare
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
ms.openlocfilehash: 9be4867c75cc16a8f699cf492dc41e9d08b96495
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475934"
---
# <a name="-optioncompare"></a><span data-ttu-id="7fbcd-103">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="7fbcd-103">-optioncompare</span></span>

<span data-ttu-id="7fbcd-104">Especifica la forma en que se realizan las comparaciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="7fbcd-104">Specifies how string comparisons are made.</span></span>

## <a name="syntax"></a><span data-ttu-id="7fbcd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fbcd-105">Syntax</span></span>

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a><span data-ttu-id="7fbcd-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7fbcd-106">Remarks</span></span>

<span data-ttu-id="7fbcd-107">Puede especificar `-optioncompare` de una de las dos formas siguientes: `-optioncompare:binary` para usar comparaciones de cadenas binarias y `-optioncompare:text` para usar comparaciones de cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="7fbcd-107">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="7fbcd-108">De forma predeterminada, el compilador utiliza `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="7fbcd-108">By default, the compiler uses `-optioncompare:binary`.</span></span>

<span data-ttu-id="7fbcd-109">En Microsoft Windows, la página de códigos actual determina el criterio de ordenación binario.</span><span class="sxs-lookup"><span data-stu-id="7fbcd-109">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="7fbcd-110">Un criterio de ordenación binario típico es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="7fbcd-110">A typical binary sort order is as follows:</span></span>

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

<span data-ttu-id="7fbcd-111">Las comparaciones de cadenas basadas en texto siguen un criterio de ordenación de texto sin distinción de mayúsculas y minúsculas determinado por la configuración regional del sistema.</span><span class="sxs-lookup"><span data-stu-id="7fbcd-111">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="7fbcd-112">Un criterio de ordenación de texto típico es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="7fbcd-112">A typical text sort order is as follows:</span></span>

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="7fbcd-113">Para establecer -optioncompare en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7fbcd-113">To set -optioncompare in the Visual Studio IDE</span></span>

1. <span data-ttu-id="7fbcd-114">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="7fbcd-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7fbcd-115">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7fbcd-115">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="7fbcd-116">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="7fbcd-116">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="7fbcd-117">Modifique el valor del cuadro **Option Compare**.</span><span class="sxs-lookup"><span data-stu-id="7fbcd-117">Modify the value in the **Option Compare** box.</span></span>

### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="7fbcd-118">Para establecer -optioncompare mediante programación</span><span class="sxs-lookup"><span data-stu-id="7fbcd-118">To set -optioncompare programmatically</span></span>

<span data-ttu-id="7fbcd-119">Consulte [Option Compare (instrucción)](../../language-reference/statements/option-compare-statement.md)</span><span class="sxs-lookup"><span data-stu-id="7fbcd-119">See [Option Compare Statement](../../language-reference/statements/option-compare-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="7fbcd-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7fbcd-120">Example</span></span>

<span data-ttu-id="7fbcd-121">El código siguiente compila `ProjFile.vb` y utiliza comparaciones de cadenas binarias.</span><span class="sxs-lookup"><span data-stu-id="7fbcd-121">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a><span data-ttu-id="7fbcd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fbcd-122">See also</span></span>

- [<span data-ttu-id="7fbcd-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7fbcd-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="7fbcd-124">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="7fbcd-124">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="7fbcd-125">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="7fbcd-125">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="7fbcd-126">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="7fbcd-126">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="7fbcd-127">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="7fbcd-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="7fbcd-128">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7fbcd-128">Option Compare Statement</span></span>](../../language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="7fbcd-129">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="7fbcd-129">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
