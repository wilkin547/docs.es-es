---
title: Exponer los datos como servicio (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 1dc1f0ec12c50c4c97b141a34b468e3367ead75e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780301"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a>Exponer los datos como un servicio (WCF Data Services)

WCF Data Services se integra con Visual Studio para permitirle definir con más facilidad los servicios que exponen los datos como [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuentes. La creación de un servicio de datos que exponga una fuente de OData implica los siguientes pasos básicos:

1. **Defina el modelo de datos.** WCF Data Services admite de forma nativa modelos de datos basados en el [Entity Framework ADO.net](../adonet/ef/index.md). Para obtener más información, vea [Cómo: Cree un servicio de datos mediante un origen](create-a-data-service-using-an-adonet-ef-data-wcf.md)de datos de ADO.NET Entity Framework.

     WCF Data Services también admite modelos de datos basados en objetos Common Language Runtime (CLR) que devuelven una instancia de <xref:System.Linq.IQueryable%601> la interfaz. Esto permite implementar servicios de datos que están basados en listas, matrices y colecciones en .NET Framework. Para habilitar las operaciones de creación, actualización y eliminación sobre estas estructuras de datos, también debe implementar la interfaz <xref:System.Data.Services.IUpdatable>. Para obtener más información, consulte [Cómo Cree un servicio de datos mediante el proveedor](create-a-data-service-using-rp-wcf-data-services.md)de reflexión.

     En escenarios más avanzados, WCF Data Services incluye un conjunto de proveedores que permiten definir un modelo de datos basado en tipos de datos enlazados en tiempo de ejecución. Para obtener más información, vea [proveedores de servicios de datos personalizados](custom-data-service-providers-wcf-data-services.md).

2. **Cree el servicio de datos.** El servicio de datos más básico expone una clase que hereda de la clase <xref:System.Data.Services.DataService%601> , con un tipo `T` que es el nombre completo del espacio de nombres del contenedor de la entidad. Para obtener más información, consulta [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Configure el servicio de datos.** De forma predeterminada, WCF Data Services deshabilita el acceso a los recursos expuestos por un contenedor de entidades. La <xref:System.Data.Services.DataServiceConfiguration> interfaz le permite configurar el acceso a los recursos y las operaciones de servicio, especificar la versión admitida de oData y definir otros comportamientos de todo el servicio, como los comportamientos de procesamiento por lotes o el número máximo de entidades que se pueden devolver. en una sola respuesta. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md).

Para obtener un ejemplo de cómo crear un servicio de datos simple basado en la base de datos de ejemplo Northwind, vea [Inicio rápido](quickstart-wcf-data-services.md).

## <a name="see-also"></a>Vea también

- [Introducción](getting-started-with-wcf-data-services.md)
- [Información general](wcf-data-services-overview.md)
