---
title: 'Cómo: Validar cadenas que representan fechas u horas (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 411c8517783421b2472c3e4aa77287f8252f179b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647867"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="22508-102">Cómo: Validar cadenas que representan fechas u horas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22508-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="22508-103">El siguiente ejemplo de código establece una `Boolean` valor que indica si una cadena representa una fecha u hora válida.</span><span class="sxs-lookup"><span data-stu-id="22508-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22508-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22508-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22508-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="22508-105">Compiling the Code</span></span>  
 <span data-ttu-id="22508-106">Reemplace `("01/01/03")` y `"9:30 PM"` con la fecha y hora que desea validar.</span><span class="sxs-lookup"><span data-stu-id="22508-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="22508-107">Puede reemplazar la cadena con otra cadena codificada de forma rígida, con un `String` o variable, con un método que devuelve una cadena, como `InputBox`.</span><span class="sxs-lookup"><span data-stu-id="22508-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="22508-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="22508-108">Robust Programming</span></span>  
 <span data-ttu-id="22508-109">Utilice este método para validar la cadena antes de intentar convertir el `String` a una `DateTime` variable.</span><span class="sxs-lookup"><span data-stu-id="22508-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="22508-110">Comprobando la fecha u hora en primer lugar, puede evitar generar una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="22508-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22508-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="22508-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [<span data-ttu-id="22508-112">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22508-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
