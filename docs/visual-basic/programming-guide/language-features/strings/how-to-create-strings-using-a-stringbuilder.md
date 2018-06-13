---
title: 'Cómo: Crear cadenas mediante un objeto StringBuilder en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 49f3271d41e9e858c6ecafe1dde5330ebff767f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647737"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="e3dcd-102">Cómo: Crear cadenas mediante un objeto StringBuilder en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e3dcd-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="e3dcd-103">Este ejemplo crea una cadena larga de muchas cadenas más pequeñas mediante la <xref:System.Text.StringBuilder> clase.</span><span class="sxs-lookup"><span data-stu-id="e3dcd-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="e3dcd-104">El <xref:System.Text.StringBuilder> clase es más eficaz que la `&=` operador para concatenar muchas cadenas.</span><span class="sxs-lookup"><span data-stu-id="e3dcd-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3dcd-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3dcd-105">Example</span></span>  
 <span data-ttu-id="e3dcd-106">En el ejemplo siguiente se crea una instancia de la <xref:System.Text.StringBuilder> (clase), anexan 1.000 cadenas a esa instancia y, a continuación, devuelve la representación de cadena.</span><span class="sxs-lookup"><span data-stu-id="e3dcd-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e3dcd-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3dcd-107">See Also</span></span>  
 [<span data-ttu-id="e3dcd-108">Utilizar la clase StringBuilder</span><span class="sxs-lookup"><span data-stu-id="e3dcd-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)  
 [<span data-ttu-id="e3dcd-109">Operador &=</span><span class="sxs-lookup"><span data-stu-id="e3dcd-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="e3dcd-110">Cadenas</span><span class="sxs-lookup"><span data-stu-id="e3dcd-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="e3dcd-111">Creación de cadenas nuevas</span><span class="sxs-lookup"><span data-stu-id="e3dcd-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="e3dcd-112">Manipular cadenas</span><span class="sxs-lookup"><span data-stu-id="e3dcd-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)  
 <span data-ttu-id="e3dcd-113">[Ejemplo de cadenas](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e3dcd-113">[Strings Sample](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span></span>
