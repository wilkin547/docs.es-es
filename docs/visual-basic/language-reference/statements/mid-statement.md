---
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
ms.openlocfilehash: 0379a6cabe819365b22994a5e4f9353d98b2c768
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873201"
---
# <a name="mid-statement"></a><span data-ttu-id="84bd7-102">Mid (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="84bd7-102">Mid Statement</span></span>

<span data-ttu-id="84bd7-103">Reemplaza un número especificado de caracteres de una `String` variable por caracteres de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="84bd7-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84bd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84bd7-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="84bd7-105">Partes</span><span class="sxs-lookup"><span data-stu-id="84bd7-105">Parts</span></span>  

 `Target`  
 <span data-ttu-id="84bd7-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="84bd7-106">Required.</span></span> <span data-ttu-id="84bd7-107">Nombre de la `String` variable que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="84bd7-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="84bd7-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="84bd7-108">Required.</span></span> <span data-ttu-id="84bd7-109">Expresión `Integer`.</span><span class="sxs-lookup"><span data-stu-id="84bd7-109">`Integer` expression.</span></span> <span data-ttu-id="84bd7-110">Posición de carácter en `Target` donde comienza la sustitución del texto.</span><span class="sxs-lookup"><span data-stu-id="84bd7-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="84bd7-111">`Start` utiliza un índice basado en uno.</span><span class="sxs-lookup"><span data-stu-id="84bd7-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="84bd7-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="84bd7-112">Optional.</span></span> <span data-ttu-id="84bd7-113">Expresión `Integer`.</span><span class="sxs-lookup"><span data-stu-id="84bd7-113">`Integer` expression.</span></span> <span data-ttu-id="84bd7-114">Número de caracteres que se van a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="84bd7-114">Number of characters to replace.</span></span> <span data-ttu-id="84bd7-115">Si se omite, `String` se usa ALL.</span><span class="sxs-lookup"><span data-stu-id="84bd7-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="84bd7-116">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="84bd7-116">Required.</span></span> <span data-ttu-id="84bd7-117">`String` expresión que reemplaza a parte de `Target` .</span><span class="sxs-lookup"><span data-stu-id="84bd7-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="84bd7-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="84bd7-118">Exceptions</span></span>  
  
|<span data-ttu-id="84bd7-119">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="84bd7-119">Exception type</span></span>|<span data-ttu-id="84bd7-120">Condición</span><span class="sxs-lookup"><span data-stu-id="84bd7-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="84bd7-121">`Start` <= 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="84bd7-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84bd7-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="84bd7-122">Remarks</span></span>  

 <span data-ttu-id="84bd7-123">El número de caracteres reemplazados siempre es menor o igual que el número de caracteres de `Target` .</span><span class="sxs-lookup"><span data-stu-id="84bd7-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="84bd7-124">Visual Basic tiene una <xref:Microsoft.VisualBasic.Strings.Mid%2A> función y una `Mid` instrucción.</span><span class="sxs-lookup"><span data-stu-id="84bd7-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="84bd7-125">Estos elementos operan en un número especificado de caracteres de una cadena, pero la `Mid` función devuelve los caracteres mientras la `Mid` instrucción reemplaza los caracteres.</span><span class="sxs-lookup"><span data-stu-id="84bd7-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="84bd7-126">Para obtener más información, vea <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="84bd7-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84bd7-127">La `MidB` instrucción de versiones anteriores de Visual Basic reemplaza una subcadena en bytes, en lugar de caracteres.</span><span class="sxs-lookup"><span data-stu-id="84bd7-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="84bd7-128">Se usa principalmente para convertir cadenas en aplicaciones de juegos de caracteres de doble byte (DBCS).</span><span class="sxs-lookup"><span data-stu-id="84bd7-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="84bd7-129">Todas las cadenas de Visual Basic están en Unicode y ya `MidB` no se admiten.</span><span class="sxs-lookup"><span data-stu-id="84bd7-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84bd7-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="84bd7-130">Example</span></span>  

 <span data-ttu-id="84bd7-131">En este ejemplo se utiliza la `Mid` instrucción para reemplazar un número especificado de caracteres de una variable de cadena por caracteres de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="84bd7-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="84bd7-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84bd7-132">Requirements</span></span>  

 <span data-ttu-id="84bd7-133">**Espacio de nombres:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="84bd7-133">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="84bd7-134">**Módulo:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="84bd7-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="84bd7-135">**Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="84bd7-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84bd7-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="84bd7-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="84bd7-137">Cadenas</span><span class="sxs-lookup"><span data-stu-id="84bd7-137">Strings</span></span>](../../programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="84bd7-138">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84bd7-138">Introduction to Strings in Visual Basic</span></span>](../../programming-guide/language-features/strings/introduction-to-strings.md)
