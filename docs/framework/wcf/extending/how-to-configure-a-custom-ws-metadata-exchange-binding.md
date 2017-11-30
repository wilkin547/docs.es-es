---
title: "Cómo: Configurar un enlace de WS-Metadata Exchange Binding personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4202c0471c681257fa1ab1153d363e59615e10c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a><span data-ttu-id="da8e2-102">Cómo: Configurar un enlace de WS-Metadata Exchange Binding personalizado</span><span class="sxs-lookup"><span data-stu-id="da8e2-102">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>
<span data-ttu-id="da8e2-103">En este tema se explica cómo configurar un enlace personalizado de intercambio de WS-Metadata.</span><span class="sxs-lookup"><span data-stu-id="da8e2-103">This topic will explain how to configure a custom WS-Metadata exchange binding.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="da8e2-104"> incluye cuatro enlaces de metadatos definidos por el sistema, pero puede publicar metadatos usando cualquier enlace que desee.</span><span class="sxs-lookup"><span data-stu-id="da8e2-104"> includes four system-defined metadata bindings, but you can publish metadata using any binding you want.</span></span> <span data-ttu-id="da8e2-105">En este tema, se mostrará cómo publicar metadatos mediante `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="da8e2-105">This topic will show you how to publish metadata using the `wsHttpBinding`.</span></span> <span data-ttu-id="da8e2-106">Este enlace le da la opción de exponer los metadatos de una manera segura.</span><span class="sxs-lookup"><span data-stu-id="da8e2-106">This binding gives you the option of exposing metadata in a secure way.</span></span> <span data-ttu-id="da8e2-107">El código de este artículo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="da8e2-107">The code in this article is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
### <a name="using-a-configuration-file"></a><span data-ttu-id="da8e2-108">El uso de un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="da8e2-108">Using a configuration file</span></span>  
  
1.  <span data-ttu-id="da8e2-109">En el archivo de configuración del servicio, agregue un comportamiento del servicio que contenga la etiqueta `serviceMetadata`:</span><span class="sxs-lookup"><span data-stu-id="da8e2-109">In the service's configuration file, add a service behavior that contains the `serviceMetadata` tag:</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2.  <span data-ttu-id="da8e2-110">Agregue un atributo `behaviorConfiguration` a la etiqueta del servicio que hace referencia a este nuevo comportamiento:</span><span class="sxs-lookup"><span data-stu-id="da8e2-110">Add a `behaviorConfiguration` attribute to the service tag that references this new behavior:</span></span>  
  
    ```xml  
    <service        name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">   
    ```  
  
3.  <span data-ttu-id="da8e2-111">Agregue un extremo de metadatos que especifique mex como dirección, `wsHttpBinding` como enlace, y <xref:System.ServiceModel.Description.IMetadataExchange> como contrato:</span><span class="sxs-lookup"><span data-stu-id="da8e2-111">Add a metadata endpoint specifying mex as the address, `wsHttpBinding` as the binding, and <xref:System.ServiceModel.Description.IMetadataExchange> as the contract:</span></span>  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4.  <span data-ttu-id="da8e2-112">Para comprobar que el extremo de intercambio de metadatos está funcionando correctamente, agregue una etiqueta de extremo en el archivo de configuración del cliente:</span><span class="sxs-lookup"><span data-stu-id="da8e2-112">To verify the metadata exchange endpoint is working correctly add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5.  <span data-ttu-id="da8e2-113">En el método Main () del cliente, cree una nueva instancia <xref:System.ServiceModel.Description.MetadataExchangeClient>, establezca su propiedad <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> en `true`, llame <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> y, a continuación, recorra en iteración la colección de metadatos devuelta:</span><span class="sxs-lookup"><span data-stu-id="da8e2-113">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set its <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a><span data-ttu-id="da8e2-114">Configurar por código</span><span class="sxs-lookup"><span data-stu-id="da8e2-114">Configuring by code</span></span>  
  
1.  <span data-ttu-id="da8e2-115">Crear una <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> instancia de enlace:</span><span class="sxs-lookup"><span data-stu-id="da8e2-115">Create a <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> binding instance:</span></span>  
  
    ```  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2.  <span data-ttu-id="da8e2-116">Cree una instancia <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="da8e2-116">Create a <xref:System.ServiceModel.ServiceHost> instance:</span></span>  
  
    ```  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3.  <span data-ttu-id="da8e2-117">Agregue un extremo de servicio y agregue una instancia <xref:System.ServiceModel.Description.ServiceMetadataBehavior>:</span><span class="sxs-lookup"><span data-stu-id="da8e2-117">Add a service endpoint and add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance:</span></span>  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4.  <span data-ttu-id="da8e2-118">Agregar un extremo de intercambio de metadatos, especificando el <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> creado anteriormente:</span><span class="sxs-lookup"><span data-stu-id="da8e2-118">Add a metadata exchange endpoint, specifying the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> created earlier:</span></span>  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5.  <span data-ttu-id="da8e2-119">Para comprobar que el punto de conexión de intercambio de metadatos está funcionando correctamente, agregue una etiqueta de punto de conexión en el archivo de configuración del cliente:</span><span class="sxs-lookup"><span data-stu-id="da8e2-119">To verify that the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6.  <span data-ttu-id="da8e2-120">En el método Main () del cliente, cree una nueva instancia <xref:System.ServiceModel.Description.MetadataExchangeClient>, establezca la propiedad <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> en `true`, llame <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> y, a continuación, recorra en iteración la colección de metadatos devuelta:</span><span class="sxs-lookup"><span data-stu-id="da8e2-120">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="da8e2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="da8e2-121">See Also</span></span>  
 [<span data-ttu-id="da8e2-122">Metadatos que publican el comportamiento</span><span class="sxs-lookup"><span data-stu-id="da8e2-122">Metadata Publishing Behavior</span></span>](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)  
 [<span data-ttu-id="da8e2-123">Recuperar metadatos</span><span class="sxs-lookup"><span data-stu-id="da8e2-123">Retrieve Metadata</span></span>](../../../../docs/framework/wcf/samples/retrieve-metadata.md)  
 [<span data-ttu-id="da8e2-124">Metadatos</span><span class="sxs-lookup"><span data-stu-id="da8e2-124">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="da8e2-125">Publicación de metadatos</span><span class="sxs-lookup"><span data-stu-id="da8e2-125">Publishing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)  
 [<span data-ttu-id="da8e2-126">Publicación de puntos de conexión de metadatos</span><span class="sxs-lookup"><span data-stu-id="da8e2-126">Publishing Metadata Endpoints</span></span>](../../../../docs/framework/wcf/publishing-metadata-endpoints.md)
