---
title: Globalización y localización de aplicaciones .NET
ms.date: 06/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- international applications [.NET]
- globalization [.NET], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
ms.openlocfilehash: 10d07a02a7ff744a87b920fd97df24b076c22cc3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288295"
---
# <a name="globalizing-and-localizing-net-applications"></a><span data-ttu-id="ce405-102">Globalización y localización de aplicaciones .NET</span><span class="sxs-lookup"><span data-stu-id="ce405-102">Globalizing and localizing .NET applications</span></span>

<span data-ttu-id="ce405-103">El desarrollo de una aplicación de uso internacional, incluida una aplicación que se pueda localizar en uno o varios idiomas, implica tres pasos: globalización, revisión de localizabilidad y localización.</span><span class="sxs-lookup"><span data-stu-id="ce405-103">Developing a world-ready application, including an application that can be localized into one or more languages, involves three steps: globalization, localizability review, and localization.</span></span>

[<span data-ttu-id="ce405-104">Globalización</span><span class="sxs-lookup"><span data-stu-id="ce405-104">Globalization</span></span>](globalization.md)

<span data-ttu-id="ce405-105">Este paso conlleva diseñar y codificar una aplicación de referencias culturales e idiomáticas neutras que admita el uso de interfaces de usuario localizadas y datos regionales para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ce405-105">This step involves designing and coding an application that is culture-neutral and language-neutral, and that supports localized user interfaces and regional data for all users.</span></span> <span data-ttu-id="ce405-106">Implica tomar decisiones de diseño y programación que no se basan en suposiciones específicas de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="ce405-106">It involves making design and programming decisions that are not based on culture-specific assumptions.</span></span> <span data-ttu-id="ce405-107">Aunque una aplicación globalizada no está localizada, está diseñada y escrita para poder localizarla posteriormente en uno o varios idiomas con relativa facilidad.</span><span class="sxs-lookup"><span data-stu-id="ce405-107">While a globalized application is not localized, it nevertheless is designed and written so that it can be subsequently localized into one or more languages with relative ease.</span></span>

[<span data-ttu-id="ce405-108">Revisión de localización</span><span class="sxs-lookup"><span data-stu-id="ce405-108">Localizability review</span></span>](localizability-review.md)

<span data-ttu-id="ce405-109">Este paso implica revisar el código y el diseño de una aplicación para asegurarse de que puede localizarse fácilmente e identificar posibles obstáculos para la localización, además de comprobar que el código ejecutable de la aplicación está separado de los recursos.</span><span class="sxs-lookup"><span data-stu-id="ce405-109">This step involves reviewing an application's code and design to ensure that it can be localized easily and to identify potential roadblocks for localization, and verifying that the application's executable code is separated from its resources.</span></span> <span data-ttu-id="ce405-110">Si la fase de globalización ha sido efectiva, la revisión de localizabilidad confirmará las decisiones de diseño y codificación tomadas durante dicha fase.</span><span class="sxs-lookup"><span data-stu-id="ce405-110">If the globalization stage was effective, the localizability review will confirm the design and coding choices made during globalization.</span></span> <span data-ttu-id="ce405-111">En la etapa de localizabilidad también puede identificarse cualquier problema pendiente, de forma que el código fuente de una aplicación no tenga que modificarse durante la fase de localización.</span><span class="sxs-lookup"><span data-stu-id="ce405-111">The localizability stage may also identify any remaining issues so that an application's source code doesn't have to be modified during the localization stage.</span></span>

[<span data-ttu-id="ce405-112">Localización</span><span class="sxs-lookup"><span data-stu-id="ce405-112">Localization</span></span>](localization.md)

<span data-ttu-id="ce405-113">Este paso implica personalizar una aplicación para referencias culturales o regiones específicas.</span><span class="sxs-lookup"><span data-stu-id="ce405-113">This step involves customizing an application for specific cultures or regions.</span></span> <span data-ttu-id="ce405-114">Si los pasos de globalización y localizabilidad se han realizado correctamente, la localización consiste principalmente en traducir la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ce405-114">If the globalization and localizability steps have been performed correctly, localization consists primarily of translating the user interface.</span></span>

