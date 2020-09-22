---
title: Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 8c80429db618e1bcadce1a58a6514d625f0b3cf1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870239"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="93ccd-102">Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'</span><span class="sxs-lookup"><span data-stu-id="93ccd-102">Value of type 'type1' cannot be converted to 'type2'</span></span>

<span data-ttu-id="93ccd-103">El valor de tipo ' tipo1 ' no se puede convertir en ' Type2 '.</span><span class="sxs-lookup"><span data-stu-id="93ccd-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="93ccd-104">Puede usar la propiedad ' value ' para obtener el valor de cadena del primer elemento de ' \<parentElement> '.</span><span class="sxs-lookup"><span data-stu-id="93ccd-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="93ccd-105">Se intentó convertir implícitamente un literal XML a un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="93ccd-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="93ccd-106">El literal XML no se puede convertir implícitamente al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="93ccd-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="93ccd-107">**Identificador de error:** BC31194</span><span class="sxs-lookup"><span data-stu-id="93ccd-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="93ccd-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="93ccd-108">To correct this error</span></span>  
  
- <span data-ttu-id="93ccd-109">Use la propiedad `Value` del literal XML para hacer referencia a su valor como `String`.</span><span class="sxs-lookup"><span data-stu-id="93ccd-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="93ccd-110">Use la función `CType` , otra función de conversión de tipo o la clase <xref:System.Convert> para convertir el valor como el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="93ccd-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93ccd-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93ccd-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="93ccd-112">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="93ccd-112">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="93ccd-113">Literales XML</span><span class="sxs-lookup"><span data-stu-id="93ccd-113">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="93ccd-114">XML</span><span class="sxs-lookup"><span data-stu-id="93ccd-114">XML</span></span>](../../programming-guide/language-features/xml/index.md)
