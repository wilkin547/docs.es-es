---
title: Procedimiento para configurar un enlace de WS-Metadata Exchange personalizado
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 6459e3f0cf0ab72af8027bd6802a0e7aa574aece
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635785"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a><span data-ttu-id="0a968-102">Procedimiento para configurar un enlace de WS-Metadata Exchange personalizado</span><span class="sxs-lookup"><span data-stu-id="0a968-102">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>

<span data-ttu-id="0a968-103">En este artículo se explica cómo configurar un enlace de intercambio WS-Metadata personalizado.</span><span class="sxs-lookup"><span data-stu-id="0a968-103">This article explains how to configure a custom WS-Metadata exchange binding.</span></span> <span data-ttu-id="0a968-104">Windows Communication Foundation (WCF) incluye cuatro enlaces de metadatos definidos por el sistema, pero puede publicar metadatos mediante cualquier enlace que desee.</span><span class="sxs-lookup"><span data-stu-id="0a968-104">Windows Communication Foundation (WCF) includes four system-defined metadata bindings, but you can publish metadata using any binding you want.</span></span> <span data-ttu-id="0a968-105">En este artículo se muestra `wsHttpBinding`cómo publicar metadatos mediante el archivo .</span><span class="sxs-lookup"><span data-stu-id="0a968-105">This article shows you how to publish metadata using the `wsHttpBinding`.</span></span> <span data-ttu-id="0a968-106">Este enlace le da la opción de exponer los metadatos de una manera segura.</span><span class="sxs-lookup"><span data-stu-id="0a968-106">This binding gives you the option of exposing metadata in a secure way.</span></span> <span data-ttu-id="0a968-107">El código de este artículo se basa en [introducción](../samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="0a968-107">The code in this article is based on the [Getting Started](../samples/getting-started-sample.md).</span></span>  
  
### <a name="using-a-configuration-file"></a><span data-ttu-id="0a968-108">El uso de un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="0a968-108">Using a configuration file</span></span>  
  
1. <span data-ttu-id="0a968-109">En el archivo de configuración del servicio, agregue un comportamiento del servicio que contenga la etiqueta `serviceMetadata`:</span><span class="sxs-lookup"><span data-stu-id="0a968-109">In the service's configuration file, add a service behavior that contains the `serviceMetadata` tag:</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="0a968-110">Agregue un atributo `behaviorConfiguration` a la etiqueta del servicio que hace referencia a este nuevo comportamiento:</span><span class="sxs-lookup"><span data-stu-id="0a968-110">Add a `behaviorConfiguration` attribute to the service tag that references this new behavior:</span></span>  
  
    ```xml  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior" />
    ```  
  
3. <span data-ttu-id="0a968-111">Agregue un punto de conexión de metadatos que especifique mex como dirección, `wsHttpBinding` como enlace, y <xref:System.ServiceModel.Description.IMetadataExchange> como contrato:</span><span class="sxs-lookup"><span data-stu-id="0a968-111">Add a metadata endpoint specifying mex as the address, `wsHttpBinding` as the binding, and <xref:System.ServiceModel.Description.IMetadataExchange> as the contract:</span></span>  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4. <span data-ttu-id="0a968-112">Para comprobar que el punto de conexión de intercambio de metadatos funciona correctamente, agregue una etiqueta de punto final en el archivo de configuración del cliente:</span><span class="sxs-lookup"><span data-stu-id="0a968-112">To verify the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5. <span data-ttu-id="0a968-113">En el método Main () del cliente, cree una nueva instancia <xref:System.ServiceModel.Description.MetadataExchangeClient>, establezca su propiedad <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> en `true`, llame <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> y, a continuación, recorra en iteración la colección de metadatos devuelta:</span><span class="sxs-lookup"><span data-stu-id="0a968-113">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set its <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```csharp
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a><span data-ttu-id="0a968-114">Configurar por código</span><span class="sxs-lookup"><span data-stu-id="0a968-114">Configuring by code</span></span>  
  
1. <span data-ttu-id="0a968-115">Cree una instancia de enlace <xref:System.ServiceModel.WSHttpBinding>:</span><span class="sxs-lookup"><span data-stu-id="0a968-115">Create a <xref:System.ServiceModel.WSHttpBinding> binding instance:</span></span>  
  
    ```csharp  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2. <span data-ttu-id="0a968-116">Cree una instancia <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="0a968-116">Create a <xref:System.ServiceModel.ServiceHost> instance:</span></span>  
  
    ```csharp  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3. <span data-ttu-id="0a968-117">Agregue un extremo de servicio y agregue una instancia <xref:System.ServiceModel.Description.ServiceMetadataBehavior>:</span><span class="sxs-lookup"><span data-stu-id="0a968-117">Add a service endpoint and add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance:</span></span>  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4. <span data-ttu-id="0a968-118">Agregue un punto de conexión de intercambio de metadatos, especificando <xref:System.ServiceModel.WSHttpBinding> creado anteriormente:</span><span class="sxs-lookup"><span data-stu-id="0a968-118">Add a metadata exchange endpoint, specifying the <xref:System.ServiceModel.WSHttpBinding> created earlier:</span></span>  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5. <span data-ttu-id="0a968-119">Para comprobar que el extremo de intercambio de metadatos está funcionando correctamente, agregue una etiqueta de extremo en el archivo de configuración del cliente:</span><span class="sxs-lookup"><span data-stu-id="0a968-119">To verify that the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6. <span data-ttu-id="0a968-120">En el método Main () del cliente, cree una nueva instancia <xref:System.ServiceModel.Description.MetadataExchangeClient>, establezca la propiedad <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> en `true`, llame <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> y, a continuación, recorra en iteración la colección de metadatos devuelta:</span><span class="sxs-lookup"><span data-stu-id="0a968-120">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```csharp  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0a968-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a968-121">See also</span></span>

- [<span data-ttu-id="0a968-122">Comportamiento de publicación de metadatos</span><span class="sxs-lookup"><span data-stu-id="0a968-122">Metadata Publishing Behavior</span></span>](../samples/metadata-publishing-behavior.md)
- [<span data-ttu-id="0a968-123">Recuperación de metadatos</span><span class="sxs-lookup"><span data-stu-id="0a968-123">Retrieve Metadata</span></span>](../samples/retrieve-metadata.md)
- [<span data-ttu-id="0a968-124">Metadata</span><span class="sxs-lookup"><span data-stu-id="0a968-124">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="0a968-125">Publicación de metadatos</span><span class="sxs-lookup"><span data-stu-id="0a968-125">Publishing Metadata</span></span>](../feature-details/publishing-metadata.md)
- [<span data-ttu-id="0a968-126">Publicación de puntos de conexión de metadatos</span><span class="sxs-lookup"><span data-stu-id="0a968-126">Publishing Metadata Endpoints</span></span>](../publishing-metadata-endpoints.md)
