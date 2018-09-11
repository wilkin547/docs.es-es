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
ms.openlocfilehash: a653e63ded04616b6b0c6bdfb26a0a673d9299fc
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44277106"
---
# <a name="mid-statement"></a><span data-ttu-id="9a1d8-102">Mid (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="9a1d8-102">Mid Statement</span></span>
<span data-ttu-id="9a1d8-103">Reemplaza un número especificado de caracteres de un `String` variable por los caracteres de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a1d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a1d8-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="9a1d8-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="9a1d8-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="9a1d8-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-106">Required.</span></span> <span data-ttu-id="9a1d8-107">Nombre de la `String` variable va a modificar.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="9a1d8-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-108">Required.</span></span> <span data-ttu-id="9a1d8-109">`Integer` expresión.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-109">`Integer` expression.</span></span> <span data-ttu-id="9a1d8-110">Posición de carácter de `Target` donde comienza la sustitución de texto.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="9a1d8-111">`Start` utiliza un índice basado en uno.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="9a1d8-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-112">Optional.</span></span> <span data-ttu-id="9a1d8-113">`Integer` expresión.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-113">`Integer` expression.</span></span> <span data-ttu-id="9a1d8-114">Número de caracteres que se va a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-114">Number of characters to replace.</span></span> <span data-ttu-id="9a1d8-115">Si omite todos `String` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="9a1d8-116">Requerido.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-116">Required.</span></span> <span data-ttu-id="9a1d8-117">`String` Expresión que reemplaza parte de `Target`.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="9a1d8-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="9a1d8-118">Exceptions</span></span>  
  
|<span data-ttu-id="9a1d8-119">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="9a1d8-119">Exception type</span></span>|<span data-ttu-id="9a1d8-120">Condición</span><span class="sxs-lookup"><span data-stu-id="9a1d8-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="9a1d8-121">`Start` < = 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a1d8-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a1d8-122">Remarks</span></span>  
 <span data-ttu-id="9a1d8-123">El número de caracteres reemplazados siempre es menor o igual que el número de caracteres en `Target`.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="9a1d8-124">Visual Basic tiene un <xref:Microsoft.VisualBasic.Strings.Mid%2A> función y un `Mid` instrucción.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="9a1d8-125">Estos elementos funcionan en un número especificado de caracteres en una cadena, pero la `Mid` función devuelve los caracteres mientras el `Mid` instrucción reemplaza los caracteres.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="9a1d8-126">Para obtener más información, consulta <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a1d8-127">El `MidB` instrucción de versiones anteriores de Visual Basic reemplaza una subcadena en bytes, en lugar de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="9a1d8-128">Se utiliza principalmente para convertir cadenas en aplicaciones de caracteres de doble byte (DBCS).</span><span class="sxs-lookup"><span data-stu-id="9a1d8-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="9a1d8-129">Todas las cadenas en Visual Basic están en Unicode, y `MidB` ya no se admite.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a1d8-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a1d8-130">Example</span></span>  
 <span data-ttu-id="9a1d8-131">Este ejemplo se usa el `Mid` instrucción para reemplazar un número especificado de caracteres de una variable de cadena de caracteres de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="9a1d8-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="9a1d8-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a1d8-132">Requirements</span></span>  
 <span data-ttu-id="9a1d8-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="9a1d8-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="9a1d8-134">**Módulo:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="9a1d8-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="9a1d8-135">**Ensamblado:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a1d8-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1d8-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a1d8-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="9a1d8-137">Cadenas</span><span class="sxs-lookup"><span data-stu-id="9a1d8-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="9a1d8-138">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a1d8-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
