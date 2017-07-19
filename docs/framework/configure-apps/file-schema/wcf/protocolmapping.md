---
title: "&lt;protocolMapping&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;protocolMapping&gt;
Representa una sección de configuración para definir un conjunto de asignaciones de protocolos predeterminados entre esquemas de protocolos de transporte \(ej., http, net.tcp, net.pipe, etc.\) y enlaces WCF.  Al crear extremos predeterminados en tiempo de ejecución, [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] observa las asignaciones configuradas y decide qué enlace usar para una dirección base determinada.  
  
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
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<filtros\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Contiene una asignación de protocolo predeterminado entre un esquema de protocolos de transporte \(ej., http, net.tcp, net.pipe, etc.\) y un enlace WCF.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|system.ServiceModel|Elemento raíz de todos los elementos de configuración de WCF.|  
  
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