---
title: Valor de tipo &#39; type1 &#39; no se puede convertir a &#39; type2 &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords: BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: efa6fcd4d996fb3277cc4cac2af16a86a2d65977
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a><span data-ttu-id="f98aa-102">Valor de tipo &#39; type1 &#39; no se puede convertir a &#39; type2 &#39;</span><span class="sxs-lookup"><span data-stu-id="f98aa-102">Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;</span></span>
<span data-ttu-id="f98aa-103">No se puede convertir el valor de tipo 'tipo1' a 'tipo2'.</span><span class="sxs-lookup"><span data-stu-id="f98aa-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="f98aa-104">Puede utilizar la propiedad 'Value' para obtener el valor de cadena del primer elemento de '\<Elementoprimario >'.</span><span class="sxs-lookup"><span data-stu-id="f98aa-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="f98aa-105">Se intentó convertir implícitamente un literal XML a un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="f98aa-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="f98aa-106">El literal XML no se puede convertir implícitamente al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="f98aa-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="f98aa-107">**Id. de error:** BC31194</span><span class="sxs-lookup"><span data-stu-id="f98aa-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f98aa-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f98aa-108">To correct this error</span></span>  
  
-   <span data-ttu-id="f98aa-109">Use la propiedad `Value` del literal XML para hacer referencia a su valor como `String`.</span><span class="sxs-lookup"><span data-stu-id="f98aa-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="f98aa-110">Use la función `CType` , otra función de conversión de tipo o la clase <xref:System.Convert> para convertir el valor como el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="f98aa-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98aa-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f98aa-111">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="f98aa-112">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="f98aa-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="f98aa-113">Literales XML</span><span class="sxs-lookup"><span data-stu-id="f98aa-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="f98aa-114">XML</span><span class="sxs-lookup"><span data-stu-id="f98aa-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
