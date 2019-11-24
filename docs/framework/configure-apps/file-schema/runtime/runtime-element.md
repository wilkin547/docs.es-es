---
title: <runtime> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime
helpviewer_keywords:
- <runtime> element
- runtime element
- container tags, <runtime> element
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
ms.openlocfilehash: 3825ae7c3e35193cb835981600fe1ef83097cd2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430458"
---
# <a name="runtime-element"></a>\<runtime> Element

Provides information used by the common language runtime to configure applications.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;\<runtime>

## <a name="syntax"></a>Sintaxis

```xml
<runtime>
</runtime>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

The following sections describe child elements and parent elements.

### <a name="attributes"></a>Atributos

Ninguno.

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md)|Especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.|
|[\<AppContextSwitchOverrides>](appcontextswitchoverrides-element.md)|Define uno o varios modificadores usados por la clase <xref:System.AppContext> para proporcionar un mecanismo para cancelar la participación con nueva funcionalidad.|
|[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)|Especifica el ensamblado que proporciona el administrador de dominios de aplicación para el dominio de aplicación predeterminado en el proceso.|
|[\<appDomainManagerType>](appdomainmanagertype-element.md)|Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.|
|[\<appDomainResourceMonitoring>](appdomainresourcemonitoring-element.md)|Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.|
|[\<assemblyBinding>](assemblybinding-element-for-runtime.md)|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|
|[\<bypassTrustedAppStrongNames>](bypasstrustedappstrongnames-element.md)|Especifica si debe omitirse la comprobación de nombre seguro para los ensamblados de confianza.|
|[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)|Specifies that the runtime should use legacy sorting behavior when performing string comparisons.|
|[\<developmentMode>](developmentmode-element.md)|Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.|
|[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)|Specifies whether the caching of binding failures, which is the default behavior in the .NET Framework version 2.0, is disabled.|
|[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)|Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.|
|[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)|Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.|
|[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)|Determina si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|
|[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)|Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).|
|[\<etwEnable>](etwenable-element.md)|Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)|Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.|
|[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)|En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).|
|[\<gcConcurrent>](gcconcurrent-element.md)|Specifies whether the common language runtime runs garbage collection concurrently.|
|[\<GCCpuGroup>](gccpugroup-element.md)|Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|
|[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)|Defines the affinity between garbage collection heaps and individual processors.|
|[\<GCHeapCount>](gcheapcount-element.md)|Specifies the number of heaps/threads to use for server garbage collection.|
|[\<GCLOHThreshold>](gclohthreshold-element.md)|Specifies the threshold size that causes the garbage collector to put objects on the large object heap.|
|[\<GCNoAffinitize>](gcnoaffinitize-element.md)|Specifies whether or not to affinitize server garbage collection threads with CPUs.|
|[\<gcServer>](gcserver-element.md)|Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.|
|[\<generatePublisherEvidence>](generatepublisherevidence-element.md)|Especifica si el runtime usa la directiva de edición de seguridad de acceso al código (CAS).|
|[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)|Especifica si el runtime permite código administrado para detectar infracciones de acceso y otras excepciones de estado dañado.|
|[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)|Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.|
|[\<loadfromRemoteSources>](loadfromremotesources-element.md)|Especifica si los ensamblados de orígenes remotos se cargan como ensamblados de plena confianza.|
|[\<NetFx40_LegacySecurityPolicy>](netfx40-legacysecuritypolicy-element.md)|Especifica si el runtime usa la directiva de seguridad de acceso al código (CAS) heredada.|
|[\<NetFx40_PInvokeStackResilience>](netfx40-pinvokestackresilience-element.md)|Especifica si el runtime corrige automáticamente las declaraciones de invocación de plataforma incorrectas en tiempo de ejecución, a costa de transiciones más lentas entre código administrado y código no administrado.|
|[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](netfx45-cultureawarecomparergethashcode-longstrings-element.md)|Especifica si el runtime usa una cantidad de memoria fija para calcular los códigos hash para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .|
|[\<PreferComInsteadOfRemoting>](prefercominsteadofmanagedremoting-element.md)|Especifica que el runtime usará interoperabilidad COM en lugar de comunicación remota entre límites de dominio de aplicación.|
|[\<relativeBindForResources>](relativebindforresources-element.md)|Optimiza el sondeo de ensamblados satélite.|
|[\<shadowCopyVerifyByTimeStamp>](shadowcopyverifybytimestamp-element.md)|Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.|
|[\<supportPortability>](supportportability-element.md)|Especifica que una aplicación puede hacer referencia al mismo ensamblado en dos implementaciones diferentes de .NET Framework, deshabilitando el comportamiento predeterminado que trata los ensamblados como equivalentes para los propósitos de portabilidad de aplicación.|
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Proporciona información de configuración de la caché de objetos en memoria predeterminada.|
|[\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md)|Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.|
|[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)|Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.|
|[\<TimeSpan_LegacyFormatMode>](timespan-legacyformatmode-element.md)|Especifica si el runtime usa formato heredado para los valores <xref:System.TimeSpan>.|
|[\<useLegacyJit>](uselegacyjit-element.md)|Determina si Common Language Runtime usa el compilador JIT de 64 bits heredado para la compilación Just-In-Time.|
|[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)|Especifica si el runtime calcula los códigos hash de las cadenas por cada dominio de aplicación.|
|[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)|Solicita que el runtime use tamaños de pila explícitos al crear determinados subprocesos que utiliza internamente, en lugar del tamaño de pila predeterminado.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|

## <a name="remarks"></a>Comentarios

The child elements in the [\<runtime>](runtime-element.md) section of a configuration file are used by the common language runtime to configure how an application executes. For example, the [\<gcServer>](gcserver-element.md) element determines whether the garbage collector uses workstation garbage collection or server garbage collection, the [\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md) element determines whether the common language runtime calculates hash codes for string on a per-application or a per-application domain basis, and the `AppContextSwitchOverrides` element allows library users to opt in or opt out of changed  functionality provided by a library.

The elements in the [\<runtime>](runtime-element.md) section are read automatically by the common language runtime at application startup. You can also define the configuration file for a non-default application domain by supplying its name to the <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> property; its settings are read automatically when the application domain is loaded. You should rarely, if ever, have a need to directly read the settings in the [\<runtime>](runtime-element.md) section in your application's configuration file.

## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
