---
title: "Cómo: Validar cadenas que representan fechas u horas (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed3201ef2bbef97eebbafa5ef128ca015adac013
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="c5ac5-102">Cómo: Validar cadenas que representan fechas u horas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5ac5-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="c5ac5-103">El siguiente ejemplo de código establece una `Boolean` valor que indica si una cadena representa una fecha u hora válida.</span><span class="sxs-lookup"><span data-stu-id="c5ac5-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5ac5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5ac5-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c5ac5-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c5ac5-105">Compiling the Code</span></span>  
 <span data-ttu-id="c5ac5-106">Reemplace `("01/01/03")` y `"9:30 PM"` con la fecha y hora que desea validar.</span><span class="sxs-lookup"><span data-stu-id="c5ac5-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="c5ac5-107">Puede reemplazar la cadena con otra cadena codificada de forma rígida, con un `String` o variable, con un método que devuelve una cadena, como `InputBox`.</span><span class="sxs-lookup"><span data-stu-id="c5ac5-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c5ac5-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="c5ac5-108">Robust Programming</span></span>  
 <span data-ttu-id="c5ac5-109">Utilice este método para validar la cadena antes de intentar convertir el `String` a una `DateTime` variable.</span><span class="sxs-lookup"><span data-stu-id="c5ac5-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="c5ac5-110">Comprobando la fecha u hora en primer lugar, puede evitar generar una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c5ac5-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5ac5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5ac5-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [<span data-ttu-id="c5ac5-112">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c5ac5-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
