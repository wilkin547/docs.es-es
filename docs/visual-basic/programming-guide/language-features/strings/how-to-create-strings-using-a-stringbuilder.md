---
title: Procedimiento Crear cadenas mediante un objeto StringBuilder en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032137"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="74987-102">Procedimiento Crear cadenas mediante un objeto StringBuilder en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="74987-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="74987-103">En este ejemplo se crea una cadena larga en varias cadenas más pequeñas mediante la <xref:System.Text.StringBuilder> clase.</span><span class="sxs-lookup"><span data-stu-id="74987-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="74987-104">El <xref:System.Text.StringBuilder> clase es más eficaz que el `&=` operador para concatenar muchas cadenas.</span><span class="sxs-lookup"><span data-stu-id="74987-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74987-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74987-105">Example</span></span>  
 <span data-ttu-id="74987-106">En el ejemplo siguiente se crea una instancia de la <xref:System.Text.StringBuilder> (clase), anexa 1.000 cadenas a esa instancia y, a continuación, devuelve su representación de cadena.</span><span class="sxs-lookup"><span data-stu-id="74987-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a><span data-ttu-id="74987-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="74987-107">See also</span></span>

- [<span data-ttu-id="74987-108">Utilizar la clase StringBuilder</span><span class="sxs-lookup"><span data-stu-id="74987-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="74987-109">Operador &=</span><span class="sxs-lookup"><span data-stu-id="74987-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="74987-110">Cadenas</span><span class="sxs-lookup"><span data-stu-id="74987-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="74987-111">Creación de cadenas nuevas</span><span class="sxs-lookup"><span data-stu-id="74987-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="74987-112">Manipular cadenas</span><span class="sxs-lookup"><span data-stu-id="74987-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
