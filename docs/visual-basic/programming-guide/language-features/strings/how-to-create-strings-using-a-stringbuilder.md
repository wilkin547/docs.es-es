---
description: 'Más información acerca de cómo: crear cadenas mediante StringBuilder en Visual Basic'
title: 'Cómo: crear cadenas mediante StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 6def32517f71ec3c2a7795c3395e3e572903ce1e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429824"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="2ea35-103">Cómo: crear cadenas mediante StringBuilder en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ea35-103">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="2ea35-104">Este ejemplo crea una cadena larga a partir de muchas cadenas más pequeñas mediante la <xref:System.Text.StringBuilder> clase.</span><span class="sxs-lookup"><span data-stu-id="2ea35-104">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="2ea35-105">La <xref:System.Text.StringBuilder> clase es más eficaz que el `&=` operador para concatenar muchas cadenas.</span><span class="sxs-lookup"><span data-stu-id="2ea35-105">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="2ea35-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ea35-106">Example</span></span>

<span data-ttu-id="2ea35-107">En el ejemplo siguiente se crea una instancia de la <xref:System.Text.StringBuilder> clase, se anexan las cadenas 1.000 a esa instancia y, después, se devuelve su representación de cadena:</span><span class="sxs-lookup"><span data-stu-id="2ea35-107">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="2ea35-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ea35-108">See also</span></span>

- [<span data-ttu-id="2ea35-109">Utilizar la clase StringBuilder</span><span class="sxs-lookup"><span data-stu-id="2ea35-109">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="2ea35-110">&= (operador)</span><span class="sxs-lookup"><span data-stu-id="2ea35-110">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="2ea35-111">Cadenas</span><span class="sxs-lookup"><span data-stu-id="2ea35-111">Strings</span></span>](index.md)
- [<span data-ttu-id="2ea35-112">Creación de cadenas</span><span class="sxs-lookup"><span data-stu-id="2ea35-112">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="2ea35-113">Manipulación de cadenas</span><span class="sxs-lookup"><span data-stu-id="2ea35-113">Manipulating Strings</span></span>](../../../../standard/base-types/best-practices-strings.md)
