---
title: Generar la biblioteca cliente del servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 999cbaa98c26d2d00b7e8f319ee87f8b07d7f5c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357756"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Generar la biblioteca cliente del servicio de datos (Data Services de WCF)
Un servicio de datos que implementa el [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] puede devolver un documento de metadatos de servicio que describe el modelo de datos expuesto por la [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente de distribución. Para obtener más información, consulte [OData: documento de metadatos del servicio](http://go.microsoft.com/fwlink/?LinkId=186070). Puede usar el **Agregar referencia de servicio** cuadro de diálogo de Visual Studio para agregar una referencia a un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-servicio basado en. Cuando usa esta herramienta para agregar una referencia a los metadatos devueltos por un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] de la fuente en un proyecto de cliente, realiza las acciones siguientes:  
  
-   Solicita el documento de metadatos del servicio al servicio de datos e interpreta los metadatos devueltos.  
  
    > [!NOTE]
    >  Los metadatos devueltos se almacenan en el proyecto de cliente como un archivo .edmx. Este archivo .edmx no se puede abrir utilizando el diseñador de Entity Data Model ya que no tiene el mismo formato que un archivo .edmx utilizado por Entity Framework. Puede ver este archivo de metadatos utilizando el editor XML o cualquier editor de texto. Para obtener más información, consulte el [ \[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833) especificación  
  
-   Genera una representación del servicio como una clase de contenedor de entidades que hereda de <xref:System.Data.Services.Client.DataServiceContext>. Esta clase de contenedor de entidades generada es similar al contenedor de entidades generado por las herramientas de Entity Data Model. Para más información, vea [Información general de Servicios de objeto (Entity Framework)](http://msdn.microsoft.com/library/43014cf9-c9cb-4538-bfbb-197820b60038).  
  
-   Genera clases de datos para los tipos de modelo de entidad que detecta en los metadatos del servicio.  
  
-   Agrega al proyecto una referencia al ensamblado `System.Data.Services.Client`.  
  
 Para obtener más información, consulte [Cómo: agregar una referencia de servicio de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Las clases de servicio de datos de cliente también puede generarse utilizando la [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) herramienta en el símbolo del sistema. Para obtener más información, consulte [Cómo: manualmente generar datos clases del servicio cliente](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Asignación de tipos de datos del cliente  
 Cuando se usa el **Agregar referencia de servicio** cuadro de diálogo de Visual Studio o la `DataSvcUtil.exe` herramienta para generar clases de datos de cliente que se basan en un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente de distribución, los tipos de datos de .NET Framework se asignan a los tipos primitivos de la modelo de datos como sigue:  
  
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
  
 Para obtener más información, consulte [OData: tipos de datos primitivos](http://go.microsoft.com/fwlink/?LinkId=186072).  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
