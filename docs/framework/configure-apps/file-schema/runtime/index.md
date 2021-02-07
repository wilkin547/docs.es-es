---
description: 'Más información acerca de: esquema de configuración de tiempo de ejecución'
title: Esquema de la configuración de Common Language Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- schema runtime settings
- configuration schema [.NET Framework], runtime settings
- runtime settings schema
ms.assetid: f04816ab-110d-4e28-9283-845d6d9a4a68
ms.openlocfilehash: ee9c209866eb8c505130327d78a18482f5a282e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726135"
---
# <a name="run-time-settings-schema"></a>Esquema de la configuración del entorno en tiempo de ejecución

La Common Language Runtime usa la configuración de tiempo de ejecución para configurar las aplicaciones destinadas a la .NET Framework.

## <a name="the-runtime-section-and-its-parent-and-child-elements"></a>La \<runtime> sección y sus elementos primarios y secundarios

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<AppContextSwitchOverrides>](appcontextswitchoverrides-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainManagerType>](appdomainmanagertype-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<appDomainResourceMonitoring>](appdomainresourcemonitoring-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<assemblyBinding>](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<dependentAssembly>](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<assemblyIdentity>](assemblyidentity-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<bindingRedirect>](bindingredirect-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<codeBase>](codebase-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<publisherPolicy>](publisherpolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<probing>](probing-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<qualifyAssembly>](qualifyassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<supportPortability>](supportportability-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<bypassTrustedAppStrongNames>](bypasstrustedappstrongnames-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<developmentMode>](developmentmode-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<etwEnable>](etwenable-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcConcurrent>](gcconcurrent-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCCpuGroup>](gccpugroup-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCHeapCount>](gcheapcount-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCLOHThreshold>](gclohthreshold-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<GCNoAffinitize>](gcnoaffinitize-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<gcServer>](gcserver-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<generatePublisherEvidence>](generatepublisherevidence-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<loadfromRemoteSources>](loadfromremotesources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<NetFx40_LegacySecurityPolicy>](netfx40-legacysecuritypolicy-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<NetFx40_PInvokeStackResilience>](netfx40-pinvokestackresilience-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](netfx45-cultureawarecomparergethashcode-longstrings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<PreferComInsteadOfManagedRemoting>](prefercominsteadofmanagedremoting-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<relativeBindForResources>](relativebindforresources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<shadowCopyVerifyByTimeStamp>](shadowcopyverifybytimestamp-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<TimeSpan_LegacyFormatMode>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<useLegacyJit>](uselegacyjit-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)\
&nbsp;&nbsp;[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<memoryCache>](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<namedCaches>](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<add>](add-element-for-namedcaches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clear>](clear-element-for-namedcaches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<remove>](remove-element-for-namedcaches.md)

## <a name="alphabetical-list-of-runtime-elements"></a>Lista alfabética de \<runtime> elementos

