---
description: 'Más información sobre: BC31200: los literales XML y las propiedades XML no se admiten en el código incrustado en ASP.NET'
title: No se admiten literales XML ni propiedades XML en código incrustado en ASP.NET
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 0a5328676ee38a56334b77f665a464daa586ce3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701409"
---
# <a name="bc31200-xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="d9b22-103">BC31200: no se admiten literales XML ni propiedades XML en código incrustado en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d9b22-103">BC31200: XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>

<span data-ttu-id="d9b22-104">No se admiten literales XML ni propiedades XML en código incrustado dentro de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d9b22-104">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="d9b22-105">Para usar las características XML, mueva el código al código subyacente.</span><span class="sxs-lookup"><span data-stu-id="d9b22-105">To use XML features, move the code to code-behind.</span></span>

 <span data-ttu-id="d9b22-106">Un literal XML o una propiedad de eje XML se define dentro del código incrustado ( `<%= =>` ) en un archivo ASP.net.</span><span class="sxs-lookup"><span data-stu-id="d9b22-106">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>

 <span data-ttu-id="d9b22-107">**Identificador de error:** BC31200</span><span class="sxs-lookup"><span data-stu-id="d9b22-107">**Error ID:** BC31200</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d9b22-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d9b22-108">To correct this error</span></span>

- <span data-ttu-id="d9b22-109">Mueva el código que incluye el literal XML o la propiedad de eje XML a un archivo de código subyacente de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d9b22-109">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9b22-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9b22-110">See also</span></span>

- [<span data-ttu-id="d9b22-111">Literales XML</span><span class="sxs-lookup"><span data-stu-id="d9b22-111">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="d9b22-112">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="d9b22-112">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="d9b22-113">XML</span><span class="sxs-lookup"><span data-stu-id="d9b22-113">XML</span></span>](../../programming-guide/language-features/xml/index.md)
