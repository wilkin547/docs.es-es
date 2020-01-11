---
title: Inicio rápido (Servicios de datos de WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: 43cd34ad02f1e2d212ff5e2ff4694591fbed52e5
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900958"
---
# <a name="quickstart-wcf-data-services"></a>Inicio rápido (Servicios de datos de WCF)

Esta guía de inicio rápido le ayudará a familiarizarse con WCF Data Services y el Open Data Protocol (OData) a través de una serie de tareas que admiten los temas de [Introducción](getting-started-with-wcf-data-services.md).

## <a name="what-youll-learn"></a>Lo que aprenderá

En la primera tarea de esta guía de inicio rápido se muestra cómo crear un servicio de datos para exponer una fuente de OData desde la base de datos de ejemplo Northwind. En temas posteriores, tendrá acceso a la fuente de OData mediante un explorador Web y también creará una aplicación cliente Windows Presentation Foundation (WPF) que consume la fuente de OData mediante las bibliotecas de cliente.

## <a name="prerequisites"></a>Requisitos previos

Para completar este tutorial rápido, debe instalar los siguientes componentes:

- Programa para la mejora

- Instancia de SQL Server. Esto incluye SQL Server Express, que se incluye en una instalación predeterminada de Visual Studio 2015, o como parte de la carga de trabajo de **procesamiento y almacenamiento de datos** en Visual Studio 2017 o posterior.

- Base de datos de ejemplo Northwind. Para descargar esta base de datos de ejemplo, consulte la página de descargas, [Bases de datos de ejemplo de SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).

## <a name="wcf-data-services-quickstart-tasks"></a>Tareas del tutorial rápido de WCF Data Services

 [Crear el servicio de datos](creating-the-data-service.md)

 Defina la aplicación ASP.NET, defina el modelo de datos, cree el servicio de datos y habilite el acceso a los recursos.

 [Acceder al servicio desde un explorador Web](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Inicie el servicio desde Visual Studio y obtenga acceso a él enviando solicitudes GET de HTTP a través de un explorador web a las fuentes expuestas.

 [Crear la aplicación cliente de .NET Framework](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Cree una aplicación de WPF para usar la fuente de OData, enlace datos a controles de Windows, cambie los datos en los controles enlazados y, a continuación, envíe los cambios de vuelta al servicio de datos.

> [!NOTE]
> Los archivos de proyecto de una versión completada del tutorial rápido se pueden descargar desde [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Inicio de la guía de inicio rápido](creating-the-data-service.md)

## <a name="see-also"></a>Vea también

- [ADO.NET Entity Framework](../adonet/ef/index.md)
