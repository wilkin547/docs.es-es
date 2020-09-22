---
title: No se admiten literales XML ni propiedades XML en código incrustado en ASP.NET
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 861677636f9a73015b26efec30df728d07fbdf72
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870213"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="57eb5-102">No se admiten literales XML ni propiedades XML en código incrustado en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="57eb5-102">XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>

<span data-ttu-id="57eb5-103">No se admiten literales XML ni propiedades XML en código incrustado dentro de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="57eb5-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="57eb5-104">Para usar las características XML, mueva el código al código subyacente.</span><span class="sxs-lookup"><span data-stu-id="57eb5-104">To use XML features, move the code to code-behind.</span></span>  
  
 <span data-ttu-id="57eb5-105">Un literal XML o una propiedad de eje XML se define dentro del código incrustado ( `<%= =>` ) en un archivo ASP.net.</span><span class="sxs-lookup"><span data-stu-id="57eb5-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>  
  
 <span data-ttu-id="57eb5-106">**Identificador de error:** BC31200</span><span class="sxs-lookup"><span data-stu-id="57eb5-106">**Error ID:** BC31200</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="57eb5-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="57eb5-107">To correct this error</span></span>  
  
- <span data-ttu-id="57eb5-108">Mueva el código que incluye el literal XML o la propiedad de eje XML a un archivo de código subyacente de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="57eb5-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57eb5-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57eb5-109">See also</span></span>

- [<span data-ttu-id="57eb5-110">Literales XML</span><span class="sxs-lookup"><span data-stu-id="57eb5-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="57eb5-111">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="57eb5-111">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="57eb5-112">XML</span><span class="sxs-lookup"><span data-stu-id="57eb5-112">XML</span></span>](../../programming-guide/language-features/xml/index.md)
