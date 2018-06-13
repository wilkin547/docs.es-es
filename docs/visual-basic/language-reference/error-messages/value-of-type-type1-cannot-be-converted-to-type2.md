---
title: Valor de tipo &#39;type1&#39; no se puede convertir a &#39;type2&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 9e59d3bc5e2bfca3628248d08ffc475334d4da79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602767"
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a><span data-ttu-id="84cdc-102">Valor de tipo &#39;type1&#39; no se puede convertir a &#39;type2&#39;</span><span class="sxs-lookup"><span data-stu-id="84cdc-102">Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;</span></span>
<span data-ttu-id="84cdc-103">No se puede convertir el valor de tipo 'tipo1' a 'tipo2'.</span><span class="sxs-lookup"><span data-stu-id="84cdc-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="84cdc-104">Puede utilizar la propiedad 'Value' para obtener el valor de cadena del primer elemento de '\<Elementoprimario >'.</span><span class="sxs-lookup"><span data-stu-id="84cdc-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="84cdc-105">Se intentó convertir implícitamente un literal XML a un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="84cdc-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="84cdc-106">El literal XML no se puede convertir implícitamente al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="84cdc-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="84cdc-107">**Id. de error:** BC31194</span><span class="sxs-lookup"><span data-stu-id="84cdc-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="84cdc-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="84cdc-108">To correct this error</span></span>  
  
-   <span data-ttu-id="84cdc-109">Use la propiedad `Value` del literal XML para hacer referencia a su valor como `String`.</span><span class="sxs-lookup"><span data-stu-id="84cdc-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="84cdc-110">Use la función `CType` , otra función de conversión de tipo o la clase <xref:System.Convert> para convertir el valor como el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="84cdc-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84cdc-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="84cdc-111">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="84cdc-112">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="84cdc-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="84cdc-113">Literales XML</span><span class="sxs-lookup"><span data-stu-id="84cdc-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="84cdc-114">XML</span><span class="sxs-lookup"><span data-stu-id="84cdc-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
