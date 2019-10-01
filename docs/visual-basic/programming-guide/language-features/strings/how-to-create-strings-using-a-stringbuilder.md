---
title: 'Cómo: crear cadenas mediante StringBuilder en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 19e036abc9d25ec7fdfd6c33ebb420ec4f503cbc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700104"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="92d2e-102">Cómo: crear cadenas mediante StringBuilder en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="92d2e-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="92d2e-103">Este ejemplo crea una cadena larga a partir de muchas cadenas más pequeñas mediante la clase <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="92d2e-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="92d2e-104">La clase <xref:System.Text.StringBuilder> es más eficaz que el operador `&=` para concatenar muchas cadenas.</span><span class="sxs-lookup"><span data-stu-id="92d2e-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="92d2e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92d2e-105">Example</span></span>

<span data-ttu-id="92d2e-106">En el ejemplo siguiente se crea una instancia de la clase <xref:System.Text.StringBuilder>, se anexan cadenas 1.000 a esa instancia y, después, se devuelve su representación de cadena:</span><span class="sxs-lookup"><span data-stu-id="92d2e-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="92d2e-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="92d2e-107">See also</span></span>

- [<span data-ttu-id="92d2e-108">Utilizar la clase StringBuilder</span><span class="sxs-lookup"><span data-stu-id="92d2e-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="92d2e-109">Operador &=</span><span class="sxs-lookup"><span data-stu-id="92d2e-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="92d2e-110">Cadenas</span><span class="sxs-lookup"><span data-stu-id="92d2e-110">Strings</span></span>](index.md)
- [<span data-ttu-id="92d2e-111">Creación de cadenas nuevas</span><span class="sxs-lookup"><span data-stu-id="92d2e-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="92d2e-112">Manipular cadenas</span><span class="sxs-lookup"><span data-stu-id="92d2e-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
