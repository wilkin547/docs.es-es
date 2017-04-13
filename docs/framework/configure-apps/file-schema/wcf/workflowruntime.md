---
title: "&lt;workflowRuntime&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;workflowRuntime&gt;
Especifica los valores de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar los servicios [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] basados en flujo de trabajo.  
  
## Sintaxis  
  
```  
  
<workflowRuntime cachedInstanceExpiration="TimeSpan"  
                                  enablePerformanceCounters="Boolean"  
                                  name="String"  
                                  validateOnCreate="Boolean">  
                 <commonParameters>  
                    <add name="String" value="String" />  
                 </commonParameters>  
                 <services>  
                    <add type="String"/>  
                 </services>  
</workflowRuntime>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|cachedInstanceExpiration|Un valor <xref:System.Timespan> opcional que especifica la duración máxima que una instancia de flujo de trabajo puede quedarse en memoria en estado inactivo antes de descargarse o cancelarse de forma obligatoria.  Si workflowruntime tiene `PersistenceService` que realiza unloadOnIdle, se omite este atributo.|  
|enablePerformanceCounters|Un valor booleano opcional que especifica si los contadores de rendimiento están habilitados.  Los contadores de rendimiento proporcionan información sobre varias estadísticas relacionadas con el flujo de trabajo, pero producen una reducción del rendimiento al iniciar el motor en tiempo de ejecución del flujo de trabajo, y durante la ejecución de las instancias del flujo de trabajo.  El valor predeterminado es `true`.|  
|name|Una cadena que contiene el nombre del motor en tiempo de ejecución del flujo de trabajo.  El nombre se usa en resultado para distinguir este tiempo de ejecución de otros tiempo de ejecución que se pueden estar ejecutando en el sistema, por ejemplo, en contadores de rendimiento.<br /><br /> El valor predeterminado es una cadena vacía.|  
|validateOnCreate|Un valor booleano opcional que especifica si se producirá la validación de definición de flujo de trabajo cuando se abra WorkflowServiceHost.  Cuando este atributo se establece en `true`, se ejecuta la validación del flujo de trabajo cada vez que se llama a `WorkflowServiceHost.Open`.  Si se encuentran errores de validación, se inicia un error <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.<br /><br /> Cuando esta propiedad se establece en `false`, no pasará ninguna validación de definición de flujo de trabajo.<br /><br /> El valor predeterminado de esta propiedad es `true`.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|commonParameters|Una colección de parámetros comunes usada por los servicios.  Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.|  
|servicios|Una  colección de servicios que se agregará al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.  Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.  Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.  Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## Comentarios  
 Para obtener más información sobre cómo usar un archivo de configuración para controlar el comportamiento de un objeto <xref:System.Workflow.Runtime.WorkflowRuntime> de una aplicación host de Windows Workflow Foundation, vea [Workflow Configuration Files](http://msdn.microsoft.com/es-es/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).  
  
## Ejemplo  
  
```  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <commonParameters>  
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
            <add name="EnableRetries" value="True" />  
         </commonParameters>  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>   
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>   
 <xref:System.Workflow.Runtime.WorkflowRuntime>   
 [Workflow Configuration Files](http://msdn.microsoft.com/es-es/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)