|Elemento|Descripción|
|-------------|-----------------|
|[\<add>](add-element-for-namedcaches.md)|Agrega una caché con nombre a la colección `namedCaches` de una caché en memoria.|
|[\<alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md)|Especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.|
|[\<AppContextSwitchOverrides>](appcontextswitchoverrides-element.md)|Define uno o varios modificadores usados por la clase <xref:System.AppContext> para proporcionar un mecanismo para cancelar la participación con nueva funcionalidad.|
|[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)|Especifica el ensamblado que proporciona el administrador de dominios de aplicación para el dominio de aplicación predeterminado en el proceso.|
|[\<appDomainManagerType>](appdomainmanagertype-element.md)|Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.|
|[\<appDomainResourceMonitoring>](appdomainresourcemonitoring-element.md)|Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.|
|[\<assemblyBinding>](assemblybinding-element-for-runtime.md)|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|
|[\<assemblyIdentity>](assemblyidentity-element-for-runtime.md)|Contiene información de identificación sobre un ensamblado.|
|[\<bindingRedirect>](bindingredirect-element.md)|Redirige una versión de ensamblado a otra versión.|
|[\<bypassTrustedAppStrongNames>](bypasstrustedappstrongnames-element.md)|Especifica si debe omitirse la comprobación de nombre seguro para los ensamblados de confianza.|
|[\<clear>](clear-element-for-namedcaches.md)|Borra la colección `namedCaches` de una caché en memoria.|
|[\<codeBase>](codebase-element.md)|Especifica dónde puede encontrar el runtime un ensamblado.|
|[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)|Especifica que el runtime debe usar el comportamiento de ordenación heredado al realizar comparaciones de cadenas.|
|[\<dependentAssembly>](dependentassembly-element.md)|Encapsula la directiva de enlace y la ubicación de cada ensamblado.|
|[\<developmentMode>](developmentmode-element.md)|Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.|
|[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)|Especifica si el almacenamiento en caché de errores de enlace, que es el comportamiento predeterminado en el .NET Framework 2,0, está deshabilitado.|
|[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)|Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.|
|[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)|Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.|
|[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)|Determina si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|
|[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)|Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).|
|[\<etwEnable>](etwenable-element.md)|Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)|Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.|
|[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)|En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).|
|[\<gcConcurrent>](gcconcurrent-element.md)|Especifica si CLR ejecuta la recolección de elementos no utilizados simultáneamente.|
|[\<GCCpuGroup>](gccpugroup-element.md)|Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|
|[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)|Define la afinidad entre los montones de GC y los procesadores individuales.|
|[\<GCHeapCount>](gcheapcount-element.md)|Especifica el número de montones o subprocesos que se usarán para la recolección de elementos no utilizados de servidor.  |
|[\<GCLOHThreshold>](gclohthreshold-element.md)|Especifica el tamaño del umbral que hace que los objetos se dirijan al montón de objetos grandes (montón).|
|[\<GCNoAffinitize>](gcnoaffinitize-element.md)|Especifica si establecer afinidad entre o no los subprocesos de GC del servidor con CPU.|
|[\<gcServer>](gcserver-element.md)|Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.|
|[\<generatePublisherEvidence>](generatepublisherevidence-element.md)|Especifica si el runtime usa la directiva de edición de seguridad de acceso al código (CAS).|
|[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)|Especifica si el runtime permite código administrado para detectar infracciones de acceso y otras excepciones de estado dañado.|
|[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)|Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.|
|[\<loadfromRemoteSources>](loadfromremotesources-element.md)|Especifica si los ensamblados de orígenes remotos se cargan como ensamblados de plena confianza.|
|[\<memoryCache>](memorycache-element-cache-settings.md)|Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .|
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Contiene una colección de valores de configuración para la instancia de `namedCache` .|
|[\<NetFx40_LegacySecurityPolicy>](netfx40-legacysecuritypolicy-element.md)|Especifica si el runtime usa la directiva de seguridad de acceso al código (CAS) heredada.|
|[\<NetFx40_PInvokeStackResilience>](netfx40-pinvokestackresilience-element.md)|Especifica si el runtime corrige automáticamente las declaraciones de invocación de plataforma incorrectas en tiempo de ejecución, a costa de transiciones más lentas entre código administrado y código no administrado.|
|[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Especifica si el runtime usa una cantidad de memoria fija para calcular los códigos hash para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .|
|[\<PreferComInsteadOfManagedRemoting>](prefercominsteadofmanagedremoting-element.md)|Especifica que el runtime usará interoperabilidad COM en lugar de comunicación remota entre límites de dominio de aplicación.|
|[\<probing>](probing-element.md)|Especifica los subdirectorios en los que busca el runtime cuando se cargan los ensamblados.|
|[\<publisherPolicy>](publisherpolicy-element.md)|Especifica si el tiempo de ejecución aplica la directiva de editor.|
|[\<qualifyAssembly>](qualifyassembly-element.md)|Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.|
|[\<relativeBindForResources>](relativebindforresources-element.md)|Optimiza el sondeo de ensamblados satélite.|
|[\<remove>](remove-element-for-namedcaches.md)|Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.|
|[\<runtime>](runtime-element.md)|Contiene información del enlace del ensamblado y del comportamiento de la recolección de elementos no utilizados.|
|[\<shadowCopyTimeStampVerification>](shadowcopyverifybytimestamp-element.md)|Especifica si la copia sombra usa el comportamiento de inicio predeterminado introducido en el .NET Framework 4, o revierte al comportamiento de inicio de versiones anteriores de la .NET Framework.|
|[\<supportPortability>](supportportability-element.md)|Especifica que una aplicación puede hacer referencia al mismo ensamblado en dos implementaciones diferentes de .NET Framework, deshabilitando el comportamiento predeterminado que trata los ensamblados como equivalentes para los propósitos de portabilidad de aplicación.|
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Proporciona información de configuración de la caché de objetos en memoria predeterminada.|
|[\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md)|Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.|
|[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)|Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.|
|[\<TimeSpan_LegacyFormatMode>](runtime-element.md)|Especifica si el runtime usa formato heredado para los valores <xref:System.TimeSpan>.|
|[\<useLegacyJit>](uselegacyjit-element.md)|Determina si Common Language Runtime usa el compilador JIT de 64 bits heredado para la compilación Just-In-Time.|
|[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)|Especifica si el runtime calcula los códigos hash de las cadenas por cada dominio de aplicación.|
|[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)|Solicita que el runtime use tamaños de pila explícitos al crear determinados subprocesos que utiliza internamente, en lugar del tamaño de pila predeterminado.|

## <a name="see-also"></a>Vea también

- [Esquema de los archivos de configuración](../index.md)
- [Para deshabilitar la recolección de elementos no utilizados simultánea](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Redirigir versiones de ensamblado](../../redirect-assembly-versions.md)
