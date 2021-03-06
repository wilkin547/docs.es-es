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
# <a name="compare-razor-usage-in-aspnet-mvc-and-aspnet-core"></a>Comparar el uso de Razor en ASP.NET MVC y ASP.NET Core

La sintaxis básica de Razor no ha cambiado sustancialmente entre ASP.NET MVC y ASP.NET Core. Sin embargo, hay algunas diferencias, como la introducción de las [aplicaciones auxiliares de etiquetas](/aspnet/core/mvc/views/tag-helpers/intro) y Razor pages, que deben tenerse en cuenta al migrar. Si la aplicación hace un uso intensivo de la funcionalidad personalizada de Razor, consulte la [referencia de sintaxis Razor para ASP.net Core](/aspnet/core/razor-pages) para ver qué cambios pueden ser necesarios al migrar a ASP.net Core.

## <a name="tag-helpers"></a>Asistentes de etiquetas

Los asistentes de etiquetas permiten que el código de servidor participe en la creación y la representación de elementos HTML en archivos de Razor. Ofrecen muchas ventajas con respecto a las aplicaciones auxiliares HTML y deben usarse en lugar de las aplicaciones auxiliares HTML siempre que sea posible. Proporcionan una experiencia de desarrollo compatible con HTML, ya que se parecen a HTML estándar y se omiten con la mayoría de las herramientas diseñadas para editar HTML. Dentro de _Visual Studio_, hay una amplia compatibilidad con IntelliSense para crear marcado HTML y Razor con aplicaciones auxiliares de etiquetas. Las aplicaciones auxiliares de etiquetas pueden proporcionar un comportamiento sencillo o complejo a partir del marcado declarativo en archivos Razor.

## <a name="razor-pages"></a>Páginas de Razor

Razor Pages ofrecen una alternativa a los controladores, acciones y vistas de las aplicaciones basadas en formularios y páginas. [Razor pages se comparan con ASP.NET MVC anteriormente en este capítulo](./comparing-razor-pages-aspnet-mvc.md).

## <a name="references"></a>Referencias

- [Migración de ASP.NET MVC a ASP.NET Core MVC: Controladores y vistas](/aspnet/core/migration/mvc#migrate-controllers-and-views)
- [Asistentes de etiquetas en ASP.NET Core](/aspnet/core/mvc/views/tag-helpers/intro)
- [Introducción a las páginas de Razor en ASP.NET Core](/aspnet/core/razor-pages)
- [Referencia de sintaxis de Razor para ASP.NET Core](/aspnet/core/razor-pages)

>[!div class="step-by-step"]
>[Anterior](controller-differences.md)
>[Siguiente](signalr-differences.md)
