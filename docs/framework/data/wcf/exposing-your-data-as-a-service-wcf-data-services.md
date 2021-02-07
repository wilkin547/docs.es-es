---
description: Más información acerca de cómo exponer los datos como un servicio (Servicios de datos de WCF)
title: Exponer los datos como servicio (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 496cf18b264672814295916467e1bff93feebdde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765976"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a>Exponer los datos como un servicio (Servicios de datos de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Servicios de datos de WCF se integra con Visual Studio para permitirle definir con más facilidad los servicios que exponen los datos como fuentes Open Data Protocol (OData). La creación de un servicio de datos que exponga una fuente de OData implica los siguientes pasos básicos:

1. **Defina el modelo de datos.** Servicios de datos de WCF admite de forma nativa modelos de datos basados en el [Entity Framework ADO.net](../adonet/ef/index.md). Para obtener más información, consulte [Cómo: crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework](create-a-data-service-using-an-adonet-ef-data-wcf.md).

     Servicios de datos de WCF también admite modelos de datos basados en objetos Common Language Runtime (CLR) que devuelven una instancia de la <xref:System.Linq.IQueryable%601> interfaz. Esto permite implementar servicios de datos que están basados en listas, matrices y colecciones en .NET Framework. Para habilitar las operaciones de creación, actualización y eliminación sobre estas estructuras de datos, también debe implementar la interfaz <xref:System.Data.Services.IUpdatable>. Para obtener más información, vea [Cómo: crear un servicio de datos mediante el proveedor de reflexión](create-a-data-service-using-rp-wcf-data-services.md).

     En escenarios más avanzados, Servicios de datos de WCF incluye un conjunto de proveedores que permiten definir un modelo de datos basado en tipos de datos enlazados en tiempo de ejecución. Para obtener más información, vea [proveedores de servicios de datos personalizados](custom-data-service-providers-wcf-data-services.md).

2. **Cree el servicio de datos.** El servicio de datos más básico expone una clase que hereda de la clase <xref:System.Data.Services.DataService%601> , con un tipo `T` que es el nombre completo del espacio de nombres del contenedor de la entidad. Para obtener más información, consulta [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Configure el servicio de datos.** De forma predeterminada, Servicios de datos de WCF deshabilita el acceso a los recursos expuestos por un contenedor de entidades. La <xref:System.Data.Services.DataServiceConfiguration> interfaz le permite configurar el acceso a los recursos y las operaciones de servicio, especificar la versión admitida de oData y definir otros comportamientos de todo el servicio, como los comportamientos de procesamiento por lotes o el número máximo de entidades que se pueden devolver en una única respuesta. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md).

Para obtener un ejemplo de cómo crear un servicio de datos simple basado en la base de datos de ejemplo Northwind, vea [Inicio rápido](quickstart-wcf-data-services.md).

## <a name="see-also"></a>Vea también

- [Introducción](getting-started-with-wcf-data-services.md)
- [Información general](wcf-data-services-overview.md)
