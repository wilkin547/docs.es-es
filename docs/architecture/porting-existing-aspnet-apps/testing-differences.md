---
title: Comparar las opciones de prueba entre ASP.NET MVC y ASP.NET Core
description: ¿En qué se diferencian las pruebas entre las aplicaciones ASP.NET MVC y las aplicaciones ASP.NET Core?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: f0907d09df058c07ed993c251868f00bc28b0736
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401689"
---
# <a name="compare-testing-options-between-aspnet-mvc-and-aspnet-core"></a>Comparar las opciones de prueba entre ASP.NET MVC y ASP.NET Core

Las aplicaciones MVC de ASP.NET admiten pruebas unitarias de controladores, pero este enfoque a menudo omite muchas características de MVC como enrutamiento, autorización, enlace de modelos, validación de modelos, filtros, etc. Para probar estas características de MVC además de la lógica dentro de la propia acción del controlador, con frecuencia la aplicación debe implementarse y probarse con una herramienta como Selenium. Estas pruebas son considerablemente más caras, más frágiles y más lentas que las pruebas unitarias típicas que se pueden ejecutar sin necesidad de hospedar y ejecutar toda la aplicación.

Los [controladores de ASP.net Core pueden ser pruebas unitarias](/aspnet/core/mvc/controllers/testing) , al igual que los controladores ASP.NET MVC, pero con las mismas limitaciones. Sin embargo, [ASP.net Core admite también pruebas de integración rápidas y fáciles de usar](/aspnet/core/test/integration-tests) . Las pruebas de integración se hospedan en una `TestHost` clase y normalmente se configuran en un personalizado `WebApplicationFactory` que puede reemplazar o reemplazar las dependencias de la aplicación. Por ejemplo, con frecuencia durante las pruebas de integración, la aplicación se destinará a un origen de datos diferente y puede reemplazar los servicios que envían mensajes de correo electrónico con implementaciones falsas o ficticias.

ASP.NET MVC y Web API no eran compatibles con nada, como los escenarios de prueba de integración disponibles en ASP.NET Core. En cualquier esfuerzo de migración, debe asignar el tiempo necesario para escribir algunas pruebas de integración para el sistema recién migrado con el fin de asegurarse de que funciona según lo previsto y continúa haciéndolo. Incluso si no ha escrito pruebas de la lógica de la aplicación Web antes de la migración, debe tener en cuenta la posibilidad de hacerlo a medida que vaya a ASP.NET Core.

## <a name="references"></a>Referencias

- [Crear pruebas unitarias para aplicaciones de ASP.NET MVC](/aspnet/mvc/overview/older-versions-1/unit-testing/creating-unit-tests-for-asp-net-mvc-applications-cs)
- [Lógica del controlador de pruebas unitarias en ASP.NET Core](/aspnet/core/mvc/controllers/testing)
- [Pruebas de integración en ASP.NET Core](/aspnet/core/test/integration-tests)

>[!div class="step-by-step"]
>[Anterior](signalr-differences.md)
>[Siguiente](migrate-large-solutions.md)
