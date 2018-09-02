---
title: '&lt;workflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 849b09936f303c21fe55a6a46d561590c6a4c808
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43455762"
---
# <a name="ltworkflowruntimegt"></a>&lt;workflowRuntime&gt;
Especifica la configuración de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar servicios de Windows Communication Foundation (WCF) basados en flujo de trabajo.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
\<workflowRuntime >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|cachedInstanceExpiration|Un valor <xref:System.TimeSpan> opcional que especifica la duración máxima que una instancia de flujo de trabajo puede quedarse en memoria en estado inactivo antes de descargarse o cancelarse de forma obligatoria. Si workflowruntime tiene `PersistenceService` que realiza unloadOnIdle, se omite este atributo.|  
|enablePerformanceCounters|Un valor booleano opcional que especifica si los contadores de rendimiento están habilitados. Los contadores de rendimiento proporcionan información sobre varias estadísticas relacionadas con el flujo de trabajo, pero producen una reducción del rendimiento al iniciar el motor en tiempo de ejecución del flujo de trabajo, y durante la ejecución de las instancias del flujo de trabajo. El valor predeterminado es `true`.|  
|name|Una cadena que contiene el nombre del motor en tiempo de ejecución del flujo de trabajo. El nombre se usa en resultado para distinguir este tiempo de ejecución de otros tiempo de ejecución que se pueden estar ejecutando en el sistema, por ejemplo, en contadores de rendimiento.<br /><br /> El valor predeterminado es una cadena vacía.|  
|validateOnCreate|Un valor booleano opcional que especifica si se producirá la validación de definición de flujo de trabajo cuando se abra WorkflowServiceHost.  Cuando este atributo se establece en `true`, se ejecuta la validación del flujo de trabajo cada vez que se llama a `WorkflowServiceHost.Open`. Si se encuentran errores de validación, se inicia un error <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.<br /><br /> Cuando esta propiedad se establece en `false`, no pasará ninguna validación de definición de flujo de trabajo.<br /><br /> El valor predeterminado de esta propiedad es `true`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|commonParameters|Una colección de parámetros comunes usada por los servicios. Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.|  
|servicios|Una  colección de servicios que se agregará al motor <xref:System.Workflow.Runtime.WorkflowRuntime>. Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado. Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores. Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<comportamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre el uso de un archivo de configuración para controlar el comportamiento de un <xref:System.Workflow.Runtime.WorkflowRuntime> objeto de una aplicación de host de Windows Workflow Foundation, vea [archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).  
  
## <a name="example"></a>Ejemplo  
  
```xml  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
