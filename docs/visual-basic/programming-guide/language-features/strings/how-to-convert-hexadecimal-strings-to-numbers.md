---
description: 'Más información acerca de cómo: convertir cadenas hexadecimales en números (Visual Basic)'
title: Procedimiento para convertir cadenas hexadecimales en números
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: cf1648b5f85f189f203f56cf569041e4f2db5ac3
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425548"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="37d32-103">Cómo: Convertir cadenas hexadecimales en números (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d32-103">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>

<span data-ttu-id="37d32-104">En este ejemplo se convierte una cadena hexadecimal en un entero mediante el <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="37d32-104">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="37d32-105">Para convertir una cadena hexadecimal en un número</span><span class="sxs-lookup"><span data-stu-id="37d32-105">To convert a hexadecimal string to a number</span></span>

- <span data-ttu-id="37d32-106">Use el <xref:System.Convert.ToInt32(System.String,System.Int32)> método para convertir el número expresado en base-16 en un entero.</span><span class="sxs-lookup"><span data-stu-id="37d32-106">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>

  <span data-ttu-id="37d32-107">El primer argumento del <xref:System.Convert.ToInt32(System.String,System.Int32)> método es la cadena que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="37d32-107">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="37d32-108">El segundo argumento describe en qué base se expresa el número; hexadecimal es base 16.</span><span class="sxs-lookup"><span data-stu-id="37d32-108">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- <span data-ttu-id="37d32-109">Tenga en cuenta que la cadena hexadecimal tiene las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="37d32-109">Note that the hexadecimal string has the following restrictions:</span></span>

  - <span data-ttu-id="37d32-110">No puede incluir el `&h` prefijo.</span><span class="sxs-lookup"><span data-stu-id="37d32-110">It cannot include the `&h` prefix.</span></span>
  - <span data-ttu-id="37d32-111">No puede incluir el `_` separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="37d32-111">It cannot include the `_` digit separator.</span></span>

  <span data-ttu-id="37d32-112">Si el prefijo o el separador de dígitos están presentes, la llamada al <xref:System.Convert.ToInt32(System.String,System.Int32)> método produce una excepción <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="37d32-112">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="37d32-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37d32-113">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
