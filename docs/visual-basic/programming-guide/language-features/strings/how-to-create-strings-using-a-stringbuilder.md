---
title: Procedimiento Crear cadenas mediante un objeto StringBuilder en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 5cd118ddd196bdf84045ae8b02fe590e5b087e4e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967963"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="b5ec7-102">Filtrar Crear cadenas mediante un objeto StringBuilder en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5ec7-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="b5ec7-103">En este ejemplo se crea una cadena larga en varias cadenas más pequeñas mediante la <xref:System.Text.StringBuilder> clase.</span><span class="sxs-lookup"><span data-stu-id="b5ec7-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="b5ec7-104">El <xref:System.Text.StringBuilder> clase es más eficaz que el `&=` operador para concatenar muchas cadenas.</span><span class="sxs-lookup"><span data-stu-id="b5ec7-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5ec7-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5ec7-105">Example</span></span>  
 <span data-ttu-id="b5ec7-106">En el ejemplo siguiente se crea una instancia de la <xref:System.Text.StringBuilder> (clase), anexa 1.000 cadenas a esa instancia y, a continuación, devuelve su representación de cadena.</span><span class="sxs-lookup"><span data-stu-id="b5ec7-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a><span data-ttu-id="b5ec7-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5ec7-107">See also</span></span>
- [<span data-ttu-id="b5ec7-108">Utilizar la clase StringBuilder</span><span class="sxs-lookup"><span data-stu-id="b5ec7-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="b5ec7-109">Operador &=</span><span class="sxs-lookup"><span data-stu-id="b5ec7-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="b5ec7-110">Cadenas</span><span class="sxs-lookup"><span data-stu-id="b5ec7-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="b5ec7-111">Creación de cadenas nuevas</span><span class="sxs-lookup"><span data-stu-id="b5ec7-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="b5ec7-112">Manipular cadenas</span><span class="sxs-lookup"><span data-stu-id="b5ec7-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
