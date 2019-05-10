---
title: Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 4a0f3eb2b1603899e9acc1273c023ec5d0ed3132
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913347"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="df3fd-102">Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'</span><span class="sxs-lookup"><span data-stu-id="df3fd-102">Value of type 'type1' cannot be converted to 'type2'</span></span>
<span data-ttu-id="df3fd-103">No se puede convertir el valor de tipo 'tipo1' a 'tipo2'.</span><span class="sxs-lookup"><span data-stu-id="df3fd-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="df3fd-104">Puede usar la propiedad 'Value' para obtener el valor de cadena del primer elemento de '\<Elementoprimario >'.</span><span class="sxs-lookup"><span data-stu-id="df3fd-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="df3fd-105">Se intentó convertir implícitamente un literal XML a un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="df3fd-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="df3fd-106">El literal XML no se puede convertir implícitamente al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="df3fd-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="df3fd-107">**Identificador de error:** BC31194</span><span class="sxs-lookup"><span data-stu-id="df3fd-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="df3fd-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="df3fd-108">To correct this error</span></span>  
  
- <span data-ttu-id="df3fd-109">Use la propiedad `Value` del literal XML para hacer referencia a su valor como `String`.</span><span class="sxs-lookup"><span data-stu-id="df3fd-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="df3fd-110">Use la función `CType` , otra función de conversión de tipo o la clase <xref:System.Convert> para convertir el valor como el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="df3fd-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3fd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="df3fd-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="df3fd-112">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="df3fd-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="df3fd-113">Literales XML</span><span class="sxs-lookup"><span data-stu-id="df3fd-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="df3fd-114">XML</span><span class="sxs-lookup"><span data-stu-id="df3fd-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
