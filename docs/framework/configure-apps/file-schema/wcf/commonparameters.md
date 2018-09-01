---
title: '&lt;commonParameters&gt;'
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: 5e4c19c48709ffd81cb00e9820e6c3cdb297ec7e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43391725"
---
# <a name="ltcommonparametersgt"></a>&lt;commonParameters&gt;
Representa una colección de parámetros que se utilizan globalmente en varios servicios. Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
\<workflowRuntime >  
\<commonParameters >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|Agrega un par de nombre y valor de parámetros comunes utilizados por los servicios para la colección.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<workflowRuntime >](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|Especifica la configuración de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar servicios de Windows Communication Foundation (WCF) basados en flujo de trabajo.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.  
  
> [!NOTE]
>  El servicio de seguimiento de SQL no utiliza de forma consistente el valor `ConnectionString` si se especifica en la sección `<commonParameters>`. Es posible que se produzca un error en alguna de sus operaciones, como al recuperar la propiedad `StateMachineWorkflowInstance.StateHistory`. Para solucionar este problema, especifique el atributo `ConnectionString` en la sección de configuración del proveedor de seguimiento, tal y como se indica en el ejemplo siguiente.  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 Puede habilitar los servicios que confirman los lotes de trabajo en los almacenes de persistencia, como <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> y <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, para reintentar su transacción utilizando el parámetro `EnableRetries` como se muestra en el ejemplo siguiente:  
  
```xml  
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
  
 Tenga en cuenta que el `EnableRetries` parámetro puede establecerse en un nivel global (como se muestra en el *CommonParameters* sección) o para servicios individuales que admiten `EnableRetries` (como se muestra en el *servicios*sección).  
  
 El siguiente código de ejemplo muestra cómo cambiar los parámetros comunes mediante programación.  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 Para obtener más información sobre el uso de un archivo de configuración para controlar el comportamiento de un <xref:System.Workflow.Runtime.WorkflowRuntime> objeto de una aplicación de host de Windows Workflow Foundation, vea [archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
