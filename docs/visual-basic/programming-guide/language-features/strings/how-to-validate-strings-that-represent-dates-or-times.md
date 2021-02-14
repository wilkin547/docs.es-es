---
description: 'Más información acerca de cómo: validar cadenas que representan fechas u horas (Visual Basic)'
title: Procedimiento para validar cadenas que representan fechas u horas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 4e9255717d1711d8e9839c218a78b359549d9eef
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424260"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="f2bdc-103">Cómo: Validar cadenas que representan fechas u horas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2bdc-103">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>

<span data-ttu-id="f2bdc-104">En el ejemplo de código siguiente se establece un `Boolean` valor que indica si una cadena representa una fecha u hora válida.</span><span class="sxs-lookup"><span data-stu-id="f2bdc-104">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2bdc-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2bdc-105">Example</span></span>  

 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="f2bdc-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f2bdc-106">Compile the code</span></span>  

 <span data-ttu-id="f2bdc-107">Reemplace `("01/01/03")` y `"9:30 PM"` por la fecha y hora que desea validar.</span><span class="sxs-lookup"><span data-stu-id="f2bdc-107">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="f2bdc-108">Puede reemplazar la cadena por otra cadena codificada de forma rígida, por una `String` variable, o por un método que devuelva una cadena, como `InputBox` .</span><span class="sxs-lookup"><span data-stu-id="f2bdc-108">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f2bdc-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="f2bdc-109">Robust Programming</span></span>  

 <span data-ttu-id="f2bdc-110">Utilice este método para validar la cadena antes de intentar convertir `String` en una `DateTime` variable.</span><span class="sxs-lookup"><span data-stu-id="f2bdc-110">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="f2bdc-111">Al comprobar la fecha o la hora en primer lugar, puede evitar generar una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2bdc-111">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2bdc-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2bdc-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="f2bdc-113">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f2bdc-113">Validating Strings in Visual Basic</span></span>](validating-strings.md)
