---
title: 'Cambio importante: El control de rutas de acceso de cookies ahora se ajusta a RFC 6265'
description: Obtenga información sobre el cambio importante en .NET 5 donde se han implementado los algoritmos de control de rutas de acceso definidos en RFC 6265 para las clases Cookie y CookieContainer.
ms.date: 08/18/2020
ms.openlocfilehash: 5ee1bccc79a5ac271904dd3223b58cc168f18cfa
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256470"
---
# <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a><span data-ttu-id="2e20d-103">El control de rutas de acceso de cookies ahora se ajusta a RFC 6265</span><span class="sxs-lookup"><span data-stu-id="2e20d-103">Cookie path handling now conforms to RFC 6265</span></span>

<span data-ttu-id="2e20d-104">Los algoritmos de control de rutas de acceso que se definen en [RFC 6265](https://tools.ietf.org/html/rfc6265) se implementaron para las clases <xref:System.Net.Cookie> y <xref:System.Net.CookieContainer>.</span><span class="sxs-lookup"><span data-stu-id="2e20d-104">Path-handling algorithms defined in [RFC 6265](https://tools.ietf.org/html/rfc6265) were implemented for the <xref:System.Net.Cookie> and <xref:System.Net.CookieContainer> classes.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2e20d-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="2e20d-105">Version introduced</span></span>

<span data-ttu-id="2e20d-106">5.0</span><span class="sxs-lookup"><span data-stu-id="2e20d-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="2e20d-107">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="2e20d-107">Change description</span></span>

- <span data-ttu-id="2e20d-108">Ya no es necesario que la propiedad <xref:System.Net.Cookie.Path> sea un prefijo de la ruta de acceso de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2e20d-108">The <xref:System.Net.Cookie.Path> property is no longer required to be a prefix of the request path.</span></span>
- <span data-ttu-id="2e20d-109">El cálculo del valor predeterminado de <xref:System.Net.Cookie.Path> y los algoritmos de coincidencia de ruta de acceso se implementaron tal y como se define en la [sección 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) de RFC 6265.</span><span class="sxs-lookup"><span data-stu-id="2e20d-109">The calculation of the default value of <xref:System.Net.Cookie.Path> and path-matching algorithms were implemented as defined in [section 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) of RFC 6265.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2e20d-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="2e20d-110">Recommended action</span></span>

<span data-ttu-id="2e20d-111">En la mayoría de los casos, no tiene que realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="2e20d-111">In most cases, you won't need to take any action.</span></span> <span data-ttu-id="2e20d-112">Sin embargo, si el código dependía de la validación de <xref:System.Net.Cookie.Path>, deberá implementar la validación necesaria en el código.</span><span class="sxs-lookup"><span data-stu-id="2e20d-112">However, if your code was dependent on <xref:System.Net.Cookie.Path> validation, you'll need to implement required validation in your code.</span></span> <span data-ttu-id="2e20d-113">Si el código dependía del cálculo de valores predeterminados para <xref:System.Net.Cookie.Path>, considere la posibilidad de proporcionar el valor <xref:System.Net.Cookie.Path> manualmente en lugar de usar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2e20d-113">If your code was dependent on default value calculation for <xref:System.Net.Cookie.Path>, consider supplying the <xref:System.Net.Cookie.Path> value manually instead of using the default value.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2e20d-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2e20d-114">Affected APIs</span></span>

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

### Category

Networking

-->
