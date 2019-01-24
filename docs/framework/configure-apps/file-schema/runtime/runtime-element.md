---
title: '&lt;en tiempo de ejecución&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime
helpviewer_keywords:
- <runtime> element
- runtime element
- container tags, <runtime> element
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 10cc81bee24fb757e4d826eb42d4ccf2324e6dab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659532"
---
# <a name="ltruntimegt-element"></a>&lt;en tiempo de ejecución&gt; elemento
Proporciona información de common language runtime usada para configurar las aplicaciones.  
  
 \<configuration>  
\<runtime>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<runtime>  
</runtime>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 Las siguientes secciones describen los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<alwaysFlowImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)|Especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.|  
|[\<AppContextSwitchOverrides>](../../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)|Define uno o varios modificadores usados por la clase <xref:System.AppContext> para proporcionar un mecanismo para cancelar la participación con nueva funcionalidad.|  
|[\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)|Especifica el ensamblado que proporciona el administrador de dominios de aplicación para el dominio de aplicación predeterminado en el proceso.|  
|[\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)|Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.|  
|[\<appDomainResourceMonitoring>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)|Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.|  
|[\<assemblyBinding>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|[\<bypassTrustedAppStrongNames>](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)|Especifica si debe omitirse la comprobación de nombre seguro para los ensamblados de confianza.|  
|[\<CompatSortNLSVersion>](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)|Especifica que el tiempo de ejecución debe usar el comportamiento de ordenación heredado al realizar comparaciones de cadenas.|  
|[\<developmentMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)|Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.|  
|[\<disableCachingBindingFailures>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)|Especifica si el almacenamiento en caché de errores de enlace, que es el comportamiento predeterminado en la versión 2.0 de .NET Framework, está deshabilitado.|  
|[\<disableCommitThreadStack>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)|Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.|  
|[\<disableFusionUpdatesFromADManager>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)|Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.|  
|[\<EnableAmPmParseAdjustment>](../../../../../docs/framework/configure-apps/file-schema/runtime/enableampmparseadjustment-element.md)|Determina si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|  
|[\<enforceFIPSPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)|Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).|  
|[\<etwEnable>](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)|Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.|  
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)|Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.|  
|[\<gcAllowVeryLargeObjects>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)|En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).|  
|[\<gcConcurrent>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)|Especifica si common language runtime ejecuta la recolección de elementos no utilizados simultáneamente.|  
|[\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)|Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|  
|[\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)|Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.|  
|[\<generatePublisherEvidence>](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)|Especifica si el runtime usa la directiva de edición de seguridad de acceso al código (CAS).|  
|[\<legacyCorruptedStateExceptionsPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)|Especifica si el runtime permite código administrado para detectar infracciones de acceso y otras excepciones de estado dañado.|  
|[\<legacyImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)|Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.|  
|[\<loadfromRemoteSources>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)|Especifica si los ensamblados de orígenes remotos se cargan como ensamblados de plena confianza.|  
|[<NetFx40_LegacySecurityPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)|Especifica si el runtime usa la directiva de seguridad de acceso al código (CAS) heredada.|  
|[<NetFx40_PInvokeStackResilience>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)|Especifica si el runtime corrige automáticamente las declaraciones de invocación de plataforma incorrectas en tiempo de ejecución, a costa de transiciones más lentas entre código administrado y código no administrado.|  
|[<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Especifica si el runtime usa una cantidad de memoria fija para calcular los códigos hash para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .|  
|[\<PreferComInsteadOfRemoting>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)|Especifica que el runtime usará interoperabilidad COM en lugar de comunicación remota entre límites de dominio de aplicación.|  
|[\<relativeBindForResources>](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)|Optimiza el sondeo de ensamblados satélite.|  
|[\<shadowCopyVerifyByTimeStamp>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)|Especifica si la creación de instantáneas usa el comportamiento de inicio predeterminado especificado en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o se revierte el comportamiento de inicio de versiones anteriores de .NET Framework.|  
|[\<supportPortability>](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)|Especifica que una aplicación puede hacer referencia al mismo ensamblado en dos implementaciones diferentes de .NET Framework, deshabilitando el comportamiento predeterminado que trata los ensamblados como equivalentes para los propósitos de portabilidad de aplicación.|  
|[\<system.runtime.caching>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Proporciona información de configuración de la caché de objetos en memoria predeterminada.|  
|[<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)|Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.|  
|[\<ThrowUnobservedTaskExceptions>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)|Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.|  
|[<TimeSpan_LegacyFormatMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/timespan-legacyformatmode-element.md)|Especifica si el runtime usa formato heredado para los valores <xref:System.TimeSpan>.|  
|[\<useLegacyJit>](../../../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)|Determina si Common Language Runtime usa el compilador JIT de 64 bits heredado para la compilación Just-In-Time.|  
|[\<UseRandomizedStringHashAlgorithm>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)|Especifica si el runtime calcula los códigos hash de las cadenas por cada dominio de aplicación.|  
|[\<UseSmallInternalThreadStacks>](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)|Solicita que el runtime use tamaños de pila explícitos al crear determinados subprocesos que utiliza internamente, en lugar del tamaño de pila predeterminado.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## <a name="remarks"></a>Comentarios  
 Los elementos secundarios en el [ \<en tiempo de ejecución >](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sección de un archivo de configuración se usan por common language runtime para configurar cómo se ejecuta una aplicación. Por ejemplo, el [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento determina si el recolector de elementos no utilizados utiliza la recolección de elementos no utilizados de estación de trabajo o la recolección de elementos no utilizados de servidor, el [ \< UseRandomizedStringHashAlgorithm >](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md) elemento determina si common language runtime calcula los códigos hash para cadenas por una aplicación o un dominio por aplicación y el `AppContextSwitchOverrides` elemento permite a los usuarios de la biblioteca para participar o no fuera de la funcionalidad proporcionada por una biblioteca que ha cambiado.  
  
 Los elementos de la [ \<en tiempo de ejecución >](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sección lee automáticamente common language runtime al iniciarse la aplicación. También puede definir el archivo de configuración para un dominio de aplicación no predeterminado proporcionando su nombre a la <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> propiedad; su configuración se lee de forma automática cuando se carga el dominio de aplicación. Debe rara vez, si alguna vez, tiene una necesidad de leer directamente la configuración en el [ \<en tiempo de ejecución >](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sección en el archivo de configuración de la aplicación.  
  
## <a name="see-also"></a>Vea también
- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
