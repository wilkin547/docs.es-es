---
title: No se admiten literales XML ni propiedades XML en código incrustado en ASP.NET
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: d96386f8495685391203826fea85efba47c44951
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163264"
---
# <a name="bc31200-xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="3460e-102">BC31200: no se admiten literales XML ni propiedades XML en código incrustado en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3460e-102">BC31200: XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>

<span data-ttu-id="3460e-103">No se admiten literales XML ni propiedades XML en código incrustado dentro de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3460e-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="3460e-104">Para usar las características XML, mueva el código al código subyacente.</span><span class="sxs-lookup"><span data-stu-id="3460e-104">To use XML features, move the code to code-behind.</span></span>

 <span data-ttu-id="3460e-105">Un literal XML o una propiedad de eje XML se define dentro del código incrustado ( `<%= =>` ) en un archivo ASP.net.</span><span class="sxs-lookup"><span data-stu-id="3460e-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>

 <span data-ttu-id="3460e-106">**Identificador de error:** BC31200</span><span class="sxs-lookup"><span data-stu-id="3460e-106">**Error ID:** BC31200</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="3460e-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3460e-107">To correct this error</span></span>

- <span data-ttu-id="3460e-108">Mueva el código que incluye el literal XML o la propiedad de eje XML a un archivo de código subyacente de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3460e-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>

## <a name="see-also"></a><span data-ttu-id="3460e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3460e-109">See also</span></span>

- [<span data-ttu-id="3460e-110">Literales XML</span><span class="sxs-lookup"><span data-stu-id="3460e-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="3460e-111">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="3460e-111">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="3460e-112">XML</span><span class="sxs-lookup"><span data-stu-id="3460e-112">XML</span></span>](../../programming-guide/language-features/xml/index.md)
