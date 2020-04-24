---
title: 'Cómo: crear cadenas con StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645322"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="bc7fc-102">Cómo: crear cadenas mediante StringBuilder en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc7fc-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="bc7fc-103">En este ejemplo se construye una cadena <xref:System.Text.StringBuilder> larga a partir de muchas cadenas más pequeñas mediante la clase.</span><span class="sxs-lookup"><span data-stu-id="bc7fc-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="bc7fc-104">La <xref:System.Text.StringBuilder> clase es más `&=` eficaz que el operador para concatenar muchas cadenas.</span><span class="sxs-lookup"><span data-stu-id="bc7fc-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="bc7fc-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc7fc-105">Example</span></span>

<span data-ttu-id="bc7fc-106">En el ejemplo siguiente <xref:System.Text.StringBuilder> se crea una instancia de la clase, se anexan 1.000 cadenas a esa instancia y, a continuación, se devuelve su representación de cadena:</span><span class="sxs-lookup"><span data-stu-id="bc7fc-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="bc7fc-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc7fc-107">See also</span></span>

- [<span data-ttu-id="bc7fc-108">Uso de la clase StringBuilder</span><span class="sxs-lookup"><span data-stu-id="bc7fc-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="bc7fc-109">&- Operador</span><span class="sxs-lookup"><span data-stu-id="bc7fc-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="bc7fc-110">Cadenas</span><span class="sxs-lookup"><span data-stu-id="bc7fc-110">Strings</span></span>](index.md)
- [<span data-ttu-id="bc7fc-111">Creación de cadenas</span><span class="sxs-lookup"><span data-stu-id="bc7fc-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="bc7fc-112">Manipulación de cadenas</span><span class="sxs-lookup"><span data-stu-id="bc7fc-112">Manipulating Strings</span></span>](../../../../standard/base-types/best-practices-strings.md)
