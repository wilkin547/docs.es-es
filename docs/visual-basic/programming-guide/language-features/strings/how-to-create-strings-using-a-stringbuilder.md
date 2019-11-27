---
title: 'Cómo: crear cadenas mediante StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 9295b9d0cdcfdb05dfc75f75f48c16c2354b09b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344378"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="c4c32-102">Cómo: crear cadenas mediante StringBuilder en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c4c32-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="c4c32-103">Este ejemplo crea una cadena larga a partir de muchas cadenas más pequeñas mediante la <xref:System.Text.StringBuilder> clase.</span><span class="sxs-lookup"><span data-stu-id="c4c32-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="c4c32-104">La clase <xref:System.Text.StringBuilder> es más eficaz que el operador `&=` para concatenar muchas cadenas.</span><span class="sxs-lookup"><span data-stu-id="c4c32-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="c4c32-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4c32-105">Example</span></span>

<span data-ttu-id="c4c32-106">En el ejemplo siguiente se crea una instancia de la clase <xref:System.Text.StringBuilder>, se anexan cadenas 1.000 a esa instancia y, después, se devuelve su representación de cadena:</span><span class="sxs-lookup"><span data-stu-id="c4c32-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="c4c32-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4c32-107">See also</span></span>

- [<span data-ttu-id="c4c32-108">Utilizar la clase StringBuilder</span><span class="sxs-lookup"><span data-stu-id="c4c32-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="c4c32-109">Operador &=</span><span class="sxs-lookup"><span data-stu-id="c4c32-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="c4c32-110">Cadenas</span><span class="sxs-lookup"><span data-stu-id="c4c32-110">Strings</span></span>](index.md)
- [<span data-ttu-id="c4c32-111">Creación de cadenas nuevas</span><span class="sxs-lookup"><span data-stu-id="c4c32-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="c4c32-112">Manipular cadenas</span><span class="sxs-lookup"><span data-stu-id="c4c32-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
