---
title: Comparación de Razor Pages con ASP.NET MVC
description: Razor Pages ofrecen una mejor manera de organizar las responsabilidades que las vistas de MVC tradicionales para las aplicaciones basadas en páginas. Obtenga información sobre cómo se comparan con el enfoque tradicional de ASP.NET MVC en esta sección.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: c188e7336e129fa710002081f1bef1f635cbe1fd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401794"
---
# <a name="compare-razor-pages-to-aspnet-mvc"></a>Comparación de Razor Pages con ASP.NET MVC

Razor Pages es la manera preferida de crear aplicaciones basadas en formularios o páginas en ASP.NET Core. Desde los [documentos](/aspnet/core/razor-pages/), "Razor pages puede hacer que los escenarios centrados en páginas de codificación sean más fáciles y productivos que usar controladores y vistas". Si la aplicación ASP.NET MVC hace un uso intensivo de las vistas, puede que desee considerar la posibilidad de migrar desde acciones y vistas a Razor Pages.

Una aplicación de MVC basada en una vista fuertemente tipada típica usará un controlador para contener una o varias acciones. El controlador interactuará con el dominio o modelo de datos y creará una instancia de una clase ViewModel. Después, esta clase ViewModel se pasa a la vista asociada a esa acción. Con este enfoque, junto con la estructura de carpetas predeterminada de las aplicaciones MVC, para agregar una nueva página a una aplicación, es necesario modificar un controlador en una carpeta, una vista en una subcarpeta anidada de otra carpeta y un ViewModel en otra carpeta.

Razor Pages agrupar la acción (ahora un *controlador*) y el ViewModel (denominado *PageModel*) en una clase y vincular esta clase a la vista (denominada página de Razor). Todos los Razor Pages van a una carpeta *pages* en la raíz del proyecto ASP.net Core. Razor Pages usar una Convención de enrutamiento basada en su nombre y ubicación en esta carpeta. Los controladores se comportan exactamente igual que los métodos de acción pero tienen el verbo HTTP que controlan en su nombre (por ejemplo, `OnGet` ). Tampoco tienen que devolver necesariamente, ya que, de forma predeterminada, se supone que devuelve la página a la que están asociados. Esto tiende a mantener Razor Pages y sus controladores más pequeños y más centrados, al mismo tiempo que facilitan la búsqueda y el trabajo de todos los archivos necesarios para agregar o modificar una parte concreta de una aplicación.

Como parte de un cambio de ASP.NET MVC a ASP.NET Core, los equipos deben considerar si desean migrar controladores y vistas a ASP.NET Core controladores y vistas, o a Razor Pages. Lo más probable es que la primera de ellas requiera un esfuerzo menos bajo, pero no permitirá que el equipo aproveche las ventajas de Razor Pages sobre la organización tradicional de archivos basados en vistas.

## <a name="references"></a>Referencias

- [Introducción a las páginas de Razor en ASP.NET Core](/aspnet/core/razor-pages/)
- [Aplicaciones ASP.NET Core más sencillas con Razor Pages](/archive/msdn-magazine/2017/september/asp-net-core-simpler-asp-net-mvc-apps-with-razor-pages)

>[!div class="step-by-step"]
>[Anterior](routing-differences.md)
>[Siguiente](webapi-differences.md)
