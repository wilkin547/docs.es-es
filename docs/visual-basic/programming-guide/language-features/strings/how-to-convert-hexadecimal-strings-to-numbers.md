---
title: Procedimiento Convertir cadenas hexadecimales en números (Visual Basic)
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: 76acee8913df35d4d071017078b38a3c474c3357
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54633830"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="ae817-102">Procedimiento Convertir cadenas hexadecimales en números (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae817-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="ae817-103">En este ejemplo convierte una cadena hexadecimal en un entero con el <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="ae817-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="ae817-104">Para convertir una cadena hexadecimal en un número</span><span class="sxs-lookup"><span data-stu-id="ae817-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="ae817-105">Use el <xref:System.Convert.ToInt32(System.String,System.Int32)> método para convertir el número expresado en base 16 en un entero.</span><span class="sxs-lookup"><span data-stu-id="ae817-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="ae817-106">El primer argumento de la <xref:System.Convert.ToInt32(System.String,System.Int32)> método es la cadena para convertir.</span><span class="sxs-lookup"><span data-stu-id="ae817-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="ae817-107">El segundo argumento describe la base en que el número se expresa en; hexadecimal es base 16.</span><span class="sxs-lookup"><span data-stu-id="ae817-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- <span data-ttu-id="ae817-108">Tenga en cuenta que la cadena hexadecimal tiene las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="ae817-108">Note that the hexadecimal string has the following restrictions:</span></span>

   - <span data-ttu-id="ae817-109">No puede incluir el `&h` prefijo.</span><span class="sxs-lookup"><span data-stu-id="ae817-109">It cannot include the `&h` prefix.</span></span>
   - <span data-ttu-id="ae817-110">No puede incluir el `_` separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="ae817-110">It cannot include the `_` digit separator.</span></span>

   <span data-ttu-id="ae817-111">Si el prefijo o un separador de dígitos está presente, la llamada a la <xref:System.Convert.ToInt32(System.String,System.Int32)> método produce una <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="ae817-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae817-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae817-112">See also</span></span>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
