---
title: "&lt;add&gt; de &lt;commonParameters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;add&gt; de &lt;commonParameters&gt;
Especifica un par de nombre y valor de parámetros que se utilizan globalmente en varios servicios.  Normalmente este parámetro incluye la cadena de conexión a la base de datos que podría ser compartida por servicios duraderos.  
  
## Sintaxis  
  
```  
  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|El nombre del parámetro especificado para un servicio.|  
|value|El valor del parámetro especificado para un servicio.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<commonParameters\>](http://msdn.microsoft.com/es-es/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|Una colección de parámetros comunes usada por los servicios.  Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.|  
  
## Comentarios  
 El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.  
  
 Puede habilitar los servicios que confirman los lotes de trabajo en los almacenes de persistencia, como <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> y <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, para reintentar su transacción utilizando el parámetro `EnableRetries` como se muestra en el ejemplo siguiente:  
  
```  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 Observe que el parámetro `EnableRetries` se puede establecer en un nivel global \(como se muestra en la sección *CommonParameters* \) o para servicios individuales que admiten `EnableRetries` \(como se muestra en la sección *Servicios* \).  
  
 Para obtener más información sobre cómo usar un archivo de configuración para controlar el comportamiento de un objeto <xref:System.Workflow.Runtime.WorkflowRuntime> de una aplicación host de Windows Workflow Foundation, vea [Workflow Configuration Files](http://msdn.microsoft.com/es-es/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).  
  
## Ejemplo  
  
```  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>   
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>   
 <xref:System.Workflow.Runtime.WorkflowRuntime>   
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>   
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>   
 [Workflow Configuration Files](http://msdn.microsoft.com/es-es/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)   
 [\<commonParameters\>](http://msdn.microsoft.com/es-es/d0e1e6fc-985a-4713-b7da-194e30dfab4c)