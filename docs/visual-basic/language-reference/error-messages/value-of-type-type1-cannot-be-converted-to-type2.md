---
title: Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: f19f157bd4c76f481aa3232bc33c2a0c6ac21367
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400284"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="93de7-102">Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'</span><span class="sxs-lookup"><span data-stu-id="93de7-102">Value of type 'type1' cannot be converted to 'type2'</span></span>
<span data-ttu-id="93de7-103">El valor de tipo ' tipo1 ' no se puede convertir en ' Type2 '.</span><span class="sxs-lookup"><span data-stu-id="93de7-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="93de7-104">Puede usar la propiedad ' value ' para obtener el valor de cadena del primer elemento de ' \<parentElement> '.</span><span class="sxs-lookup"><span data-stu-id="93de7-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="93de7-105">Se intentó convertir implícitamente un literal XML a un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="93de7-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="93de7-106">El literal XML no se puede convertir implícitamente al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="93de7-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="93de7-107">**Identificador de error:** BC31194</span><span class="sxs-lookup"><span data-stu-id="93de7-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="93de7-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="93de7-108">To correct this error</span></span>  
  
- <span data-ttu-id="93de7-109">Use la propiedad `Value` del literal XML para hacer referencia a su valor como `String`.</span><span class="sxs-lookup"><span data-stu-id="93de7-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="93de7-110">Use la función `CType` , otra función de conversión de tipo o la clase <xref:System.Convert> para convertir el valor como el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="93de7-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93de7-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93de7-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="93de7-112">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="93de7-112">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="93de7-113">Literales XML</span><span class="sxs-lookup"><span data-stu-id="93de7-113">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="93de7-114">XML</span><span class="sxs-lookup"><span data-stu-id="93de7-114">XML</span></span>](../../programming-guide/language-features/xml/index.md)
