---
title: Generar la biblioteca cliente del servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 14ea550715c1b224945137f123eed3b53e56cead
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918652"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Generar la biblioteca cliente del servicio de datos (Data Services de WCF)
Un servicio de datos que implementa [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] puede devolver un documento de metadatos de servicio que describe el modelo de datos expuesto por la [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente. Para obtener más información, [consulte OData: Documento](https://go.microsoft.com/fwlink/?LinkId=186070)de metadatos de servicio. Puede usar el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio para agregar una referencia a [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]un servicio basado en. Cuando se usa esta herramienta para agregar una referencia a los metadatos devueltos por una [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente en un proyecto de cliente, realiza las siguientes acciones:  
  
- Solicita el documento de metadatos del servicio al servicio de datos e interpreta los metadatos devueltos.  
  
    > [!NOTE]
    > Los metadatos devueltos se almacenan en el proyecto de cliente como un archivo .edmx. Este archivo .edmx no se puede abrir utilizando el diseñador de Entity Data Model ya que no tiene el mismo formato que un archivo .edmx utilizado por Entity Framework. Puede ver este archivo de metadatos utilizando el editor XML o cualquier editor de texto. Para obtener más información, consulte [ \[MC-EDMX\]: Entity Data Model para la especificación de](https://go.microsoft.com/fwlink/?LinkID=178833) formato de empaquetado de Data Services  
  
- Genera una representación del servicio como una clase de contenedor de entidades que hereda de <xref:System.Data.Services.Client.DataServiceContext>. Esta clase de contenedor de entidades generada es similar al contenedor de entidades generado por las herramientas de Entity Data Model. Para más información, vea [Información general de Servicios de objeto (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).  
  
- Genera clases de datos para los tipos de modelo de entidad que detecta en los metadatos del servicio.  
  
- Agrega al proyecto una referencia al ensamblado `System.Data.Services.Client`.  
  
 Para obtener más información, consulte [Cómo Agregue una referencia](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)de servicio de datos.  
  
 Las clases del servicio de datos del cliente también se pueden generar mediante la herramienta [herramienta datasvcutil. exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) en el símbolo del sistema. Para obtener más información, consulte [Cómo Generar manualmente las clases](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)del servicio de datos del cliente.  
  
## <a name="client-data-type-mapping"></a>Asignación de tipos de datos del cliente  
 Cuando se usa el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio `DataSvcUtil.exe` o la herramienta para generar clases de datos de cliente basadas [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] en una fuente, los tipos de datos de .NET Framework se asignan a los tipos primitivos del modelo de datos de la siguiente manera:  
  
|Tipo del modelo de datos|Tipo de datos de .NET Framework|  
|---------------------|------------------------------|  
|`Edm.Binary`|<xref:System.Byte>`[]`|  
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
  
 Para obtener más información, [consulte OData: Tipos](https://go.microsoft.com/fwlink/?LinkId=186072)de datos primitivos.  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
