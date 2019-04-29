---
title: Generar la biblioteca cliente del servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 96b7bfabef589464e99e808d19f0dee6cfb23536
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765666"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Generar la biblioteca cliente del servicio de datos (Data Services de WCF)
Un servicio de datos que implementa el [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] puede devolver un documento de metadatos de servicio que describe el modelo de datos expuesto por la [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuentes de distribución. Para obtener más información, consulte [OData: Documento de metadatos de servicio](https://go.microsoft.com/fwlink/?LinkId=186070). Puede usar el **Add Service Reference** cuadro de diálogo de Visual Studio para agregar una referencia a un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-servicio basado en. Cuando use esta herramienta para agregar una referencia a los metadatos devueltos por una [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] la fuente en un proyecto de cliente, realiza las acciones siguientes:  
  
- Solicita el documento de metadatos del servicio al servicio de datos e interpreta los metadatos devueltos.  
  
    > [!NOTE]
    >  Los metadatos devueltos se almacenan en el proyecto de cliente como un archivo .edmx. Este archivo .edmx no se puede abrir utilizando el diseñador de Entity Data Model ya que no tiene el mismo formato que un archivo .edmx utilizado por Entity Framework. Puede ver este archivo de metadatos utilizando el editor XML o cualquier editor de texto. Para obtener más información, consulte el [ \[MC-EDMX\]: Entity Data Model para Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) especificación  
  
- Genera una representación del servicio como una clase de contenedor de entidades que hereda de <xref:System.Data.Services.Client.DataServiceContext>. Esta clase de contenedor de entidades generada es similar al contenedor de entidades generado por las herramientas de Entity Data Model. Para más información, vea [Información general de Servicios de objeto (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).  
  
- Genera clases de datos para los tipos de modelo de entidad que detecta en los metadatos del servicio.  
  
- Agrega al proyecto una referencia al ensamblado `System.Data.Services.Client`.  
  
 Para obtener más información, vea [Cómo: Agregar una referencia de servicio de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 También se pueden generar las clases de servicio de datos de cliente mediante el uso de la [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) herramienta en el símbolo del sistema. Para obtener más información, vea [Cómo: Generar manualmente clases del servicio de datos de cliente](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Asignación de tipos de datos del cliente  
 Cuando se usa el **Add Service Reference** cuadro de diálogo de Visual Studio o el `DataSvcUtil.exe` herramienta para generar clases de datos de cliente que se basan en un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente, los tipos de datos de .NET Framework se asignan a los tipos primitivos de la modelo de datos como sigue:  
  
|Tipo del modelo de datos|Tipo de datos de .NET Framework|  
|---------------------|------------------------------|  
|`Edm.Binary`|<xref:System.Byte> `[]`|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 Para obtener más información, consulte [OData: Tipos de datos primitivos](https://go.microsoft.com/fwlink/?LinkId=186072).  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
