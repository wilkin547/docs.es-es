---
title: Generar la biblioteca cliente del servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: d53f2d209d6fb0a6f3cadb96245338060ece87db
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780290"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="22127-102">Generar la biblioteca cliente del servicio de datos (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="22127-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="22127-103">Un servicio de datos que implementa [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] puede devolver un documento de metadatos de servicio que describe el modelo de datos expuesto por la [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente.</span><span class="sxs-lookup"><span data-stu-id="22127-103">A data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] can return a service metadata document that describes the data model exposed by the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span> <span data-ttu-id="22127-104">Para obtener más información, [consulte OData: Documento](https://go.microsoft.com/fwlink/?LinkId=186070)de metadatos de servicio.</span><span class="sxs-lookup"><span data-stu-id="22127-104">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="22127-105">Puede usar el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio para agregar una referencia a [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]un servicio basado en.</span><span class="sxs-lookup"><span data-stu-id="22127-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service.</span></span> <span data-ttu-id="22127-106">Cuando se usa esta herramienta para agregar una referencia a los metadatos devueltos por una [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente en un proyecto de cliente, realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="22127-106">When you use this tool to add a reference to the metadata returned by an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="22127-107">Solicita el documento de metadatos del servicio al servicio de datos e interpreta los metadatos devueltos.</span><span class="sxs-lookup"><span data-stu-id="22127-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="22127-108">Los metadatos devueltos se almacenan en el proyecto de cliente como un archivo .edmx.</span><span class="sxs-lookup"><span data-stu-id="22127-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="22127-109">Este archivo .edmx no se puede abrir utilizando el diseñador de Entity Data Model ya que no tiene el mismo formato que un archivo .edmx utilizado por Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="22127-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="22127-110">Puede ver este archivo de metadatos utilizando el editor XML o cualquier editor de texto.</span><span class="sxs-lookup"><span data-stu-id="22127-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="22127-111">Para obtener más información, consulte [ \[MC-EDMX\]: Entity Data Model para la especificación de](https://go.microsoft.com/fwlink/?LinkID=178833) formato de empaquetado de Data Services</span><span class="sxs-lookup"><span data-stu-id="22127-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
- <span data-ttu-id="22127-112">Genera una representación del servicio como una clase de contenedor de entidades que hereda de <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="22127-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="22127-113">Esta clase de contenedor de entidades generada es similar al contenedor de entidades generado por las herramientas de Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="22127-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="22127-114">Para más información, vea [Información general de Servicios de objeto (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="22127-114">For more information, see [Object Services Overview (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="22127-115">Genera clases de datos para los tipos de modelo de entidad que detecta en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="22127-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="22127-116">Agrega al proyecto una referencia al ensamblado `System.Data.Services.Client`.</span><span class="sxs-lookup"><span data-stu-id="22127-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="22127-117">Para obtener más información, consulte [Cómo Agregue una referencia](how-to-add-a-data-service-reference-wcf-data-services.md)de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="22127-117">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="22127-118">Las clases del servicio de datos del cliente también se pueden generar mediante la herramienta [herramienta datasvcutil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="22127-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="22127-119">Para obtener más información, consulte [Cómo Generar manualmente las clases](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)del servicio de datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="22127-119">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="22127-120">Asignación de tipos de datos del cliente</span><span class="sxs-lookup"><span data-stu-id="22127-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="22127-121">Cuando se usa el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio `DataSvcUtil.exe` o la herramienta para generar clases de datos de cliente basadas [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] en una fuente, los tipos de datos de .NET Framework se asignan a los tipos primitivos del modelo de datos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="22127-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="22127-122">Tipo del modelo de datos</span><span class="sxs-lookup"><span data-stu-id="22127-122">Data model type</span></span>|<span data-ttu-id="22127-123">Tipo de datos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="22127-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="22127-124"><xref:System.Byte>`[]`</span><span class="sxs-lookup"><span data-stu-id="22127-124"><xref:System.Byte> `[]`</span></span>|  
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
  
 <span data-ttu-id="22127-125">Para obtener más información, [consulte OData: Tipos](https://go.microsoft.com/fwlink/?LinkId=186072)de datos primitivos.</span><span class="sxs-lookup"><span data-stu-id="22127-125">For more information, see [OData: Primitive Data Types](https://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22127-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="22127-126">See also</span></span>

- [<span data-ttu-id="22127-127">Biblioteca cliente de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="22127-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="22127-128">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="22127-128">Quickstart</span></span>](quickstart-wcf-data-services.md)
