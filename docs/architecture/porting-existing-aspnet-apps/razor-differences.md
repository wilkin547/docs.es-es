---
title: Comparar el uso de Razor en ASP.NET MVC y ASP.NET Core
description: ¿Cómo difiere Razor entre ASP.NET MVC y ASP.NET Core?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: a9f7fa2e6b8c0c6bf61c743cf8c956b1ad09713c
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401719"
---
# <a name="compare-razor-usage-in-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="e4a96-103">Comparar el uso de Razor en ASP.NET MVC y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e4a96-103">Compare Razor usage in ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="e4a96-104">La sintaxis básica de Razor no ha cambiado sustancialmente entre ASP.NET MVC y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e4a96-104">The basic syntax of Razor hasn't changed substantially between ASP.NET MVC and ASP.NET Core.</span></span> <span data-ttu-id="e4a96-105">Sin embargo, hay algunas diferencias, como la introducción de las [aplicaciones auxiliares de etiquetas](/aspnet/core/mvc/views/tag-helpers/intro) y Razor pages, que deben tenerse en cuenta al migrar.</span><span class="sxs-lookup"><span data-stu-id="e4a96-105">However, there are certain differences, such as the introduction of [Tag Helpers](/aspnet/core/mvc/views/tag-helpers/intro) and Razor Pages, that should be considered when migrating.</span></span> <span data-ttu-id="e4a96-106">Si la aplicación hace un uso intensivo de la funcionalidad personalizada de Razor, consulte la [referencia de sintaxis Razor para ASP.net Core](/aspnet/core/razor-pages) para ver qué cambios pueden ser necesarios al migrar a ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="e4a96-106">If your app makes heavy use of custom Razor functionality, refer to the [Razor syntax reference for ASP.NET Core](/aspnet/core/razor-pages) to see what changes may be required when you migrate to ASP.NET Core.</span></span>

## <a name="tag-helpers"></a><span data-ttu-id="e4a96-107">Asistentes de etiquetas</span><span class="sxs-lookup"><span data-stu-id="e4a96-107">Tag Helpers</span></span>

<span data-ttu-id="e4a96-108">Los asistentes de etiquetas permiten que el código de servidor participe en la creación y la representación de elementos HTML en archivos de Razor.</span><span class="sxs-lookup"><span data-stu-id="e4a96-108">Tag Helpers enable server-side code to participate in creating and rendering HTML elements in Razor files.</span></span> <span data-ttu-id="e4a96-109">Ofrecen muchas ventajas con respecto a las aplicaciones auxiliares HTML y deben usarse en lugar de las aplicaciones auxiliares HTML siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="e4a96-109">They offer many advantages over HTML Helpers and should be used in place of HTML Helpers wherever possible.</span></span> <span data-ttu-id="e4a96-110">Proporcionan una experiencia de desarrollo compatible con HTML, ya que se parecen a HTML estándar y se omiten con la mayoría de las herramientas diseñadas para editar HTML.</span><span class="sxs-lookup"><span data-stu-id="e4a96-110">They provide an HTML-friendly development experience, since they look like standard HTML and are ignored by most tooling designed to edit HTML.</span></span> <span data-ttu-id="e4a96-111">Dentro de _Visual Studio_, hay una amplia compatibilidad con IntelliSense para crear marcado HTML y Razor con aplicaciones auxiliares de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="e4a96-111">Within _Visual Studio_, there's rich IntelliSense support for creating HTML and Razor markup with Tag Helpers.</span></span> <span data-ttu-id="e4a96-112">Las aplicaciones auxiliares de etiquetas pueden proporcionar un comportamiento sencillo o complejo a partir del marcado declarativo en archivos Razor.</span><span class="sxs-lookup"><span data-stu-id="e4a96-112">Tag Helpers can provide simple or complex behavior from declarative markup in Razor files.</span></span>

## <a name="razor-pages"></a><span data-ttu-id="e4a96-113">Páginas de Razor</span><span class="sxs-lookup"><span data-stu-id="e4a96-113">Razor Pages</span></span>

<span data-ttu-id="e4a96-114">Razor Pages ofrecen una alternativa a los controladores, acciones y vistas de las aplicaciones basadas en formularios y páginas.</span><span class="sxs-lookup"><span data-stu-id="e4a96-114">Razor Pages offer an alternative to controllers, actions, and views for page- and form-based apps.</span></span> <span data-ttu-id="e4a96-115">[Razor pages se comparan con ASP.NET MVC anteriormente en este capítulo](./comparing-razor-pages-aspnet-mvc.md).</span><span class="sxs-lookup"><span data-stu-id="e4a96-115">[Razor Pages were compared to ASP.NET MVC earlier in this chapter](./comparing-razor-pages-aspnet-mvc.md).</span></span>

## <a name="references"></a><span data-ttu-id="e4a96-116">Referencias</span><span class="sxs-lookup"><span data-stu-id="e4a96-116">References</span></span>

- [<span data-ttu-id="e4a96-117">Migración de ASP.NET MVC a ASP.NET Core MVC: Controladores y vistas</span><span class="sxs-lookup"><span data-stu-id="e4a96-117">Migrate from ASP.NET MVC to ASP.NET Core MVC: Controllers and Views</span></span>](/aspnet/core/migration/mvc#migrate-controllers-and-views)
- [<span data-ttu-id="e4a96-118">Asistentes de etiquetas en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e4a96-118">Tag Helpers in ASP.NET Core</span></span>](/aspnet/core/mvc/views/tag-helpers/intro)
- [<span data-ttu-id="e4a96-119">Introducción a las páginas de Razor en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e4a96-119">Introduction to Razor Pages in ASP.NET Core</span></span>](/aspnet/core/razor-pages)
- [<span data-ttu-id="e4a96-120">Referencia de sintaxis de Razor para ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e4a96-120">Razor syntax reference for ASP.NET Core</span></span>](/aspnet/core/razor-pages)

>[!div class="step-by-step"]
><span data-ttu-id="e4a96-121">[Anterior](controller-differences.md)
>[Siguiente](signalr-differences.md)</span><span class="sxs-lookup"><span data-stu-id="e4a96-121">[Previous](controller-differences.md)
[Next](signalr-differences.md)</span></span>
