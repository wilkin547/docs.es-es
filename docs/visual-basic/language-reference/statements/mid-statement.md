---
title: Mid (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: ee0f2e771a938619bf988263b176464080e60e7a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974840"
---
# <a name="mid-statement"></a><span data-ttu-id="2c070-102">Mid (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="2c070-102">Mid Statement</span></span>
<span data-ttu-id="2c070-103">Reemplaza un número especificado de caracteres de un `String` variable por los caracteres de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="2c070-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c070-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c070-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="2c070-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="2c070-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="2c070-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2c070-106">Required.</span></span> <span data-ttu-id="2c070-107">Nombre de la `String` variable va a modificar.</span><span class="sxs-lookup"><span data-stu-id="2c070-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="2c070-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2c070-108">Required.</span></span> <span data-ttu-id="2c070-109">`Integer` expresión.</span><span class="sxs-lookup"><span data-stu-id="2c070-109">`Integer` expression.</span></span> <span data-ttu-id="2c070-110">Posición de carácter de `Target` donde comienza la sustitución de texto.</span><span class="sxs-lookup"><span data-stu-id="2c070-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="2c070-111">`Start` utiliza un índice basado en uno.</span><span class="sxs-lookup"><span data-stu-id="2c070-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="2c070-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2c070-112">Optional.</span></span> <span data-ttu-id="2c070-113">`Integer` expresión.</span><span class="sxs-lookup"><span data-stu-id="2c070-113">`Integer` expression.</span></span> <span data-ttu-id="2c070-114">Número de caracteres que se va a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="2c070-114">Number of characters to replace.</span></span> <span data-ttu-id="2c070-115">Si omite todos `String` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="2c070-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="2c070-116">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2c070-116">Required.</span></span> <span data-ttu-id="2c070-117">`String` Expresión que reemplaza parte de `Target`.</span><span class="sxs-lookup"><span data-stu-id="2c070-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="2c070-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="2c070-118">Exceptions</span></span>  
  
|<span data-ttu-id="2c070-119">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="2c070-119">Exception type</span></span>|<span data-ttu-id="2c070-120">Condición</span><span class="sxs-lookup"><span data-stu-id="2c070-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="2c070-121">`Start` < = 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="2c070-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c070-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c070-122">Remarks</span></span>  
 <span data-ttu-id="2c070-123">El número de caracteres reemplazados siempre es menor o igual que el número de caracteres en `Target`.</span><span class="sxs-lookup"><span data-stu-id="2c070-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="2c070-124">Visual Basic tiene un <xref:Microsoft.VisualBasic.Strings.Mid%2A> función y un `Mid` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2c070-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="2c070-125">Estos elementos funcionan en un número especificado de caracteres en una cadena, pero la `Mid` función devuelve los caracteres mientras el `Mid` instrucción reemplaza los caracteres.</span><span class="sxs-lookup"><span data-stu-id="2c070-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="2c070-126">Para obtener más información, consulta <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="2c070-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c070-127">El `MidB` instrucción de versiones anteriores de Visual Basic reemplaza una subcadena en bytes, en lugar de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2c070-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="2c070-128">Se utiliza principalmente para convertir cadenas en aplicaciones de caracteres de doble byte (DBCS).</span><span class="sxs-lookup"><span data-stu-id="2c070-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="2c070-129">Todas las cadenas en Visual Basic están en Unicode, y `MidB` ya no se admite.</span><span class="sxs-lookup"><span data-stu-id="2c070-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c070-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c070-130">Example</span></span>  
 <span data-ttu-id="2c070-131">Este ejemplo se usa el `Mid` instrucción para reemplazar un número especificado de caracteres de una variable de cadena de caracteres de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="2c070-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="2c070-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c070-132">Requirements</span></span>  
 <span data-ttu-id="2c070-133">**Espacio de nombres**: [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="2c070-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="2c070-134">**Módulo:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="2c070-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="2c070-135">**Ensamblado:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c070-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c070-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c070-136">See also</span></span>
- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="2c070-137">Cadenas</span><span class="sxs-lookup"><span data-stu-id="2c070-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="2c070-138">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c070-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
