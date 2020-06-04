---
title: Option Compare (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Compare
- vb.OptionCompare
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword [Visual Basic]
- binary comparison [Visual Basic]
- strings [Visual Basic], returning from functions
- binary comparison [Visual Basic], Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword [Visual Basic], Option Compare statement
- Binary keyword [Visual Basic], Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement [Visual Basic]
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
ms.openlocfilehash: 1ffe3e45a296d02364f488540d987d85133013bd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404387"
---
# <a name="option-compare-statement"></a><span data-ttu-id="029c0-102">Option Compare (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="029c0-102">Option Compare Statement</span></span>
<span data-ttu-id="029c0-103">Declara el método de comparación predeterminado que se utiliza al comparar datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="029c0-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="029c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="029c0-104">Syntax</span></span>  
  
```vb  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="029c0-105">Partes</span><span class="sxs-lookup"><span data-stu-id="029c0-105">Parts</span></span>  
  
|<span data-ttu-id="029c0-106">Término</span><span class="sxs-lookup"><span data-stu-id="029c0-106">Term</span></span>|<span data-ttu-id="029c0-107">Definición</span><span class="sxs-lookup"><span data-stu-id="029c0-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="029c0-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="029c0-108">Optional.</span></span> <span data-ttu-id="029c0-109">Genera comparaciones de cadenas basadas en un criterio de ordenación que se deriva de las representaciones binarias internas de los caracteres.</span><span class="sxs-lookup"><span data-stu-id="029c0-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="029c0-110">Este tipo de comparación es especialmente útil si las cadenas pueden contener caracteres que no serán interpretados como texto.</span><span class="sxs-lookup"><span data-stu-id="029c0-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="029c0-111">En este caso, no conviene desviar las comparaciones con equivalencias alfabéticas, como la no distinción entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="029c0-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="029c0-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="029c0-112">Optional.</span></span> <span data-ttu-id="029c0-113">Genera comparaciones de cadenas basadas en un criterio de ordenación de texto sin distinción entre mayúsculas y minúsculas, determinado por la configuración regional del sistema.</span><span class="sxs-lookup"><span data-stu-id="029c0-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="029c0-114">Este tipo de comparación es útil si las cadenas contienen todos los caracteres de texto y si desea compararlas teniendo en cuenta equivalencias alfabéticas, como la no distinción entre mayúsculas y minúsculas y las letras estrechamente relacionadas.</span><span class="sxs-lookup"><span data-stu-id="029c0-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="029c0-115">Por ejemplo, tal vez le interese considerar que `A` y `a` son iguales, y que `Ä` y `ä` van antes que `B` y `b`.</span><span class="sxs-lookup"><span data-stu-id="029c0-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="029c0-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="029c0-116">Remarks</span></span>  
 <span data-ttu-id="029c0-117">Si se utiliza la instrucción `Option Compare`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.</span><span class="sxs-lookup"><span data-stu-id="029c0-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="029c0-118">La instrucción `Option Compare` especifica el método de comparación de cadenas (`Binary` o `Text`).</span><span class="sxs-lookup"><span data-stu-id="029c0-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="029c0-119">El método de comparación de texto predeterminado es `Binary`.</span><span class="sxs-lookup"><span data-stu-id="029c0-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="029c0-120">Una comparación `Binary` compara el valor numérico de Unicode de cada carácter en cada cadena.</span><span class="sxs-lookup"><span data-stu-id="029c0-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="029c0-121">Una comparación `Text` compara cada carácter Unicode basándose en su significado léxico en la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="029c0-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="029c0-122">En Microsoft Windows, el criterio de ordenación viene determinado por la página de código.</span><span class="sxs-lookup"><span data-stu-id="029c0-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="029c0-123">Para obtener más información, vea [Páginas de códigos](/cpp/c-runtime-library/code-pages).</span><span class="sxs-lookup"><span data-stu-id="029c0-123">For more information, see [Code Pages](/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="029c0-124">En el ejemplo siguiente, los caracteres de la página de códigos inglés/europeo (ANSI 1252) se ordenan mediante el uso de `Option Compare Binary`, lo que genera un criterio de ordenación binario típico.</span><span class="sxs-lookup"><span data-stu-id="029c0-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="029c0-125">Cuando se ordenan los mismos caracteres en la misma página de código mediante el uso de `Option Compare Text`, se genera el siguiente criterio de ordenación de texto.</span><span class="sxs-lookup"><span data-stu-id="029c0-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="029c0-126">Cuando la instrucción Option Compare no está presente</span><span class="sxs-lookup"><span data-stu-id="029c0-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="029c0-127">Si el código fuente no contiene una `Option Compare` instrucción, se utiliza el valor **Option Compare** en la [Página compilar, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) .</span><span class="sxs-lookup"><span data-stu-id="029c0-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="029c0-128">Si usa el compilador de línea de comandos, se usa el valor especificado por la opción del compilador [-optioncompare (](../../reference/command-line-compiler/optioncompare.md) .</span><span class="sxs-lookup"><span data-stu-id="029c0-128">If you use the command-line compiler, the setting specified by the [-optioncompare](../../reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="029c0-129">Cómo establecer Option Compare en el IDE</span><span class="sxs-lookup"><span data-stu-id="029c0-129">To set Option Compare in the IDE</span></span>  
  
1. <span data-ttu-id="029c0-130">En **Explorador de soluciones**, seleccione un proyecto.</span><span class="sxs-lookup"><span data-stu-id="029c0-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="029c0-131">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="029c0-131">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="029c0-132">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="029c0-132">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="029c0-133">Establezca el valor en el cuadro **Option Compare** .</span><span class="sxs-lookup"><span data-stu-id="029c0-133">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="029c0-134">Al crear un proyecto, el valor **Option Compare** de la pestaña **compilar** se establece en el valor **Option Compare** del cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="029c0-134">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="029c0-135">Para cambiar esta configuración, en el menú **herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="029c0-135">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="029c0-136">En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**.</span><span class="sxs-lookup"><span data-stu-id="029c0-136">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="029c0-137">La configuración predeterminada inicial en los **valores predeterminados de VB** es **binaria**.</span><span class="sxs-lookup"><span data-stu-id="029c0-137">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="029c0-138">Cómo establecer Option Compare en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="029c0-138">To set Option Compare on the command line</span></span>  
  
- <span data-ttu-id="029c0-139">Incluya la opción del compilador [-optioncompare (](../../reference/command-line-compiler/optioncompare.md) en el comando **VBC** .</span><span class="sxs-lookup"><span data-stu-id="029c0-139">Include the [-optioncompare](../../reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="029c0-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="029c0-140">Example</span></span>  
 <span data-ttu-id="029c0-141">El ejemplo siguiente utiliza la instrucción `Option Compare` para establecer la comparación binaria como método predeterminado de comparación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="029c0-141">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="029c0-142">Para utilizar este código, quite el comentario de la instrucción `Option Compare Binary` y colóquelo en la parte superior del archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="029c0-142">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#45)]  
  
## <a name="example"></a><span data-ttu-id="029c0-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="029c0-143">Example</span></span>  
 <span data-ttu-id="029c0-144">El ejemplo siguiente se utiliza la instrucción `Option Compare` para establecer el criterio de ordenación de texto sin distinción entre mayúsculas y minúsculas como método predeterminado de comparación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="029c0-144">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="029c0-145">Para utilizar este código, quite el comentario de la instrucción `Option Compare Text` y colóquelo en la parte superior del archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="029c0-145">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="029c0-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="029c0-146">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>
- <xref:Microsoft.VisualBasic.Strings.Replace%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="029c0-147">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="029c0-147">-optioncompare</span></span>](../../reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="029c0-148">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="029c0-148">Comparison Operators</span></span>](../operators/comparison-operators.md)
- [<span data-ttu-id="029c0-149">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="029c0-149">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="029c0-150">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="029c0-150">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="029c0-151">Funciones de cadena</span><span class="sxs-lookup"><span data-stu-id="029c0-151">String Functions</span></span>](../functions/string-functions.md)
- [<span data-ttu-id="029c0-152">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="029c0-152">Option Explicit Statement</span></span>](option-explicit-statement.md)
- [<span data-ttu-id="029c0-153">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="029c0-153">Option Strict Statement</span></span>](option-strict-statement.md)
