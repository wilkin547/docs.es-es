---
title: Elemento <startup>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: 5b15c504a01a0ab8e17b8ad8811d9ed183609322
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456262"
---
# <a name="startup-element"></a>\<Inicio > elemento

Especifica la información de inicio de common language runtime.

 \<Configuración > \<Inicio >

## <a name="syntax"></a>Sintaxis

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|Atributo opcional.<br /><br /> Especifica si se habilita la [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] directiva de activación en tiempo de ejecución o que se usará el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] directiva de activación.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>atributo useLegacyV2RuntimeActivationPolicy

|Valor|Descripción|
|-----------|-----------------|
|`true`|Habilitar [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] en tiempo de ejecución directiva de activación para el tiempo de ejecución elegido, que se usa para enlazar las técnicas de activación de tiempo de ejecución heredado (como el [CorBindToRuntimeEx (función)](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) al tiempo de ejecución elegida en el archivo de configuración en lugar de límites de ellos en CLR versión 2.0. Por lo tanto, si se elige la versión CLR 4 o posterior del archivo de configuración, los ensamblados de modo mixto creados con versiones anteriores de .NET Framework se cargan con la versión CLR elegida. Al establecer este valor impide que CLR versión 1.1 o CLR versión 2.0 no se cargue en el mismo proceso, deshabilitando la característica en paralelo en proceso.|
|`false`|Usar la directiva de activación predeterminada de .NET Framework 4 y versiones posteriores, que consiste en permitir en tiempo de ejecución heredado técnicas de activación para cargar la versión 1.1 o 2.0 de CLR en el proceso. Al establecer este valor impide que los ensamblados de modo mixto de carga en .NET Framework 4 o posterior, a menos que se compilaron con .NET Framework 4 o posterior. Este valor es el valor predeterminado.|

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime. Las aplicaciones compiladas con la versión 1.1 o posterior del runtime deben usar el  **\<supportedRuntime >** elemento.|
|[\<supportedRuntime>](supportedruntime-element.md)|Especifica qué versiones de Common Language Runtime admite la aplicación.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|

## <a name="remarks"></a>Comentarios

 El  **\<supportedRuntime >** se debe utilizar el elemento todas las aplicaciones compiladas con la versión 1.1 o posterior del tiempo de ejecución. Las aplicaciones compiladas para admitir sólo la versión 1.0 del tiempo de ejecución deben usar la  **\<requiredRuntime >** elemento.

 El código de inicio de una aplicación hospedada en Microsoft Internet Explorer omite el  **\<Inicio >** elemento y sus elementos secundarios.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>El atributo useLegacyV2RuntimeActivationPolicy

 Este atributo es útil si la aplicación usa rutas de acceso de activación heredada, como la [CorBindToRuntimeEx (función)](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que esas rutas de acceso para activar la versión 4 de CLR en lugar de una versión anterior, o si la aplicación compilada con .NET Framework 4, pero tiene una dependencia en un ensamblado de modo mixto generado con una versión anterior de .NET Framework. En esos escenarios, establezca el atributo en `true`.

> [!NOTE]
> Establecer el atributo como `true` que CLR versión 1.1 o CLR versión 2.0 no se cargue en el mismo proceso, deshabilitando la característica en paralelo en proceso (consulte [ejecución en paralelo para interoperabilidad COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).

## <a name="example"></a>Ejemplo

 El ejemplo siguiente muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Esquema de la configuración de inicio](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Ejecución en paralelo para interoperabilidad COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [Ejecución en paralelo en proceso](../../../deployment/in-process-side-by-side-execution.md)
