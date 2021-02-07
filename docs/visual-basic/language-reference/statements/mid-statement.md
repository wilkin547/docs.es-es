---
description: 'Más información acerca de: instrucción MID'
title: Mid (Instrucción)
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
ms.openlocfilehash: 29cf933cb38fc6ef831570d0940b481abf9cfecf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768888"
---
# <a name="mid-statement"></a><span data-ttu-id="e45f4-103">Mid (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="e45f4-103">Mid Statement</span></span>

<span data-ttu-id="e45f4-104">Reemplaza un número especificado de caracteres de una `String` variable por caracteres de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="e45f4-104">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e45f4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e45f4-105">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="e45f4-106">Partes</span><span class="sxs-lookup"><span data-stu-id="e45f4-106">Parts</span></span>  

 `Target`  
 <span data-ttu-id="e45f4-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e45f4-107">Required.</span></span> <span data-ttu-id="e45f4-108">Nombre de la `String` variable que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="e45f4-108">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="e45f4-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e45f4-109">Required.</span></span> <span data-ttu-id="e45f4-110">Expresión `Integer`.</span><span class="sxs-lookup"><span data-stu-id="e45f4-110">`Integer` expression.</span></span> <span data-ttu-id="e45f4-111">Posición de carácter en `Target` donde comienza la sustitución del texto.</span><span class="sxs-lookup"><span data-stu-id="e45f4-111">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="e45f4-112">`Start` utiliza un índice basado en uno.</span><span class="sxs-lookup"><span data-stu-id="e45f4-112">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="e45f4-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e45f4-113">Optional.</span></span> <span data-ttu-id="e45f4-114">Expresión `Integer`.</span><span class="sxs-lookup"><span data-stu-id="e45f4-114">`Integer` expression.</span></span> <span data-ttu-id="e45f4-115">Número de caracteres que se van a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="e45f4-115">Number of characters to replace.</span></span> <span data-ttu-id="e45f4-116">Si se omite, `String` se usa ALL.</span><span class="sxs-lookup"><span data-stu-id="e45f4-116">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="e45f4-117">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e45f4-117">Required.</span></span> <span data-ttu-id="e45f4-118">`String` expresión que reemplaza a parte de `Target` .</span><span class="sxs-lookup"><span data-stu-id="e45f4-118">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="e45f4-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="e45f4-119">Exceptions</span></span>  
  
|<span data-ttu-id="e45f4-120">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="e45f4-120">Exception type</span></span>|<span data-ttu-id="e45f4-121">Condición</span><span class="sxs-lookup"><span data-stu-id="e45f4-121">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="e45f4-122">`Start` <= 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="e45f4-122">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e45f4-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e45f4-123">Remarks</span></span>  

 <span data-ttu-id="e45f4-124">El número de caracteres reemplazados siempre es menor o igual que el número de caracteres de `Target` .</span><span class="sxs-lookup"><span data-stu-id="e45f4-124">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="e45f4-125">Visual Basic tiene una <xref:Microsoft.VisualBasic.Strings.Mid%2A> función y una `Mid` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e45f4-125">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="e45f4-126">Estos elementos operan en un número especificado de caracteres de una cadena, pero la `Mid` función devuelve los caracteres mientras la `Mid` instrucción reemplaza los caracteres.</span><span class="sxs-lookup"><span data-stu-id="e45f4-126">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="e45f4-127">Para obtener más información, vea <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="e45f4-127">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e45f4-128">La `MidB` instrucción de versiones anteriores de Visual Basic reemplaza una subcadena en bytes, en lugar de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e45f4-128">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="e45f4-129">Se usa principalmente para convertir cadenas en aplicaciones de juegos de caracteres de doble byte (DBCS).</span><span class="sxs-lookup"><span data-stu-id="e45f4-129">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="e45f4-130">Todas las cadenas de Visual Basic están en Unicode y ya `MidB` no se admiten.</span><span class="sxs-lookup"><span data-stu-id="e45f4-130">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e45f4-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e45f4-131">Example</span></span>  

 <span data-ttu-id="e45f4-132">En este ejemplo se utiliza la `Mid` instrucción para reemplazar un número especificado de caracteres de una variable de cadena por caracteres de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="e45f4-132">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="e45f4-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e45f4-133">Requirements</span></span>  

 <span data-ttu-id="e45f4-134">**Espacio de nombres:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="e45f4-134">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="e45f4-135">**Módulo:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="e45f4-135">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="e45f4-136">**Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="e45f4-136">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e45f4-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="e45f4-137">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="e45f4-138">Cadenas</span><span class="sxs-lookup"><span data-stu-id="e45f4-138">Strings</span></span>](../../programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="e45f4-139">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e45f4-139">Introduction to Strings in Visual Basic</span></span>](../../programming-guide/language-features/strings/introduction-to-strings.md)
