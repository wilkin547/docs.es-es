---
title: "C&#243;mo: Utilizar Svcutil.exe para descargar los documentos de metadatos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# C&#243;mo: Utilizar Svcutil.exe para descargar los documentos de metadatos
Puede utilizar Svcutil.exe para descargar metadatos de los servicios en ejecución y para guardar los metadatos en archivos locales.Para esquemas de URL de HTTP y HTTPS, Svcutil.exe intenta recuperar metadatos mediante WS\-MetadataExchange y la [detección de los servicios web XML](http://go.microsoft.com/fwlink/?LinkId=94950).Para todos los otros esquemas de URL, Svcutil.exe utiliza sólo WS\-MetadataExchange.  
  
 De forma predeterminada, Svcutil.exe utiliza los enlaces definidos en la clase <xref:System.ServiceModel.Description.MetadataExchangeBindings>.Para configurar el enlace utilizado para WS\-MetadataExchange, debe definir un extremo de cliente en el archivo de configuración para Svcutil.exe \(svcutil.exe.config\) que utiliza el contrato `IMetadataExchange` y que tiene el mismo nombre que el esquema del Identificador uniforme de recursos \(URI\) de la dirección del extremo de metadatos.  
  
> [!CAUTION]
>  Al ejecutar Svcutil.exe para obtener metadatos para un servicio que expone dos contratos de servicio distintos, cada uno de los cuales contiene una operación con el mismo nombre, Svcutil.exe muestra el error “No se pueden obtener metadatos de ....” Por ejemplo, si dispone de un servicio que expone un contrato de servicio denominado ICarService que tiene una operación Get\(Car c\) y el mismo servicio expone un contrato de servicio denominado IBookService que tiene una operación Get\(Book b\).Para solucionar este problema, realice una de las operaciones siguientes:  
>   
>  -   Cambie el nombre de una de las operaciones.  
> -   Establezca el <xref:System.ServiceModel.OperationContractAttribute.Name%2A> en un nombre distinto.  
> -   Establezca el espacio de nombres de una de las operaciones en un espacio de nombres distinto mediante la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
### Para descargar metadatos mediante Svcutil.exe  
  
1.  Busque la herramienta Svcutil.exe en la ubicación siguiente:  
  
     C:\\Archivos de programa\\Microsoft SDKs\\Windows\\v1.0.\\bin  
  
2.  En el símbolo del sistema, inicie la herramienta mediante el formato siguiente.  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Debe especificar la opción `/t:metadata` para descargar los metadatos.De lo contrario, se generan el código de cliente y la configuración.  
  
3.  El argumento \<`url`\> especifica la dirección URL a un extremo de servicio que proporciona los metadatos o a un documento de metadatos hospedado en línea.El argumento \<`epr`\> especifica la ruta de acceso a un archivo XML que contiene un `EndpointAddress` de WS\-Addressing para un extremo de servicio que admite WS\-MetadataExchange.  
  
 Para obtener más opciones sobre cómo utilizar esta herramienta para la descarga de los metadatos, vea [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## Ejemplo  
 El comando siguiente descarga los documentos de metadatos de un servicio en ejecución.  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## Vea también  
 [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)