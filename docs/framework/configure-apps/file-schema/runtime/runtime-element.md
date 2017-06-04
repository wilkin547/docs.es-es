---
title: "Elemento &lt;runtime&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "&lt;runtime&gt; (elemento)"
  - "etiquetas contenedoras, &lt;runtime&gt; (elemento)"
  - "runtime (elemento)"
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
caps.latest.revision: 70
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 62
---
# Elemento &lt;runtime&gt;
Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.  
  
## Sintaxis  
  
```  
<runtime>  
</runtime>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<alwaysFlowImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)|Especifica que la identidad de Windows siempre fluye por los puntos asincrónicos, sin tener en cuenta cómo se realizó la suplantación.|  
|[\<appDomainManagerAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)|Especifica el ensamblado que proporciona el administrador del dominio de aplicación predeterminado en el proceso.|  
|[\<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)|Especifica el tipo que actúa como administrador del dominio de aplicación para el dominio de aplicación predeterminado.|  
|[\<appDomainResourceMonitoring\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)|Indica al runtime que recopile estadísticas de todos los dominios de aplicación del proceso mientras dure el proceso.|  
|[\<el assemblyBinding\>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|[\<bypassTrustedAppStrongNames\>](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)|Especifica si debe omitirse la comprobación de nombres seguros en los ensamblados de confianza.|  
|[\<CompatSortNLSVersion\>](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)|Especifica que el runtime debe utilizar el comportamiento de ordenación heredado al realizar comparaciones de cadenas.|  
|[\<developmentMode\>](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)|Especifica si el motor de ejecución busca los ensamblados en los directorios especificados en la variable de entorno DEVPATH.|  
|[\<disableCachingBindingFailures\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)|Especifica si se deshabilita el almacenamiento en caché errores de enlace, que es el comportamiento predeterminado en la versión 2.0 de .NET Framework.|  
|[\<disableCommitThreadStack\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)|Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.|  
|[\<disableFusionUpdatesFromADManager\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)|Especifica si el comportamiento predeterminado, que es permitir que el host en tiempo de ejecución invalide la configuración para un dominio de aplicación, está deshabilitado.|  
|[\<enforceFIPSPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)|Especifica si se va a exigir el cumplimiento del requisito de configuración de equipo por el que los algoritmos criptográficos deben ser compatibles con los estándares federales de procesamiento de información \(FIPS\).|  
|[\<etwEnable\>](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)|Especifica si permitir el seguimiento de eventos para Windows \(ETW\) para los eventos de Common Language Runtime.|  
|[\<forcePerformanceCounterUniqueSharedMemoryReads\>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)|Especifica si PerfCounter.dll usa el valor del Registro CategoryOptions en una aplicación de la versión 1.1 de .NET Framework para determinar si debe cargar los datos del contador de rendimiento de la memoria compartida específica de la categoría o de la memoria global.|  
|[\<gcAllowVeryLargeObjects\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)|En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes \(GB\).|  
|[\<gcConcurrent\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)|Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados de forma simultánea.|  
|[\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)|Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|  
|[\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)|Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados del servidor.|  
|[\<generatePublisherEvidence\>](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)|Especifica si el motor en tiempo de ejecución utiliza la directiva de editor de seguridad de acceso del código \(CAS\).|  
|[\<legacyCorruptedStateExceptionsPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)|Especifica si el motor en tiempo de ejecución permite al código administrado detectar infracciones de acceso y otras excepciones que indican un estado dañado.|  
|[\<legacyImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)|Especifica que la identidad de Windows no pasa por puntos asincrónicos, sin tener en cuenta la configuración de flujo para el contexto de ejecución del subproceso actual.|  
|[\<loadfromRemoteSources\>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)|Especifica si los ensamblados de orígenes remotos se cargan como de plena confianza.|  
|[\<NetFx40\_LegacySecurityPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)|Especifica si el motor en tiempo de ejecución utiliza la directiva de seguridad de acceso del código \(CAS\) heredada.|  
|[\<NetFx40\_PInvokeStackResilience\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)|Especifica si el runtime corrige automáticamente en tiempo de ejecución las declaraciones de invocación de plataforma incorrectas, a costa de transiciones más lentas entre código administrado y no administrado.|  
|[\<NetFx45\_CultureAwareComparerGetHashCode\_LongStrings\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Especifica si el tiempo de ejecución utiliza una cantidad de memoria fija para calcular los códigos hash para el método de <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> .|  
|[\<PreferComInsteadOfRemoting\>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)|Especifica si el motor en tiempo de ejecución usará interoperabilidad COM en lugar de comunicación remota entre límites de dominio de aplicación.|  
|[\<relativeBindForResources\>](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)|Optimiza el buscar ensamblados satélite.|  
|[\<shadowCopyVerifyByTimeStamp\>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)|Especifica si la instantánea usa el comportamiento de inicio predeterminado introducido en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], o revierte al comportamiento de inicio de las versiones anteriores de .NET Framework.|  
|[\<supportPortability\>](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)|Especifica que una aplicación puede hacer referencia al mismo ensamblado en dos implementaciones diferentes de .NET Framework, deshabilitando el comportamiento predeterminado que trata los ensamblados como equivalentes para los propósitos de portabilidad de aplicación.|  
|[\<system.runtime.caching\>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Proporciona información de configuración de la caché de objetos en memoria predeterminada.|  
|[\<Thread\_UseAllCpuGroups\>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)|Especifica si el runtime distribuye los subprocesos administrados en todos los grupos de CPU.|  
|[\<ThrowUnobservedTaskExceptions\>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)|Especifica si las excepciones no controladas de tarea deben finalizar un proceso en ejecución.|  
|[\<TimeSpan\_LegacyFormatMode\>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)|Especifica si el runtime usa formato heredado para valores <xref:System.TimeSpan>.|  
|[\<UseRandomizedStringHashAlgorithm\>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)|Especifica si el runtime calcula los códigos hash de cadenas por el dominio de aplicación.|  
|[\<UseSmallInternalThreadStacks\>](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)|Solicita que el runtime use tamaños de pila explícitos cuando crea ciertos subprocesos que usa internamente, en lugar del tamaño de pila predeterminado.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## Comentarios  
 En la versión 2.0 de .NET Framework, la identidad suplantada fluye por los puntos asincrónicos dentro de un dominio de aplicación.  En la versión 2.0 de .NET Framework, puede habilitar o deshabilitar el flujo de suplantación por los puntos asincrónicos configurando correctamente el elemento del motor en tiempo de ejecución en el archivo machine.config o en el archivo de configuración de la aplicación.  Para ASP.NET, el flujo de la suplantación se puede configurar en el archivo aspnet.config se encuentra en el directorio \<\>de Windows Folder\\Microsoft.NET\\Framework\\vx.x.xxxx.  
  
 De manera predeterminada, ASP.NET deshabilita el flujo de suplantación en el archivo aspnet.config mediante los valores de configuración siguientes:  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe utilizar explícitamente los valores de configuración siguientes:  
  
```  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
 Para obtener más información, vea [\<legacyImpersonationPolicy\> \(Elemento\)](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) y [\<alwaysFlowImpersonationPolicy\> \(Elemento\)](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo redirigir una versión de ensamblado a otra versión.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
             <bindingRedirect oldVersion="1.0.0.0"  
                              newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Redirigir versiones de ensamblado](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)   
 [How to: Disable Concurrent Garbage Collection](http://msdn.microsoft.com/es-es/ba2c6c67-5778-497c-9fac-5f793b5500c7)