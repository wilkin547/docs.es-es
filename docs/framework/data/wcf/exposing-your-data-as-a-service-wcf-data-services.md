---
title: Exponer los datos como servicio (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 8e598dde0d85b1d7d4208bf2475a0f6f6eee34a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700993"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a>Exponer los datos como un servicio (WCF Data Services)

WCF Data Services se integra con Visual Studio para permitirle definir con más facilidad servicios para exponer los datos como [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuentes de distribución. Creación de un servicio de datos que expone una fuente de OData implica los siguientes pasos básicos:

1.  **Definir el modelo de datos.** WCF Data Services admite de forma nativa modelos de datos que se basan en el [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md). Para obtener más información, vea [Cómo: Crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).

     WCF Data Services también admite modelos de datos que se basan en objetos de common language runtime (CLR) que devuelven una instancia de la <xref:System.Linq.IQueryable%601> interfaz. Esto permite implementar servicios de datos que están basados en listas, matrices y colecciones en .NET Framework. Para habilitar las operaciones de creación, actualización y eliminación sobre estas estructuras de datos, también debe implementar la interfaz <xref:System.Data.Services.IUpdatable>. Para obtener más información, vea [Cómo: Crear un servicio de datos mediante el proveedor de reflexión](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).

     Para escenarios más avanzados, WCF Data Services incluye un conjunto de proveedores que le permiten definir un modelo de datos basado en tipos de datos en tiempo de ejecución. Para obtener más información, consulte [proveedores de servicios de datos personalizados](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).

2.  **Crear el servicio de datos.** El servicio de datos más básico expone una clase que hereda de la clase <xref:System.Data.Services.DataService%601> , con un tipo `T` que es el nombre completo del espacio de nombres del contenedor de la entidad. Para obtener más información, consulta [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).

3.  **Configurar el servicio de datos.** De forma predeterminada, WCF Data Services deshabilita el acceso a los recursos expuestos por un contenedor de entidades. El <xref:System.Data.Services.DataServiceConfiguration> interfaz le permite configurar el acceso a los recursos y operaciones de servicio, especifique la versión compatible de OData así como definir otros comportamientos de todo el servicio, como el procesamiento por lotes comportamientos o el número máximo de entidades que se pueden devolver en una única respuesta. Para obtener más información, consulte [configurando el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

Para obtener un ejemplo de cómo crear un servicio de datos simples que se basa en la base de datos de ejemplo Northwind, vea [Quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).

## <a name="see-also"></a>Vea también

- [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [Información general](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)