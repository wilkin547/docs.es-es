---
title: 'Cómo: Utilizar Svcutil.exe para descargar los documentos de metadatos'
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 359cdb58ef65c9fb69c0ecfc759f70164a369cce
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212115"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a><span data-ttu-id="5e180-102">Cómo: Utilizar Svcutil.exe para descargar los documentos de metadatos</span><span class="sxs-lookup"><span data-stu-id="5e180-102">How to: Use Svcutil.exe to Download Metadata Documents</span></span>
<span data-ttu-id="5e180-103">Puede utilizar Svcutil.exe para descargar metadatos de los servicios en ejecución y para guardar los metadatos en archivos locales.</span><span class="sxs-lookup"><span data-stu-id="5e180-103">You can use Svcutil.exe to download metadata from running services and to save the metadata to local files.</span></span> <span data-ttu-id="5e180-104">En el caso de los esquemas de dirección URL HTTP y HTTPS, SvcUtil. exe intenta recuperar metadatos mediante WS-MetadataExchange y la [detección de servicios Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5e180-104">For HTTP and HTTPS URL schemes, Svcutil.exe attempts to retrieve metadata using WS-MetadataExchange and [XML Web Service Discovery](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)).</span></span> <span data-ttu-id="5e180-105">Para todos los otros esquemas de URL, Svcutil.exe utiliza sólo WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="5e180-105">For all other URL schemes, Svcutil.exe uses only WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="5e180-106">De forma predeterminada, Svcutil.exe utiliza los enlaces definidos en la clase <xref:System.ServiceModel.Description.MetadataExchangeBindings>.</span><span class="sxs-lookup"><span data-stu-id="5e180-106">By default, Svcutil.exe uses the bindings defined in the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class.</span></span> <span data-ttu-id="5e180-107">Para configurar el enlace utilizado para WS-MetadataExchange, debe definir un extremo de cliente en el archivo de configuración para Svcutil.exe (svcutil.exe.config) que utiliza el contrato `IMetadataExchange` y que tiene el mismo nombre que el esquema del Identificador uniforme de recursos (URI) de la dirección del extremo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5e180-107">To configure the binding used for WS-MetadataExchange, you must define a client endpoint in the configuration file for Svcutil.exe (svcutil.exe.config) that uses the `IMetadataExchange` contract and that has the same name as the Uniform Resource Identifier (URI) scheme of the metadata endpoint address.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="5e180-108">Al ejecutar SvcUtil. exe para obtener los metadatos de un servicio que expone dos contratos de servicio diferentes, cada uno de los cuales contiene una operación con el mismo nombre, SvcUtil. exe muestra un error que indica "no se pueden obtener metadatos de...". Por ejemplo, si tiene un servicio que expone un contrato de servicio denominado `ICarService` que tiene una operación `Get(Car c)` y el mismo servicio expone un contrato de servicio denominado `IBookService` que tiene una operación `Get(Book b)`.</span><span class="sxs-lookup"><span data-stu-id="5e180-108">When running Svcutil.exe to get metadata for a service that exposes two different service contracts that each contain an operation of the same name, Svcutil.exe displays an error saying, "Cannot obtain Metadata from ...." For example, if you have a service that exposes a service contract called `ICarService` that has an operation `Get(Car c)` and the same service exposes a service contract called `IBookService` that has an operation `Get(Book b)`.</span></span> <span data-ttu-id="5e180-109">Para solucionar este problema, realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e180-109">To work around this issue, do one of the following:</span></span>
>
> - <span data-ttu-id="5e180-110">Cambie el nombre de una de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="5e180-110">Rename one of the operations.</span></span>
> - <span data-ttu-id="5e180-111">Establezca el <xref:System.ServiceModel.OperationContractAttribute.Name%2A> en un nombre distinto.</span><span class="sxs-lookup"><span data-stu-id="5e180-111">Set the <xref:System.ServiceModel.OperationContractAttribute.Name%2A> to a different name.</span></span>
> - <span data-ttu-id="5e180-112">Establezca el espacio de nombres de una de las operaciones en un espacio de nombres distinto mediante la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="5e180-112">Set one of the operations' namespaces to a different namespace using the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>
  
## <a name="to-download-metadata-using-svcutilexe"></a><span data-ttu-id="5e180-113">Para descargar metadatos mediante Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="5e180-113">To download metadata using Svcutil.exe</span></span>  
  
1. <span data-ttu-id="5e180-114">Busque la herramienta Svcutil.exe en la ubicación siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e180-114">Locate the Svcutil.exe tool at the following location:</span></span>  
  
     <span data-ttu-id="5e180-115">C:\Archivos de programa\Microsoft SDKs\Windows\v1.0.\bin</span><span class="sxs-lookup"><span data-stu-id="5e180-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span></span>  
  
2. <span data-ttu-id="5e180-116">En el símbolo del sistema, inicie la herramienta mediante el formato siguiente.</span><span class="sxs-lookup"><span data-stu-id="5e180-116">At the command prompt, launch the tool using the following format.</span></span>  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     <span data-ttu-id="5e180-117">Debe especificar la opción `/t:metadata` para descargar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="5e180-117">You must specify the `/t:metadata` option to download metadata.</span></span> <span data-ttu-id="5e180-118">De lo contrario, se generan el código de cliente y la configuración.</span><span class="sxs-lookup"><span data-stu-id="5e180-118">Otherwise, client code and configuration are generated.</span></span>  
  
3. <span data-ttu-id="5e180-119">En el <`url`argumento > se especifica la dirección URL de un extremo de servicio que proporciona metadatos o un documento de metadatos hospedado en línea.</span><span class="sxs-lookup"><span data-stu-id="5e180-119">The <`url`>argument specifies the URL to a service endpoint that provides metadata or to a metadata document hosted online.</span></span> <span data-ttu-id="5e180-120">La <`epr`argumento > especifica la ruta de acceso a un archivo XML que contiene un `EndpointAddress` de WS-Addressing para un extremo de servicio que admite WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="5e180-120">The <`epr`> argument specifies the path to an XML file that contains a WS-Addressing `EndpointAddress` for a service endpoint that supports WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="5e180-121">Para obtener más opciones sobre el uso de esta herramienta para la descarga de metadatos, vea [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5e180-121">For more options about using this tool for metadata download, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e180-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e180-122">Example</span></span>  
 <span data-ttu-id="5e180-123">El comando siguiente descarga los documentos de metadatos de un servicio en ejecución.</span><span class="sxs-lookup"><span data-stu-id="5e180-123">The following command downloads metadata documents from a running service.</span></span>  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e180-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e180-124">See also</span></span>

- [<span data-ttu-id="5e180-125">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="5e180-125">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
