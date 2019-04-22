---
title: Procedimiento Crear cadenas mediante un objeto StringBuilder en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834197"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="ebd67-102">Procedimiento Crear cadenas mediante un objeto StringBuilder en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ebd67-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="ebd67-103">En este ejemplo se crea una cadena larga en varias cadenas más pequeñas mediante la <xref:System.Text.StringBuilder> clase.</span><span class="sxs-lookup"><span data-stu-id="ebd67-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="ebd67-104">El <xref:System.Text.StringBuilder> clase es más eficaz que el `&=` operador para concatenar muchas cadenas.</span><span class="sxs-lookup"><span data-stu-id="ebd67-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebd67-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ebd67-105">Example</span></span>  
 <span data-ttu-id="ebd67-106">En el ejemplo siguiente se crea una instancia de la <xref:System.Text.StringBuilder> (clase), anexa 1.000 cadenas a esa instancia y, a continuación, devuelve su representación de cadena.</span><span class="sxs-lookup"><span data-stu-id="ebd67-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a><span data-ttu-id="ebd67-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebd67-107">See also</span></span>

- [<span data-ttu-id="ebd67-108">Utilizar la clase StringBuilder</span><span class="sxs-lookup"><span data-stu-id="ebd67-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="ebd67-109">Operador &=</span><span class="sxs-lookup"><span data-stu-id="ebd67-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="ebd67-110">Cadenas</span><span class="sxs-lookup"><span data-stu-id="ebd67-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="ebd67-111">Creación de cadenas nuevas</span><span class="sxs-lookup"><span data-stu-id="ebd67-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="ebd67-112">Manipular cadenas</span><span class="sxs-lookup"><span data-stu-id="ebd67-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
