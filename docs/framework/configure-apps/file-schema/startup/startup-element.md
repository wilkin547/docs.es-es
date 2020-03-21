---
title: <startup> (elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153741"
---
# <a name="startup-element"></a>\<startup> elemento

Especifica la información de inicio de Common Language Runtime.

[**\<configuración>**](../configuration-element.md)  
&nbsp;&nbsp;**\<>de inicio**  

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
|`useLegacyV2RuntimeActivationPolicy`|Atributo opcional.<br /><br /> Especifica si se debe habilitar la directiva de activación en tiempo de ejecución de .NET Framework 2.0 o usar la directiva de activación de .NET Framework 4.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>atributo useLegacyV2RuntimeActivationPolicy

|Value|Descripción|
|-----------|-----------------|
|`true`|Habilite la directiva de activación en tiempo de ejecución de .NET Framework 2.0 para el tiempo de ejecución elegido, que consiste en enlazar técnicas de activación en tiempo de ejecución heredadas (como la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) al tiempo de ejecución elegido del archivo de configuración en lugar de limitarlas en la versión 2.0 de CLR. Por lo tanto, si se elige CLR versión 4 o posterior del archivo de configuración, los ensamblados de modo mixto creados con versiones anteriores de .NET Framework se cargan con la versión CLR elegida. Establecer este valor impide que la versión 1.1 o la versión 2.0 de CLR se carguen en el mismo proceso, deshabilitando eficazmente la característica en paralelo en proceso.|
|`false`|Use la directiva de activación predeterminada para .NET Framework 4 y versiones posteriores, que consiste en permitir que las técnicas de activación en tiempo de ejecución heredadas carguen LA versión 1.1 o 2.0 de CLR en el proceso. Establecer este valor impide que los ensamblados en modo mixto se carguen en .NET Framework 4 o posterior a menos que se hayan compilado con .NET Framework 4 o posterior. Este es el valor predeterminado.|

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime. Las aplicaciones creadas con la versión ** \<** en tiempo de ejecución 1.1 o posterior deben usar el elemento supportedRuntime>.|
|[\<supportedRuntime>](supportedruntime-element.md)|Especifica qué versiones de Common Language Runtime admite la aplicación.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|

## <a name="remarks"></a>Observaciones

 El ** \<elemento supportedRuntime>** debe ser utilizado por todas las aplicaciones creadas con la versión 1.1 o posterior del tiempo de ejecución. Las aplicaciones creadas para admitir solo la ** \<** versión 1.0 del tiempo de ejecución deben usar el elemento requiredRuntime>.

 El código de inicio de una aplicación ** \<** hospedada en Microsoft Internet Explorer omite el elemento>de inicio y sus elementos secundarios.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>El atributo useLegacyV2RuntimeActivationPolicy

 Este atributo es útil si la aplicación usa rutas de activación heredadas, como la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que esas rutas de acceso activen la versión 4 de CLR en lugar de una versión anterior, o si la aplicación se compila con .NET Framework 4 pero tiene una dependencia de un ensamblado en modo mixto creado con una versión anterior de .NET Framework. En esos escenarios, establezca `true`el atributo en .

> [!NOTE]
> Establecer el `true` atributo para impedir que la versión 1.1 o la versión 2.0 de CLR se carguen en el mismo proceso, deshabilitando eficazmente la característica en paralelo en proceso (consulte Ejecución en paralelo para la [interoperabilidad COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.

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

## <a name="see-also"></a>Consulte también

- [Esquema de configuración de inicio](index.md)
- [Esquema del archivo de configuración](../index.md)
- [Cómo: Configurar una aplicación para admitir .NET Framework 4 o versiones posteriores](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Ejecución simultánea para interoperabilidad COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [Ejecución en paralelo en proceso](../../../deployment/in-process-side-by-side-execution.md)
