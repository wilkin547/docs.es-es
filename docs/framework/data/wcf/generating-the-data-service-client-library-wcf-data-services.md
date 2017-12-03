---
title: Generar la biblioteca cliente del servicio de datos (Data Services de WCF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 46ddf167a6cbc0ba6c73cfc53020ad33dbf10a2e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="54ec7-102">Generar la biblioteca cliente del servicio de datos (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="54ec7-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="54ec7-103">Un servicio de datos que implementa el [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] puede devolver un documento de metadatos de servicio que describe el modelo de datos expuesto por la [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente de distribución.</span><span class="sxs-lookup"><span data-stu-id="54ec7-103">A data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] can return a service metadata document that describes the data model exposed by the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span> <span data-ttu-id="54ec7-104">Para obtener más información, consulte [OData: documento de metadatos del servicio](http://go.microsoft.com/fwlink/?LinkId=186070).</span><span class="sxs-lookup"><span data-stu-id="54ec7-104">For more information, see [OData: Service Metadata Document](http://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="54ec7-105">Puede usar el **Agregar referencia de servicio** cuadro de diálogo de Visual Studio para agregar una referencia a un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-servicio basado en.</span><span class="sxs-lookup"><span data-stu-id="54ec7-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service.</span></span> <span data-ttu-id="54ec7-106">Cuando usa esta herramienta para agregar una referencia a los metadatos devueltos por un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] de la fuente en un proyecto de cliente, realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="54ec7-106">When you use this tool to add a reference to the metadata returned by an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in a client project, it performs the following actions:</span></span>  
  
-   <span data-ttu-id="54ec7-107">Solicita el documento de metadatos del servicio al servicio de datos e interpreta los metadatos devueltos.</span><span class="sxs-lookup"><span data-stu-id="54ec7-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54ec7-108">Los metadatos devueltos se almacenan en el proyecto de cliente como un archivo .edmx.</span><span class="sxs-lookup"><span data-stu-id="54ec7-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="54ec7-109">Este archivo .edmx no se puede abrir utilizando el diseñador de Entity Data Model ya que no tiene el mismo formato que un archivo .edmx utilizado por Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="54ec7-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="54ec7-110">Puede ver este archivo de metadatos utilizando el editor XML o cualquier editor de texto.</span><span class="sxs-lookup"><span data-stu-id="54ec7-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="54ec7-111">Para obtener más información, consulte el [ \[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833) especificación</span><span class="sxs-lookup"><span data-stu-id="54ec7-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
-   <span data-ttu-id="54ec7-112">Genera una representación del servicio como una clase de contenedor de entidades que hereda de <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="54ec7-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="54ec7-113">Esta clase de contenedor de entidades generada es similar al contenedor de entidades generado por las herramientas de Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="54ec7-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="54ec7-114">Para obtener más información, consulte [Object Services Overview (Entity Framework)](http://msdn.microsoft.com/en-us/43014cf9-c9cb-4538-bfbb-197820b60038).</span><span class="sxs-lookup"><span data-stu-id="54ec7-114">For more information, see [Object Services Overview (Entity Framework)](http://msdn.microsoft.com/en-us/43014cf9-c9cb-4538-bfbb-197820b60038).</span></span>  
  
-   <span data-ttu-id="54ec7-115">Genera clases de datos para los tipos de modelo de entidad que detecta en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="54ec7-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
-   <span data-ttu-id="54ec7-116">Agrega al proyecto una referencia al ensamblado `System.Data.Services.Client`.</span><span class="sxs-lookup"><span data-stu-id="54ec7-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="54ec7-117">Para obtener más información, consulte [Cómo: agregar una referencia de servicio de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="54ec7-117">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="54ec7-118">Las clases de servicio de datos de cliente también puede generarse utilizando la [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) herramienta en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="54ec7-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="54ec7-119">Para obtener más información, consulte [Cómo: manualmente generar datos clases del servicio cliente](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="54ec7-119">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="54ec7-120">Asignación de tipos de datos del cliente</span><span class="sxs-lookup"><span data-stu-id="54ec7-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="54ec7-121">Cuando se usa el **Agregar referencia de servicio** cuadro de diálogo de Visual Studio o la `DataSvcUtil.exe` herramienta para generar clases de datos de cliente que se basan en un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente de distribución, los tipos de datos de .NET Framework se asignan a los tipos primitivos de la modelo de datos como sigue:</span><span class="sxs-lookup"><span data-stu-id="54ec7-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="54ec7-122">Tipo del modelo de datos</span><span class="sxs-lookup"><span data-stu-id="54ec7-122">Data model type</span></span>|<span data-ttu-id="54ec7-123">Tipo de datos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="54ec7-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="54ec7-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="54ec7-124"><xref:System.Byte> `[]`</span></span>|  
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
  
 <span data-ttu-id="54ec7-125">Para obtener más información, consulte [OData: tipos de datos primitivos](http://go.microsoft.com/fwlink/?LinkId=186072).</span><span class="sxs-lookup"><span data-stu-id="54ec7-125">For more information, see [OData: Primitive Data Types](http://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ec7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="54ec7-126">See Also</span></span>  
 [<span data-ttu-id="54ec7-127">Biblioteca cliente de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="54ec7-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [<span data-ttu-id="54ec7-128">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="54ec7-128">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