<span data-ttu-id="ce405-115">La realización de estos tres pasos ofrece dos ventajas:</span><span class="sxs-lookup"><span data-stu-id="ce405-115">Following these three steps provides two advantages:</span></span>

- <span data-ttu-id="ce405-116">No es necesario volver a plantear una aplicación ya diseñada para admitir una sola referencia cultural, por ejemplo inglés de EE. UU., de forma que admita otras referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="ce405-116">It frees you from having to retrofit an application that is designed to support a single culture, such as U.S. English, to support additional cultures.</span></span>

- <span data-ttu-id="ce405-117">Da como resultado aplicaciones localizadas que son más estables y tienen menos errores.</span><span class="sxs-lookup"><span data-stu-id="ce405-117">It results in localized applications that are more stable and have fewer bugs.</span></span>

<span data-ttu-id="ce405-118">En .NET se proporciona una extensa compatibilidad para desarrollar aplicaciones de uso internacional y localizadas.</span><span class="sxs-lookup"><span data-stu-id="ce405-118">.NET provides extensive support for the development of world-ready and localized applications.</span></span> <span data-ttu-id="ce405-119">En concreto, muchos miembros de tipo de la biblioteca de clases de .NET contribuyen a la globalización mediante la devolución de valores que reflejan las convenciones de la referencia cultural del usuario actual o de una referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="ce405-119">In particular, many type members in the .NET class library aid globalization by returning values that reflect the conventions of either the current user's culture or a specified culture.</span></span> <span data-ttu-id="ce405-120">Además, .NET admite los ensamblados satélite, que facilitan el proceso de localización de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce405-120">Also, .NET supports satellite assemblies, which facilitate the process of localizing an application.</span></span>

<span data-ttu-id="ce405-121">Para obtener más información, consulte [Globalization documentation](/globalization/) (Documentación de globalización).</span><span class="sxs-lookup"><span data-stu-id="ce405-121">For additional information, see the [Globalization documentation](/globalization/).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ce405-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ce405-122">In this section</span></span>

[<span data-ttu-id="ce405-123">Globalización</span><span class="sxs-lookup"><span data-stu-id="ce405-123">Globalization</span></span>](globalization.md)

<span data-ttu-id="ce405-124">Analiza la primera fase de creación de una aplicación de uso internacional, que implica el diseño y la codificación de una aplicación con referencias culturales e idiomáticas neutras.</span><span class="sxs-lookup"><span data-stu-id="ce405-124">Discusses the first stage of creating a world-ready application, which involves designing and coding an application that is culture-neutral and language-neutral.</span></span>

[<span data-ttu-id="ce405-125">Globalización de .NET e ICU</span><span class="sxs-lookup"><span data-stu-id="ce405-125">.NET globalization and ICU</span></span>](globalization-icu.md)

