---
title: Generar la biblioteca cliente del servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 050a791736e90b5daf46fd272197ca21a220afb0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172624"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Generar la biblioteca cliente del servicio de datos (Data Services de WCF)

Un servicio de datos que implementa el Open Data Protocol (OData) puede devolver un documento de metadatos de servicio que describe el modelo de datos expuesto por la fuente de OData. Para obtener más información, vea la sección sobre el documento de metadatos del servicio en el artículo [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) . Puede usar el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio para agregar una referencia a un servicio basado en OData. Cuando se usa esta herramienta para agregar una referencia a los metadatos devueltos por una fuente de OData en un proyecto de cliente, realiza las siguientes acciones:  
  
- Solicita el documento de metadatos del servicio al servicio de datos e interpreta los metadatos devueltos.  
  
    > [!NOTE]
    > Los metadatos devueltos se almacenan en el proyecto de cliente como un archivo .edmx. Este archivo .edmx no se puede abrir utilizando el diseñador de Entity Data Model ya que no tiene el mismo formato que un archivo .edmx utilizado por Entity Framework. Puede ver este archivo de metadatos utilizando el editor XML o cualquier editor de texto. Para obtener más información, consulte [ \[ MC-EDMX \] : Entity Data Model para el formato de empaquetado de Data Services](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).
  
- Genera una representación del servicio como una clase de contenedor de entidades que hereda de <xref:System.Data.Services.Client.DataServiceContext>. Esta clase de contenedor de entidades generada es similar al contenedor de entidades generado por las herramientas de Entity Data Model. Para más información, vea [Información general de Servicios de objeto (Entity Framework)](/previous-versions/bb386871(v=vs.100)).  
  
- Genera clases de datos para los tipos de modelo de entidad que detecta en los metadatos del servicio.  
  
- Agrega al proyecto una referencia al ensamblado `System.Data.Services.Client`.  
  
 Para obtener más información, vea [Cómo: agregar una referencia de servicio de datos](how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Las clases del servicio de datos del cliente también se pueden generar mediante la herramienta [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) en el símbolo del sistema. Para obtener más información, vea [Cómo: generar manualmente clases del servicio de datos del cliente](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Asignación de tipos de datos del cliente  

 Cuando se usa el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio o la `DataSvcUtil.exe` herramienta para generar clases de datos de cliente que se basan en una fuente de oData, los tipos de datos de .NET Framework se asignan a los tipos primitivos del modelo de datos de la siguiente manera:  
  
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
  
 Para obtener más información, consulte la sección tipos de datos primitivos en el artículo [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) .
  
## <a name="see-also"></a>Consulte también

- [Biblioteca cliente de Data Services de WCF](wcf-data-services-client-library.md)
- [Guía de inicio rápido](quickstart-wcf-data-services.md)
