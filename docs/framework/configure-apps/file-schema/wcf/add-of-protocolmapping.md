---
title: "&lt;add&gt; de &lt;protocolMapping&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;add&gt; de &lt;protocolMapping&gt;
Representa una asignación de protocolo predeterminado entre un esquema de protocolos de transporte \(ej., http, net.tcp, net.pipe, etc.\) y un enlace [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  Al crear extremos predeterminados en tiempo de ejecución, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] observa las asignaciones configuradas y decide qué enlace usar para una dirección base determinada.  
  
## Sintaxis  
  
```vb  
  
<protocolMapping>  
    <add binding="String”  
         bindingConfiguration="String”  
         scheme="http/net.msmq/net.pipe/net.tcp"/>  
</protocolMapping>  
  
```  
  
```csharp  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|enlace|Cadena que especifica el tipo de enlace que se va a usar para un extremo durante la creación del extremo predeterminado.|  
|bindingConfiguration|Cadena que especifica el nombre de la sección de configuración de enlace a la que se va a hacer referencia.|  
|scheme|Esquema de protocolos de transporte que se va a utilizar para el extremo predeterminado.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<protocolMapping\>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Representa una sección de configuración para definir las asignaciones de protocolos predeterminados entre los esquemas de protocolos de transporte \(ej., http, net.tcp, net.pipe, etc.\) y enlaces [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].|  
  
## Ejemplo  
 En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config.  Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config.  O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.  
  
```  
  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
  
```  
  
## Vea también  
 [System.ServiceModel.Configuration.ProtocolMappingSection](assetId:///System.ServiceModel.Configuration.ProtocolMappingSection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.ServiceModel.Configuration.ProtocolMappingElement](assetId:///System.ServiceModel.Configuration.ProtocolMappingElement?qualifyHint=False&amp;autoUpgrade=True)