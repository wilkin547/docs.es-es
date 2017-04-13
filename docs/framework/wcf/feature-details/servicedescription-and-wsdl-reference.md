---
title: "ServiceDescription y referencias WSDL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eedc025d-abd9-46b1-bf3b-61d2d5c95fd6
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# ServiceDescription y referencias WSDL
Este tema describe cómo [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] asigna los documentos del lenguaje de descripción de servicios Web \(WSDL\) a y desde las instancias <xref:System.ServiceModel.Description.ServiceDescription>.  
  
## Asignaciones de ServiceDescription a WSDL 1.1  
 Puede utilizar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para exportar los documentos WSDL desde una instancia <xref:System.ServiceModel.Description.ServiceDescription> de su servicio.  Los documentos WSDL se generan automáticamente para su servicio al publicar los extremos de metadatos.  
  
 Además, puede importar instancias <xref:System.ServiceModel.Description.ServiceEndpoint>, instancias <xref:System.ServiceModel.Description.ContractDescription>, e instancias <xref:System.ServiceModel.Channels.Binding> desde documentos WSDL mediante el tipo `WsdlImporter`.  
  
 Los documentos de WSDL, exportados mediante [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], importan cualquier definición de esquema XML utilizada a partir de documentos de esquema XML externos.  Se exporta un documento de esquema XML independiente para cada espacio de nombres de destino utilizado por los tipos de datos en el servicio.  Igualmente, se exporta un documento WSDL independiente para cada espacio de nombres de destino utilizado por los contratos de servicios.  
  
### ServiceDescription  
 Se asigna una instancia <xref:System.ServiceModel.Description.ServiceDescription> a un elemento `wsdl:service`.  Una instancia <xref:System.ServiceModel.Description.ServiceDescription> contiene una colección de instancias <xref:System.ServiceModel.Description.ServiceEndpoint> en la que cada una se asigna a elementos `wsdl:port` individuales.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`Name`|El valor `wsdl:service`\/@name para el servicio.|  
|`Namespace`|El espacio de nombres de destino para la definición `wsdl:service` del servicio.|  
|`Endpoints`|Las definiciones `wsdl:port` del servicio.|  
  
### ServiceEndpoint  
 Se asigna una instancia <xref:System.ServiceModel.Description.ServiceEndpoint> a un elemento `wsdl:port`.  Una instancia <xref:System.ServiceModel.Description.ServiceEndpoint> contiene una dirección, un enlace y un contrato.  
  
 Los comportamientos del extremo que implementan la interfaz <xref:System.ServiceModel.Description.IWsdlExportExtension> pueden modificar el elemento `wsdl:port` del extremo al que están adjuntos.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`Name`|El valor `wsdl:port`\/@name del extremo, y el valor `wsdl:binding`\/@name del enlace del extremo.|  
|`Address`|La dirección para la definición `wsdl:port` del extremo.<br /><br /> El transporte del extremo determina el formato de la dirección.  Por ejemplo, para transportes compatibles con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] podría ser una dirección de SOAP o una referencia de extremo.|  
|`Binding`|La definición `wsdl:binding` del extremo.<br /><br /> A diferencia de las definiciones `wsdl:binding`, los enlaces en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no están asociados con un contrato.|  
|`Contract`|La definición `wsdl:portType` del extremo.|  
|`Behaviors`|Los comportamientos del extremo que implementan la interfaz <xref:System.ServiceModel.Description.IWsdlExportExtension> pueden modificar `wsdl:port` del extremo.|  
  
### Enlaces  
 La instancia de enlace para una instancia `ServiceEndpoint` se asigna a una definición `wsdl:binding`.  A diferencia de las definiciones `wsdl:binding`, que deben estar asociadas a un definición `wsdl:portType` específica, los enlaces [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] son independientes de cualquier contrato.  
  
 Un enlace se compone de una colección de elementos de enlace.  Cada elemento describe algún aspecto de cómo el extremo se comunica con los clientes.  Además, un enlace tiene una <xref:System.ServiceModel.Channels.MessageVersion> que indica la <xref:System.ServiceModel.EnvelopeVersion> y la <xref:System.ServiceModel.Channels.AddressingVersion> del extremo.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`Name`|Se utiliza en el nombre predeterminado de un extremo, que es el nombre del enlace al que se anexa el nombre del contrato separado por un guión bajo.|  
|`Namespace`|`targetNamespace` para la definición `wsdl:binding`.<br /><br /> En importación, si una directiva está adjunta al puerto WSDL, el espacio de nombres del enlace importado se asigna a `targetNamespace` para la definición `wsdl:port`.|  
|`BindingElementCollection`, como lo devuelve el método `CreateBindingElements`\(\).|Varias extensiones específicas del dominio para la definición `wsdl:binding`, normalmente, las aserciones de directiva.|  
|`MessageVersion`|`EnvelopeVersion` y `AddressingVersion` para el extremo.<br /><br /> Cuando se especifica `MessageVersion.None`, el enlace de WSDL no contiene un enlace SOAP y el puerto WSDL no incluye contenido de WS\-Addressing.  Este valor se utiliza normalmente para extremos “XML sin formato” \(POX\).|  
  
