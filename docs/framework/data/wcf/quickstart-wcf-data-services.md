---
description: 'Más información acerca de: Inicio rápido (Servicios de datos de WCF)'
title: Inicio rápido (Servicios de datos de WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: 92a1b8882f6a7db2ed33f032ad434efd06400421
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794954"
---
# <a name="quickstart-wcf-data-services"></a>Inicio rápido (Servicios de datos de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Esta guía de inicio rápido le ayudará a familiarizarse con Servicios de datos de WCF y el Open Data Protocol (OData) a través de una serie de tareas que admiten los temas de [Introducción](getting-started-with-wcf-data-services.md).

## <a name="what-youll-learn"></a>Temas que se abordarán

En la primera tarea de esta guía de inicio rápido se muestra cómo crear un servicio de datos para exponer una fuente de OData desde la base de datos de ejemplo Northwind. En temas posteriores, tendrá acceso a la fuente de OData mediante un explorador Web y también creará una aplicación cliente Windows Presentation Foundation (WPF) que consume la fuente de OData mediante las bibliotecas de cliente.

## <a name="prerequisites"></a>Requisitos previos

Para completar esta guía de inicio rápido, instale los siguientes componentes:

- Visual Studio

- Instancia de SQL Server. Esto incluye SQL Server Express, que se incluye en una instalación predeterminada de Visual Studio 2015, o como parte de la carga de trabajo de **procesamiento y almacenamiento de datos** en Visual Studio 2017 o posterior.

- Base de datos de ejemplo Northwind. Para instalar la base de datos, ejecute el script Transact-SQL desde las bases de datos de [ejemplo Northwind y pubs para Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).

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
