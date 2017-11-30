---
title: "Mid (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61d812ef91acc65728b04efc9aa99e3975e71d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="mid-statement"></a><span data-ttu-id="651ea-102">Mid (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="651ea-102">Mid Statement</span></span>
<span data-ttu-id="651ea-103">Reemplaza un número especificado de caracteres de un `String` variable con caracteres de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="651ea-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="651ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="651ea-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="651ea-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="651ea-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="651ea-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="651ea-106">Required.</span></span> <span data-ttu-id="651ea-107">Nombre de la `String` variable va a modificar.</span><span class="sxs-lookup"><span data-stu-id="651ea-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="651ea-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="651ea-108">Required.</span></span> <span data-ttu-id="651ea-109">`Integer`expresión.</span><span class="sxs-lookup"><span data-stu-id="651ea-109">`Integer` expression.</span></span> <span data-ttu-id="651ea-110">Posición de carácter de `Target` donde comienza el reemplazo de texto.</span><span class="sxs-lookup"><span data-stu-id="651ea-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="651ea-111">`Start`utiliza un índice basado en uno.</span><span class="sxs-lookup"><span data-stu-id="651ea-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="651ea-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="651ea-112">Optional.</span></span> <span data-ttu-id="651ea-113">`Integer`expresión.</span><span class="sxs-lookup"><span data-stu-id="651ea-113">`Integer` expression.</span></span> <span data-ttu-id="651ea-114">Número de caracteres que se va a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="651ea-114">Number of characters to replace.</span></span> <span data-ttu-id="651ea-115">Si omite todos `String` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="651ea-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="651ea-116">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="651ea-116">Required.</span></span> <span data-ttu-id="651ea-117">`String`Expresión que reemplaza parte de `Target`.</span><span class="sxs-lookup"><span data-stu-id="651ea-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="651ea-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="651ea-118">Exceptions</span></span>  
  
|<span data-ttu-id="651ea-119">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="651ea-119">Exception type</span></span>|<span data-ttu-id="651ea-120">Condición</span><span class="sxs-lookup"><span data-stu-id="651ea-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="651ea-121">`Start`< = 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="651ea-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="651ea-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="651ea-122">Remarks</span></span>  
 <span data-ttu-id="651ea-123">El número de caracteres reemplazados siempre es menor o igual que el número de caracteres en `Target`.</span><span class="sxs-lookup"><span data-stu-id="651ea-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="651ea-124">Visual Basic ofrece un <xref:Microsoft.VisualBasic.Strings.Mid%2A> función y un `Mid` instrucción.</span><span class="sxs-lookup"><span data-stu-id="651ea-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="651ea-125">Estos elementos funcionan en un número especificado de caracteres de una cadena, pero la `Mid` función devuelve los caracteres mientras el `Mid` instrucción reemplaza los caracteres.</span><span class="sxs-lookup"><span data-stu-id="651ea-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="651ea-126">Para obtener más información, consulta <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="651ea-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="651ea-127">El `MidB` instrucción de versiones anteriores de Visual Basic reemplaza una subcadena en bytes, en lugar de caracteres.</span><span class="sxs-lookup"><span data-stu-id="651ea-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="651ea-128">Se usa principalmente para convertir cadenas en aplicaciones de caracteres de doble byte (DBCS).</span><span class="sxs-lookup"><span data-stu-id="651ea-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="651ea-129">Todas las cadenas de Visual Basic están en Unicode, y `MidB` ya no se admite.</span><span class="sxs-lookup"><span data-stu-id="651ea-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="651ea-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="651ea-130">Example</span></span>  
 <span data-ttu-id="651ea-131">Este ejemplo se utiliza la `Mid` instrucción para reemplazar un número especificado de caracteres de una variable de cadena con caracteres de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="651ea-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="651ea-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="651ea-132">Requirements</span></span>  
 <span data-ttu-id="651ea-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="651ea-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="651ea-134">**Módulo:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="651ea-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="651ea-135">**Ensamblado:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="651ea-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="651ea-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="651ea-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="651ea-137">Cadenas</span><span class="sxs-lookup"><span data-stu-id="651ea-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="651ea-138">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="651ea-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