#### BindingElements  
 Los elementos de enlace de un enlace de extremo se asignan a distintas extensiones WSDL en `wsdl:binding`, por ejemplo, las aserciones de directiva.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement> del enlace determina la dirección URI del transporte de un enlace SOAP.  
  
#### AddressingVersion  
 `AddressingVersion` en un enlace se asigna a la versión de direccionamiento usada en `wsd:port`.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite direcciones SOAP 1.1 y SOAP 1.2, y referencias de extremo de WS\-Addressing 08\/2004 y de WS\-Addressing 1.0.  
  
#### EnvelopeVersion  
 `EnvelopeVersion` en un enlace se asigna a la versión de SOAP usada en `wsdl:binding`.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite enlaces SOAP 1.1 y SOAP 1.2.  
  
### Contratos  
 La instancia <xref:System.ServiceModel.Description.ContractDescription> para una instancia `ServiceEndpoint` se asigna a `wsdl:portType`.  Una instancia `ContractDescription` describe todas las operaciones de un contrato determinado.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`Name`|El valor `wsdl:portType`\/@name del contrato.|  
|`Namespace`|El espacio de nombres de destino para la definición `wsdl:portType`.|  
|`SessionMode`|El valor `wsdl:portType`\/@ msc:usingSession para el contrato.  Este atributo es una extensión [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para WSDL 1.1.|  
|`Operations`|Las definiciones `wsdl:operation` para el contrato.|  
  
### Operaciones  
 Una instancia <xref:System.ServiceModel.Description.OperationDescription> se asigna a `wsdl:portType`\/`wsdl:operation`.  `OperationDescription` contiene una colección de instancias `MessageDescription` que describen los mensajes para la operación.  
  
 Dos comportamientos de la operación participan considerablemente en la asignación de `OperationDescription` a un documento WSDL: `DataContractSerializerOperationBehavior` y `XmlSerializerOperationBehavior`.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`Name`|El valor `wsdl:portType`\/`wsdl:operation`\/@name para la operación.|  
|`ProtectionLevel`|Aserciones de protección de la directiva de seguridad adjuntas a los mensajes `wsdl:binding/wsdl:operation` de esta operación.|  
|`IsInitiating`|El valor `wsdl:portType`\/`wsdl:operation`\/@msc:isInitiating para la operación.  Este atributo es una extensión [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para WSDL 1.1.|  
|`IsTerminating`|El valor `wsdl:portType`\/`wsdl:operation`\/@msc:isTerminating para la operación.  Este atributo es una extensión [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para WSDL 1.1.|  
|`Messages`|Los mensajes `wsdl:portType`\/`wsdl:operation`\/`wsdl:input` y `wsdl:portType`\/`wsdl:operation`\/`wsdl:output` para la operación.|  
|`Faults`|Las definiciones `wsdl:portType`\/`wsdl:operation`\/`wsdl:fault` para la operación.|  
|`Behaviors`|`DataContractSerializerOperationBehavior` y `XmlSerializerOperationBehavior` están relacionados con el enlace y los mensajes de la operación.|  
  
#### DataContractSerializerOperationBehavior  
 `DataContractSerializerOperationBehavior` de una operación es una implementación `IWsdlExportExtension` que exporta los mensajes y el enlace WSDL de esa operación.  Los tipos del esquema XML se exportan mediante `XsdDataContractExporter`.  `DataContractSerializerOperationBehavior` también determina el uso y el estilo, así como el exportador e importador del esquema que se utilizarán para esa operación.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`DataContractFormatAttribute`|La propiedad `Style` de este atributo se asigna al valor `wsdl:binding`\/`wsdl:operation`\/`soap:operation`\/@style de la operación.<br /><br /> `DataContractSerializerOperationBehavior` solo admite el uso literal de los tipos del esquema en WSDL.|  
  
#### XmlSerializerOperationBehavior  
 `XmlSerializerOperationBehavior` de una operación es una implementación `IWsdlExportExtension` que exporta los mensajes y el enlace WSDL de esa operación.  Los tipos del esquema XML se exportan mediante `XmlSchemaExporter`.  `XmlSerializerOperationBehavior` también determina el uso y el estilo, así como el exportador e importador del esquema que se utilizarán para esa operación.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`XmlSerializerFormatAttribute`|La propiedad `Style` de este atributo se asigna al valor `wsdl:binding`\/`wsdl:operation`\/`soap:operation`\/@style de la operación.<br /><br /> La propiedad `Use` de este atributo se asigna a los valores `wsdl:binding`\/`wsdl:operation`\/`soap:operation`\/\* @ para todos los mensajes de la operación.|  
  
### Mensajes  
 Se asigna una instancia `MessageDescription` a `wsdl:message`, al que hace referencia `wsdl:portType`\/`wsdl:operation`\/`wsdl:input`, o a un mensaje `wsdl:portType`\/`wsdl:operation`\/`wsdl:output` de una operación.  `MessageDescription` posee un cuerpo y encabezados.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`Action`|La acción de SOAP o de WS\-Addressing para el mensaje.<br /><br /> Tenga en cuenta que las operaciones que utilizan la cadena de acción "\*" no se representan en WSDL.|  
|`Direction`|`MessageDirection.Input` se asigna a `wsdl:input`.<br /><br /> `MessageDirection.Output` se asigna a `wsdl:output`.|  
|`ProtectionLevel`|Aserciones de protección de la directiva de seguridad adjuntas a las definiciones `wsdl:message` de este mensaje.|  
|`Body`|El cuerpo del mensaje.|  
|`Headers`|Los encabezados del mensaje.|  
|`ContractDescription.Name`, `OperationContract.Name`|Al exportar, se utilizan para derivar el valor `wsdl:message`\/@name.|  
  
#### Cuerpo del mensaje  
 Se asigna una instancia de `MessageBodyDescription` a las definiciones `wsdl:message`\/`wsdl:part` para el cuerpo de un mensaje.  El cuerpo del mensaje puede ser de estilo ajustado o sencillo.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`WrapperName`|Si el estilo no es RPC, se asigna `WrapperName` al nombre de elemento al que hace referencia `wsdl:message`\/`wsdl:part` con el valor @name establecido en "parámetros".|  
|`WrapperNamespace`|Si el estilo no es RPC, se asigna `WrapperNamespace` al espacio de nombres del elemento de `wsdl:message`\/`wsdl:part` con el valor @name establecido en "parámetros".|  
|`Parts`|Las partes del mensaje de este cuerpo del mensaje.|  
|`ReturnValue`|El elemento secundario del elemento contenedor, en caso de existir uno \(documente con estilo ajustado o RPC\), de lo contrario, el primer `wsdl:message`\/`wsdl:part` del mensaje.|  
  
#### Partes del mensaje  
 Se asigna una instancia `MessagePartDescription` a `wsdl:message`\/`wsdl:part` y al tipo o elemento de esquema XML a los que señala la parte del mensaje.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`Name`|El valor de `wsd:message`\/`wsdl:part`\/@name para la parte del mensaje y el nombre del elemento a los que señala la parte del mensaje.|  
|`Namespace`|Espacio de nombres del elemento al que señala la parte del mensaje.|  
|`Index`|Índice de `wsdl:message`\/`wsdl:part` para el mensaje.|  
|`ProtectionLevel`|Aserciones de protección de la directiva de seguridad adjuntas a la definición `wsdl:message` de esta parte del mensaje.  La directiva se parametriza para señalar la parte del mensaje específica.|  
|`MessageType`|El tipo de esquema XML del elemento al que señala la parte del mensaje.|  
  
#### Encabezados de mensajes  
 Una instancia `MessageHeaderDescription` es una parte de un mensaje que también se asigna a un enlace `soap:header` de la parte del mensaje.  
  
### Errores  
 Se asigna una instancia `FaultDescription` a una definición `wsdl:portType`\/`wsdl:operation`\/`wsdl:fault` y a su definición `wsdl:message` asociada.  Se agrega `wsdl:message` al mismo espacio de nombres de destino que su tipo de puerto WSDL asociado.  `wsdl:message` tiene una única parte del mensaje denominada "detalle" que señala al elemento de esquema XML que corresponde al valor de propiedad `DefaultType` para la instancia `FaultDescription`.  
  
|Propiedades|Asignación WSDL|  
|-----------------|---------------------|  
|`Name`|El valor `wsdl:portType`\/`wsdl:operation`\/`wsdl:fault`\/@name para el error.|  
|`Namespace`|El espacio de nombres del elemento de esquema XML al que señala la parte del mensaje de información acerca del error.|  
|`Action`|La acción de SOAP o de WS\-Addressing para el error.|  
|`ProtectionLevel`|Aserciones de protección de la directiva de seguridad adjuntas a la definición `wsdl:message` de este error.|  
|`DetailType`|El tipo de esquema XML del elemento al que señala la parte del mensaje de información.|  
|`Name, ContractDescription.Name, OperationDescription.Name,`|Se utiliza para derivar el valor `wsdl:message`\/@name para el mensaje de error.|  
  
## Vea también  
 <xref:System.ServiceModel.Description>