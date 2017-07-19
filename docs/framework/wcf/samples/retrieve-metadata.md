---
title: "Recuperaci&#243;n de metadatos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8a6ef8c-a195-495a-a15e-7d92bdf0b28c
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# Recuperaci&#243;n de metadatos
Este ejemplo muestra cómo implementar un cliente que dinámicamente recupere los metadatos de un servicio para elegir un extremo con el que comunicarse.  Este ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md).  El servicio se ha modificado para exponer dos extremos, uno en la dirección base utilizando el enlace`basicHttpBinding` y otro extremo seguro en {*baseaddress*}\/ utilizando el enlace `wsHttpBinding`.  En lugar de configurar el cliente con el extremo direcciones y enlaces, el cliente recupera dinámicamente los metadatos para el servicio utilizando la clase <xref:System.ServiceModel.Description.MetadataExchangeClient> y, a continuación, importa los metadatos como <xref:System.ServiceModel.Description.ServiceEndpointCollection> utilizando la clase <xref:System.ServiceModel.Description.WsdlImporter>.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 La aplicación de cliente usa el <xref:System.ServiceModel.Description.ServiceEndpointCollection> importado para crear clientes para comunicarse con el servicio.  La aplicación cliente procesa una iteración a través de cada extremo recuperado y se comunica con cada extremo que implementa el contrato `ICalculator`.  La dirección y el enlace adecuado se proporcionan con el extremo recuperado, para que el cliente se configure para comunicar con cada extremo, como se muestra en el código muestra siguiente.  
  
```  
// Create a MetadataExchangeClient for retrieving metadata.  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexAddress);  
  
// Retrieve the metadata for all endpoints using metadata exchange protocol (mex).  
MetadataSet metadataSet = mexClient.GetMetadata();  
  
//Convert the metadata into endpoints.  
WsdlImporter importer = new WsdlImporter(metadataSet);  
ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
  
CalculatorClient client = null;  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
// Communicate with each endpoint that supports the ICalculator contract.  
foreach (ServiceEndpoint ep in endpoints)  
{  
    if (ep.Contract.Namespace.Equals(contract.Namespace) && ep.Contract.Name.Equals(contract.Name))  
    {  
        // Create a client using the endpoint address and binding.  
        client = new CalculatorClient(ep.Binding, new EndpointAddress(ep.Address.Uri));  
        Console.WriteLine("Communicate with endpoint: ");  
        Console.WriteLine("   AddressPath={0}", ep.Address.Uri.PathAndQuery);  
        Console.WriteLine("   Binding={0}", ep.Binding.Name);  
        // Call operations.  
        DoCalculations(client);  
  
        //Closing the client gracefully closes the connection and cleans up resources.  
        client.Close();  
    }  
}  
  
```  
  
 La ventana de la consola del cliente muestra las operaciones enviadas a cada uno de los extremos, mostrando la ruta de acceso de la dirección y el nombre enlazando.  
  
### Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar el procedimiento de [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar la edición de C\#, C\+\+ o Visual Basic .NET de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\RetrieveMetadata`  
  
## Vea también