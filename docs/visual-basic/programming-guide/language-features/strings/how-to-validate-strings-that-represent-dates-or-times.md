---
title: Procedimiento para validar cadenas que representan fechas u horas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 5d153ac29039375386b3cd5f03609b1e4bd1d5bf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410572"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="506c5-102">Cómo: Validar cadenas que representan fechas u horas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="506c5-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="506c5-103">En el ejemplo de código siguiente se establece un `Boolean` valor que indica si una cadena representa una fecha u hora válida.</span><span class="sxs-lookup"><span data-stu-id="506c5-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="506c5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="506c5-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="506c5-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="506c5-105">Compile the code</span></span>  
 <span data-ttu-id="506c5-106">Reemplace `("01/01/03")` y `"9:30 PM"` por la fecha y hora que desea validar.</span><span class="sxs-lookup"><span data-stu-id="506c5-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="506c5-107">Puede reemplazar la cadena por otra cadena codificada de forma rígida, por una `String` variable, o por un método que devuelva una cadena, como `InputBox` .</span><span class="sxs-lookup"><span data-stu-id="506c5-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="506c5-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="506c5-108">Robust Programming</span></span>  
 <span data-ttu-id="506c5-109">Utilice este método para validar la cadena antes de intentar convertir `String` en una `DateTime` variable.</span><span class="sxs-lookup"><span data-stu-id="506c5-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="506c5-110">Al comprobar la fecha o la hora en primer lugar, puede evitar generar una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="506c5-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="506c5-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="506c5-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="506c5-112">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="506c5-112">Validating Strings in Visual Basic</span></span>](validating-strings.md)
