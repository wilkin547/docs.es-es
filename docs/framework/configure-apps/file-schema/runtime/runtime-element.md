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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74430458"
---
# <a name="runtime-element"></a>\<runtime> (Elemento)

Proporciona información usada por el Common Language Runtime para configurar aplicaciones.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;\<runtime>

## <a name="syntax"></a>Sintaxis

```xml
<runtime>
</runtime>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las secciones siguientes se describen los elementos secundarios y los elementos primarios.

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
|[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)|Especifica que el tiempo de ejecución debe usar el comportamiento de ordenación heredado al realizar comparaciones de cadenas.|
|[\<developmentMode>](developmentmode-element.md)|Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.|
|[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)|Especifica si el almacenamiento en caché de errores de enlace, que es el comportamiento predeterminado en la .NET Framework versión 2,0, está deshabilitado.|
|[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)|Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.|
|[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)|Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.|
|[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)|Determina si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|
|[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)|Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).|
|[\<etwEnable>](etwenable-element.md)|Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)|Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.|
|[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)|En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).|
|[\<gcConcurrent>](gcconcurrent-element.md)|Especifica si el Common Language Runtime ejecuta la recolección de elementos no utilizados simultáneamente.|
|[\<GCCpuGroup>](gccpugroup-element.md)|Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|
|[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)|Define la afinidad entre los montones de recolección de elementos no utilizados y los procesadores individuales.|
|[\<GCHeapCount>](gcheapcount-element.md)|Especifica el número de montones o subprocesos que se usarán para la recolección de elementos no utilizados de servidor.|
|[\<GCLOHThreshold>](gclohthreshold-element.md)|Especifica el tamaño del umbral que hace que el recolector de elementos no utilizados coloque objetos en el montón de objetos grandes.|
|[\<GCNoAffinitize>](gcnoaffinitize-element.md)|Especifica si establecer afinidad entre o no los subprocesos de recolección de elementos no utilizados de servidor con CPU.|
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
|[\<shadowCopyVerifyByTimeStamp>](shadowcopyverifybytimestamp-element.md)|Especifica si la copia sombra usa el comportamiento de inicio predeterminado introducido en el .NET Framework 4, o revierte al comportamiento de inicio de versiones anteriores de la .NET Framework.|
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

Los elementos secundarios de la [\<runtime>](runtime-element.md) sección de un archivo de configuración se usan en el Common Language Runtime para configurar el modo en que se ejecuta una aplicación. Por ejemplo, el [\<gcServer>](gcserver-element.md) elemento determina si el recolector de elementos no utilizados utiliza la recolección de elementos no utilizados de estación de trabajo o la recolección de elementos no utilizados de servidor, el [\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md) elemento determina si el Common Language Runtime calcula los códigos hash de la cadena en una aplicación o un dominio por aplicación, y el `AppContextSwitchOverrides` elemento permite que los usuarios de la biblioteca opten por la funcionalidad modificada proporcionada por una biblioteca.

[\<runtime>](runtime-element.md)El Common Language Runtime lee automáticamente los elementos de la sección al iniciar la aplicación. También puede definir el archivo de configuración para un dominio de aplicación no predeterminado proporcionando su nombre a la <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> propiedad; su configuración se lee automáticamente cuando se carga el dominio de aplicación. En raras ocasiones, si es necesario, debe leer directamente la configuración de la sección del [\<runtime>](runtime-element.md) archivo de configuración de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
