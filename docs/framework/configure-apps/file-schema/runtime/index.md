---
title: Esquema de la configuración de Common Language Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- schema runtime settings
- configuration schema [.NET Framework], runtime settings
- runtime settings schema
ms.assetid: f04816ab-110d-4e28-9283-845d6d9a4a68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0df1f3bcf8941b5fe0a8fd19dfc7423e669a766
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465621"
---
# <a name="runtime-settings-schema"></a>Esquema de la configuración de Common Language Runtime
Common Language Runtime usa la configuración del motor en tiempo de ejecución para configurar las aplicaciones destinadas a .NET Framework.  

## <a name="the-runtime-section-and-its-parent-and-child-elements"></a>El \<en tiempo de ejecución > sección y sus elementos primarios y secundarios
  
[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
&nbsp;&nbsp;[\<en tiempo de ejecución >](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<alwaysFlowImpersonationPolicy >](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<AppContextSwitchOverrides >](../../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainResourceMonitoring >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<assemblyBinding >](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<dependentAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<assemblyIdentity >](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblyidentity-element-for-runtime.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<bindingRedirect >](../../../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<codeBase>](../../../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<probing >](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<publisherPolicy >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<qualifyAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<bypassTrustedAppStrongNames >](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<CompatSortNLSVersion >](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<developmentMode >](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableCachingBindingFailures >](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableCommitThreadStack>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableFusionUpdatesFromADManager >](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<EnableAmPmParseAdjustment >](../../../../../docs/framework/configure-apps/file-schema/runtime/enableampmparseadjustment-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<enforceFIPSPolicy >](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<etwEnable >](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<forcePerformanceCounterUniqueSharedMemoryReads>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcAllowVeryLargeObjects >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcConcurrent >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<generatePublisherEvidence >](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<legacyCorruptedStateExceptionsPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<legacyImpersonationPolicy >](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<loadfromRemoteSources>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[<NetFx40_LegacySecurityPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[<NetFx40_PInvokeStackResilience>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<PreferComInsteadOfManagedRemoting>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<relativeBindForResources >](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<shadowCopyVerifyByTimeStamp>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<supportPortability >](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<System.Runtime.Caching >](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<memoryCache >](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<namedCaches >](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<Borrar >](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<Quitar >](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<ThrowUnobservedTaskExceptions >](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[<TimeSpan_LegacyFormatMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<useLegacyJit >](../../../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<UseRandomizedStringHashAlgorithm>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[\<UseSmallInternalThreadStacks >](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)  
&nbsp;&nbsp;\<\runtime >  
\<\Configuration >

## <a name="alphabetical-list-of-runtime-elements"></a>Lista alfabética de \<en tiempo de ejecución > elementos

|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|Agrega una caché con nombre a la colección `namedCaches` de una caché en memoria.|  
|[\<alwaysFlowImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)|Especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.|  
|[\<AppContextSwitchOverrides>](../../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)|Define uno o varios modificadores usados por la clase <xref:System.AppContext> para proporcionar un mecanismo para cancelar la participación con nueva funcionalidad.|  
|[\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)|Especifica el ensamblado que proporciona el administrador de dominios de aplicación para el dominio de aplicación predeterminado en el proceso.|  
|[\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)|Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.|  
|[\<appDomainResourceMonitoring>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)|Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.|  
|[\<assemblyBinding>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|[\<assemblyIdentity>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblyidentity-element-for-runtime.md)|Contiene información de identificación sobre un ensamblado.|  
|[\<bindingRedirect>](../../../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)|Redirige una versión de ensamblado a otra versión.|  
|[\<bypassTrustedAppStrongNames>](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)|Especifica si debe omitirse la comprobación de nombre seguro para los ensamblados de confianza.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|Borra la colección `namedCaches` de una caché en memoria.|  
|[\<codeBase>](../../../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)|Especifica dónde puede encontrar el runtime un ensamblado.|  
|[\<CompatSortNLSVersion>](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)|Especifica que el runtime debe usar el comportamiento de ordenación heredado al realizar comparaciones de cadenas.|  
|[\<dependentAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|Encapsula la directiva de enlace y la ubicación de cada ensamblado.|  
|[\<developmentMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)|Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.|  
|[\<disableCachingBindingFailures>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)|Especifica si el almacenamiento en caché de errores de enlaces, que es el comportamiento predeterminado en [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)], está deshabilitado.|  
|[\<disableCommitThreadStack>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)|Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.|  
|[\<disableFusionUpdatesFromADManager>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)|Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.|  
|[\<EnableAmPmParseAdjustment>](../../../../../docs/framework/configure-apps/file-schema/runtime/enableampmparseadjustment-element.md)|Determina si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|  
|[\<enforceFIPSPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)|Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).|  
|[\<etwEnable>](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)|Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.|  
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)|Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.|  
|[\<gcAllowVeryLargeObjects>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)|En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).|  
|[\<gcConcurrent>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)|Especifica si CLR ejecuta la recolección de elementos no utilizados simultáneamente.|  
|[\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)|Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|  
|[\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)|Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.|  
|[\<generatePublisherEvidence>](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)|Especifica si el runtime usa la directiva de edición de seguridad de acceso al código (CAS).|  
|[\<legacyCorruptedStateExceptionsPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)|Especifica si el runtime permite código administrado para detectar infracciones de acceso y otras excepciones de estado dañado.|  
|[\<legacyImpersonationPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)|Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.|  
|[\<loadfromRemoteSources>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)|Especifica si los ensamblados de orígenes remotos se cargan como ensamblados de plena confianza.|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache>.|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Contiene una colección de valores de configuración para la instancia de `namedCache` .|  
|[<NetFx40_LegacySecurityPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)|Especifica si el runtime usa la directiva de seguridad de acceso al código (CAS) heredada.|  
|[<NetFx40_PInvokeStackResilience>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)|Especifica si el runtime corrige automáticamente las declaraciones de invocación de plataforma incorrectas en tiempo de ejecución, a costa de transiciones más lentas entre código administrado y código no administrado.|  
|[<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Especifica si el runtime usa una cantidad de memoria fija para calcular los códigos hash para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>.|  
|[\<PreferComInsteadOfManagedRemoting>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)|Especifica que el runtime usará interoperabilidad COM en lugar de comunicación remota entre límites de dominio de aplicación.|  
|[\<probing>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|Especifica los subdirectorios en los que busca el runtime cuando se cargan los ensamblados.|  
|[\<publisherPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|Especifica si el tiempo de ejecución aplica la directiva de editor.|  
|[\<qualifyAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.|  
|[\<relativeBindForResources>](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)|Optimiza el sondeo de ensamblados satélite.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.|  
|[\<runtime>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)|Contiene información del enlace del ensamblado y del comportamiento de la recolección de elementos no utilizados.|  
|[\<shadowCopyTimeStampVerification>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)|Especifica si la creación de instantáneas usa el comportamiento de inicio predeterminado especificado en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o se revierte el comportamiento de inicio de versiones anteriores de .NET Framework.|  
|[\<supportPortability>](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)|Especifica que una aplicación puede hacer referencia al mismo ensamblado en dos implementaciones diferentes de .NET Framework, deshabilitando el comportamiento predeterminado que trata los ensamblados como equivalentes para los propósitos de portabilidad de aplicación.|  
|[\<system.runtime.caching>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Proporciona información de configuración de la caché de objetos en memoria predeterminada.|  
|[<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)|Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.|  
|[\<ThrowUnobservedTaskExceptions>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)|Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.|  
|[<TimeSpan_LegacyFormatMode>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)|Especifica si el runtime usa formato heredado para los valores <xref:System.TimeSpan>.|  
|[\<useLegacyJit>](../../../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)|Determina si Common Language Runtime usa el compilador JIT de 64 bits heredado para la compilación Just-In-Time.|  
|[\<UseRandomizedStringHashAlgorithm>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)|Especifica si el runtime calcula los códigos hash de las cadenas por cada dominio de aplicación.|  
|[\<UseSmallInternalThreadStacks>](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)|Solicita que el runtime use tamaños de pila explícitos al crear determinados subprocesos que utiliza internamente, en lugar del tamaño de pila predeterminado.|  
  
## <a name="see-also"></a>Vea también  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Cómo: deshabilitar la recolección de elementos no utilizados simultánea](https://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [Redirigir versiones de ensamblado](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
