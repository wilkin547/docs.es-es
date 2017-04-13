---
title: "&lt;commonParameters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;commonParameters&gt;
Representa una colección de parámetros que se utilizan globalmente en varios servicios.  Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.  
  
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
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|Agrega un par de nombre y valor de parámetros comunes utilizados por los servicios para la colección.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<workflowRuntime\>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|Especifica los valores de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar los servicios [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] basados en flujo de trabajo.|  
  
## Comentarios  
 El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.  
  
> [!NOTE]
>  El servicio de seguimiento de SQL no utiliza de forma consistente el valor `ConnectionString` si se especifica en la sección `<commonParameters>`.  Es posible que se produzca un error en alguna de sus operaciones, como al recuperar la propiedad `StateMachineWorkflowInstance.StateHistory`.  Para solucionar este problema, especifique el atributo `ConnectionString` en la sección de configuración del proveedor de seguimiento, tal y como se indica en el ejemplo siguiente.  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
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
  
 El siguiente código de ejemplo muestra cómo cambiar los parámetros comunes mediante programación.  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
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
 [\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)