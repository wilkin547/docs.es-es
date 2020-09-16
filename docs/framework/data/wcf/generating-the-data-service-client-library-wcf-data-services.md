---
title: Generar la biblioteca cliente del servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: a6a388f837d00d63a39212843c3fa88b28482b26
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545812"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="88f86-102">Generar la biblioteca cliente del servicio de datos (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="88f86-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="88f86-103">Un servicio de datos que implementa el Open Data Protocol (OData) puede devolver un documento de metadatos de servicio que describe el modelo de datos expuesto por la fuente de OData.</span><span class="sxs-lookup"><span data-stu-id="88f86-103">A data service that implements the Open Data Protocol (OData) can return a service metadata document that describes the data model exposed by the OData feed.</span></span> <span data-ttu-id="88f86-104">Para obtener más información, vea la sección sobre el documento de metadatos del servicio en el artículo [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) .</span><span class="sxs-lookup"><span data-stu-id="88f86-104">For more information, see the Service Metadata Document section in the [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) article.</span></span> <span data-ttu-id="88f86-105">Puede usar el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio para agregar una referencia a un servicio basado en OData.</span><span class="sxs-lookup"><span data-stu-id="88f86-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an OData-based service.</span></span> <span data-ttu-id="88f86-106">Cuando se usa esta herramienta para agregar una referencia a los metadatos devueltos por una fuente de OData en un proyecto de cliente, realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="88f86-106">When you use this tool to add a reference to the metadata returned by an OData feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="88f86-107">Solicita el documento de metadatos del servicio al servicio de datos e interpreta los metadatos devueltos.</span><span class="sxs-lookup"><span data-stu-id="88f86-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="88f86-108">Los metadatos devueltos se almacenan en el proyecto de cliente como un archivo .edmx.</span><span class="sxs-lookup"><span data-stu-id="88f86-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="88f86-109">Este archivo .edmx no se puede abrir utilizando el diseñador de Entity Data Model ya que no tiene el mismo formato que un archivo .edmx utilizado por Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="88f86-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="88f86-110">Puede ver este archivo de metadatos utilizando el editor XML o cualquier editor de texto.</span><span class="sxs-lookup"><span data-stu-id="88f86-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="88f86-111">Para obtener más información, consulte [ \[ MC-EDMX \] : Entity Data Model para el formato de empaquetado de Data Services](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).</span><span class="sxs-lookup"><span data-stu-id="88f86-111">For more information, see [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).</span></span>
  
- <span data-ttu-id="88f86-112">Genera una representación del servicio como una clase de contenedor de entidades que hereda de <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="88f86-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="88f86-113">Esta clase de contenedor de entidades generada es similar al contenedor de entidades generado por las herramientas de Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="88f86-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="88f86-114">Para más información, vea [Información general de Servicios de objeto (Entity Framework)](/previous-versions/bb386871(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="88f86-114">For more information, see [Object Services Overview (Entity Framework)](/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="88f86-115">Genera clases de datos para los tipos de modelo de entidad que detecta en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="88f86-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="88f86-116">Agrega al proyecto una referencia al ensamblado `System.Data.Services.Client`.</span><span class="sxs-lookup"><span data-stu-id="88f86-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="88f86-117">Para obtener más información, vea [Cómo: agregar una referencia de servicio de datos](how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="88f86-117">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="88f86-118">Las clases del servicio de datos del cliente también se pueden generar mediante la herramienta [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="88f86-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="88f86-119">Para obtener más información, vea [Cómo: generar manualmente clases del servicio de datos del cliente](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="88f86-119">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="88f86-120">Asignación de tipos de datos del cliente</span><span class="sxs-lookup"><span data-stu-id="88f86-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="88f86-121">Cuando se usa el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio o la `DataSvcUtil.exe` herramienta para generar clases de datos de cliente que se basan en una fuente de oData, los tipos de datos de .NET Framework se asignan a los tipos primitivos del modelo de datos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="88f86-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an OData feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="88f86-122">Tipo del modelo de datos</span><span class="sxs-lookup"><span data-stu-id="88f86-122">Data model type</span></span>|<span data-ttu-id="88f86-123">Tipo de datos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="88f86-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="88f86-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="88f86-124"><xref:System.Byte> `[]`</span></span>|  
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
  
 <span data-ttu-id="88f86-125">Para obtener más información, consulte la sección tipos de datos primitivos en el artículo [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) .</span><span class="sxs-lookup"><span data-stu-id="88f86-125">For more information, see the Primitive Data Types section in the [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) article.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="88f86-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="88f86-126">See also</span></span>

- [<span data-ttu-id="88f86-127">Biblioteca cliente de Data Services de WCF</span><span class="sxs-lookup"><span data-stu-id="88f86-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="88f86-128">Guía de inicio rápido</span><span class="sxs-lookup"><span data-stu-id="88f86-128">Quickstart</span></span>](quickstart-wcf-data-services.md)