<span data-ttu-id="ce405-126">Describe el uso que hace .NET de los [componentes internacionales para Unicode (ICU)](http://site.icu-project.org/home).</span><span class="sxs-lookup"><span data-stu-id="ce405-126">Describes how .NET globalization uses [International Components for Unicode (ICU)](http://site.icu-project.org/home).</span></span>

[<span data-ttu-id="ce405-127">Revisión de localización</span><span class="sxs-lookup"><span data-stu-id="ce405-127">Localizability review</span></span>](localizability-review.md)

<span data-ttu-id="ce405-128">Analiza la segunda fase de creación de una aplicación localizada, que implica la identificación de obstáculos potenciales para la localización.</span><span class="sxs-lookup"><span data-stu-id="ce405-128">Discusses the second stage of creating a localized application, which involves identifying potential roadblocks to localization.</span></span>

[<span data-ttu-id="ce405-129">Localización</span><span class="sxs-lookup"><span data-stu-id="ce405-129">Localization</span></span>](localization.md)

<span data-ttu-id="ce405-130">Analiza la fase final de creación de una aplicación localizada, que implica la personalización de la interfaz de usuario de una aplicación para regiones o referencias culturales concretas.</span><span class="sxs-lookup"><span data-stu-id="ce405-130">Discusses the final stage of creating a localized application, which involves customizing an application's user interface for specific regions or cultures.</span></span>

[<span data-ttu-id="ce405-131">Operaciones de cadenas que no distinguen referencias culturales</span><span class="sxs-lookup"><span data-stu-id="ce405-131">Culture-insensitive string operations</span></span>](culture-insensitive-string-operations.md)

<span data-ttu-id="ce405-132">Se describe cómo usar los métodos y clases de .NET que tienen en cuenta las referencias culturales de manera predeterminada para obtener resultados que no las tienen en cuenta.</span><span class="sxs-lookup"><span data-stu-id="ce405-132">Describes how to use .NET methods and classes that are culture-sensitive by default to obtain culture-insensitive results.</span></span>

[<span data-ttu-id="ce405-133">Prácticas recomendadas para desarrollar aplicaciones de uso internacional</span><span class="sxs-lookup"><span data-stu-id="ce405-133">Best practices for developing world-ready applications</span></span>](best-practices-for-developing-world-ready-apps.md)

<span data-ttu-id="ce405-134">Describe los procedimientos recomendados que se deben seguir para la globalización, localización y desarrollo de aplicaciones de ASP.NET de uso internacional.</span><span class="sxs-lookup"><span data-stu-id="ce405-134">Describes the best practices to follow for globalization, localization, and developing world-ready ASP.NET applications.</span></span>

## <a name="reference"></a><span data-ttu-id="ce405-135">Referencia</span><span class="sxs-lookup"><span data-stu-id="ce405-135">Reference</span></span>

- <span data-ttu-id="ce405-136">Espacio de nombres <xref:System.Globalization?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ce405-136"><xref:System.Globalization?displayProperty=nameWithType> namespace</span></span>

   <span data-ttu-id="ce405-137">Contiene clases que definen datos relativos a la referencia cultural, tales como idioma, país o región, calendario, formatos de fecha, divisa y números, así como el criterio de ordenación para cadenas.</span><span class="sxs-lookup"><span data-stu-id="ce405-137">Contains classes that define culture-related information, including the language, the country/region, the calendars in use, the format patterns for dates, currency, and numbers, and the sort order for strings.</span></span>

- <span data-ttu-id="ce405-138">Espacio de nombres <xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="ce405-138"><xref:System.Resources> namespace</span></span>

   <span data-ttu-id="ce405-139">Proporciona clases para la creación, control y utilización de recursos.</span><span class="sxs-lookup"><span data-stu-id="ce405-139">Provides classes for creating, manipulating, and using resources.</span></span>

- <span data-ttu-id="ce405-140">Espacio de nombres <xref:System.Text></span><span class="sxs-lookup"><span data-stu-id="ce405-140"><xref:System.Text> namespace</span></span>

   <span data-ttu-id="ce405-141">Contiene clases que representan ASCII, ANSI, Unicode y otras codificaciones de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ce405-141">Contains classes representing ASCII, ANSI, Unicode, and other character encodings.</span></span>

- [<span data-ttu-id="ce405-142">Resgen.exe (generador de archivos de recursos)</span><span class="sxs-lookup"><span data-stu-id="ce405-142">Resgen.exe (Resource File Generator)</span></span>](../../framework/tools/resgen-exe-resource-file-generator.md)

   <span data-ttu-id="ce405-143">Describe cómo utilizar la herramienta Resgen.exe para convertir archivos .txt y .resx (formato de recursos basados en XML) en archivos .resources binarios de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ce405-143">Describes how to use Resgen.exe to convert .txt files and XML-based resource format (.resx) files to common language runtime binary .resources files.</span></span>

- [<span data-ttu-id="ce405-144">Winres.exe (Editor de recursos de Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ce405-144">Winres.exe (Windows Forms Resource Editor)</span></span>](../../framework/tools/winres-exe-windows-forms-resource-editor.md)

   <span data-ttu-id="ce405-145">Describe cómo usar Winres.exe para localizar formularios de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ce405-145">Describes how to use Winres.exe to localize Windows Forms forms.</span></span>
