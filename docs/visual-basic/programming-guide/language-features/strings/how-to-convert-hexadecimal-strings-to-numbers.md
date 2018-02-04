---
title: "Cómo: Convertir cadenas hexadecimales en números (Visual Basic)"
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: petrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: c35ac615e3f87710f934a1cf66e6546625298bd0
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="2cf91-102">Cómo: Convertir cadenas hexadecimales en números (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cf91-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="2cf91-103">Este ejemplo convierte una cadena hexadecimal en un entero con el <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="2cf91-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="2cf91-104">Para convertir una cadena hexadecimal en un número</span><span class="sxs-lookup"><span data-stu-id="2cf91-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="2cf91-105">Use la <xref:System.Convert.ToInt32(System.String,System.Int32)> método para convertir el número expresado en base 16 a un entero.</span><span class="sxs-lookup"><span data-stu-id="2cf91-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="2cf91-106">El primer argumento de la <xref:System.Convert.ToInt32(System.String,System.Int32)> método es la cadena que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="2cf91-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="2cf91-107">El segundo argumento describe la base en que el número se expresa en; hexadecimal es base 16.</span><span class="sxs-lookup"><span data-stu-id="2cf91-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- <span data-ttu-id="2cf91-108">Tenga en cuenta que la cadena hexadecimal tiene las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="2cf91-108">Note that the hexadecimal string has the following restrictions:</span></span>

   - <span data-ttu-id="2cf91-109">No puede incluir el `&h` prefijo.</span><span class="sxs-lookup"><span data-stu-id="2cf91-109">It cannot include the `&h` prefix.</span></span>
   - <span data-ttu-id="2cf91-110">No puede incluir el `_` separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="2cf91-110">It cannot include the `_` digit separator.</span></span>

   <span data-ttu-id="2cf91-111">Si el prefijo o un separador de dígitos está presente, la llamada a la <xref:System.Convert.ToInt32(System.String,System.Int32)> método produce un <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="2cf91-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="2cf91-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cf91-112">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
