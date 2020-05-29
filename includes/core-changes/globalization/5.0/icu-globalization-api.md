---
ms.openlocfilehash: 49041ce906ab0bb8b9482b79c44302465c4ca788
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702323"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="5c612-101">Las API de globalización usan bibliotecas de ICU en Windows</span><span class="sxs-lookup"><span data-stu-id="5c612-101">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="5c612-102">.NET 5.0 y versiones posteriores usan bibliotecas de [componentes internacionales para Unicode (ICU)](http://site.icu-project.org/home) para la funcionalidad de globalización cuando se ejecutan en la actualización de mayo de 2019 de Windows 10 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="5c612-102">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5c612-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="5c612-103">Change description</span></span>

<span data-ttu-id="5c612-104">Anteriormente, las bibliotecas de .NET usaban API de [compatibilidad con el idioma nacional (NLS)](/windows/win32/intl/national-language-support) para la funcionalidad de globalización.</span><span class="sxs-lookup"><span data-stu-id="5c612-104">Previously, .NET libraries used [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality.</span></span> <span data-ttu-id="5c612-105">Por ejemplo, las funciones de NLS se usaban para obtener datos de referencia cultural, como modelos de formato de fecha y hora, comparar cadenas y aplicar mayúsculas y minúsculas en las cadenas en la referencia cultural adecuada.</span><span class="sxs-lookup"><span data-stu-id="5c612-105">For example, NLS functions were used to get culture data, such as date and time format patterns, compare strings, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="5c612-106">A partir de .NET 5.0, si una aplicación se ejecuta en la actualización de mayo de 2019 de Windows 10 o posterior, las bibliotecas de .NET usan las API de globalización de [ICU](http://site.icu-project.org/home).</span><span class="sxs-lookup"><span data-stu-id="5c612-106">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs.</span></span> <span data-ttu-id="5c612-107">Las versiones de la actualización de mayo de 2019 de Windows 10 o posteriores incluyen la biblioteca nativa de ICU.</span><span class="sxs-lookup"><span data-stu-id="5c612-107">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="5c612-108">Si el tiempo de ejecución de .NET no puede cargar ICU, utilizará NLS en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5c612-108">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

<span data-ttu-id="5c612-109">Este cambio se introdujo por dos motivos:</span><span class="sxs-lookup"><span data-stu-id="5c612-109">This change was introduced for two reasons:</span></span>

- <span data-ttu-id="5c612-110">Las aplicaciones tienen el mismo comportamiento de globalización en distintas plataformas, como Linux, macOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="5c612-110">Apps have the same globalization behavior across platforms, including Linux, macOS, and Windows.</span></span>
- <span data-ttu-id="5c612-111">Las aplicaciones pueden controlar el comportamiento de la globalización mediante el uso de bibliotecas ICU personalizadas.</span><span class="sxs-lookup"><span data-stu-id="5c612-111">Apps can control globalization behavior by using custom ICU libraries.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5c612-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5c612-112">Version introduced</span></span>

<span data-ttu-id="5c612-113">.NET 5.0 (versión preliminar 4)</span><span class="sxs-lookup"><span data-stu-id="5c612-113">.NET 5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5c612-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5c612-114">Recommended action</span></span>

<span data-ttu-id="5c612-115">No se requiere ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="5c612-115">No action is required on the part of the developer.</span></span> <span data-ttu-id="5c612-116">Sin embargo, si desea seguir usando las API de globalización de NLS, puede establecer un [modificador en tiempo de ejecución](../../../../docs/core/run-time-config/globalization.md#nls) para revertir a ese comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5c612-116">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../../docs/core/run-time-config/globalization.md#nls) to revert to that behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="5c612-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="5c612-117">Category</span></span>

<span data-ttu-id="5c612-118">Globalización</span><span class="sxs-lookup"><span data-stu-id="5c612-118">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5c612-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5c612-119">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="5c612-120">La mayoría de tipos del espacio de nombres <xref:System.Globalization?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5c612-120">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>

<!--

#### Affected APIs

- `T:System.Span%601`
- `T:System.String`
- `N:System.Globalization`

-->
