---
title: Inicio rápido (Servicios de datos de WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121222"
---
# <a name="quickstart-wcf-data-services"></a>Inicio rápido (Servicios de datos de WCF)

Esta guía de inicio rápido le ayuda a familiarizarse con WCF Data Services y el protocolo de datos abiertos (OData) a través de una serie de tareas que admiten los temas de [Introducción](getting-started-with-wcf-data-services.md).

## <a name="what-youll-learn"></a>Temas que se abordarán

La primera tarea de esta guía de inicio rápido muestra cómo crear un servicio de datos para exponer una fuente de OData de la base de datos de ejemplo Northwind. En temas posteriores, tendrá acceso a la fuente de OData mediante un explorador web y también creará una aplicación cliente de Windows Presentation Foundation (WPF) que consume la fuente de OData mediante bibliotecas de cliente.

## <a name="prerequisites"></a>Prerrequisitos

Para completar esta guía de inicio rápido, instale los siguientes componentes:

- Visual Studio

- Una instancia de SQL Server. Esto incluye SQL Server Express, que se incluye en una instalación predeterminada de Visual Studio 2015, o como parte de la carga de trabajo de **almacenamiento y procesamiento** de datos en Visual Studio 2017 o posterior.

- Base de datos de ejemplo Northwind. Para instalar la base de datos, ejecute el script DeTransact-SQL desde [Northwind y las bases](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)de datos de ejemplo pubs para Microsoft SQL Server .

## <a name="wcf-data-services-quickstart-tasks"></a>Tareas de inicio rápido de servicios de datos WCF

 [Crear el servicio de datos](creating-the-data-service.md)

 Defina la aplicación ASP.NET, defina el modelo de datos, cree el servicio de datos y habilite el acceso a los recursos.

 [Acceda al servicio desde un navegador web](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Inicie el servicio desde Visual Studio y obtenga acceso a él enviando solicitudes GET de HTTP a través de un explorador web a las fuentes expuestas.

 [Cree la aplicación cliente de .NET Framework](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Cree una aplicación WPF para consumir la fuente de OData, enlazar datos a controles de Windows, cambiar datos en los controles enlazados y, a continuación, enviar los cambios al servicio de datos.

> [!NOTE]
> Los archivos de proyecto de una versión completa de la guía de inicio rápido se pueden descargar desde [GitHub.](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Inicie la guía de inicio rápido](creating-the-data-service.md)

## <a name="see-also"></a>Vea también

- [ADO.NET Entity Framework](../adonet/ef/index.md)
