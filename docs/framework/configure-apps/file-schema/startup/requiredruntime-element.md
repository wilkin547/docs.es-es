---
title: <requiredRuntime> (elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697497"
---
# <a name="requiredruntime-element"></a>Elemento \<requiredRuntime>

Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime. Este elemento está en desuso y ya no debe usarse. [`supportedRuntime`](supportedruntime-element.md)En su lugar, se debe usar el elemento.

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a>Sintaxis

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`version`|Atributo opcional.<br /><br /> Valor de cadena que especifica la versión de .NET Framework que admite esta aplicación. El valor de cadena debe coincidir con el nombre de directorio que se encuentra en la .NET Framework raíz de instalación. No se analiza el contenido del valor de cadena.|
|`safemode`|Atributo opcional.<br /><br /> Especifica si el código de inicio en tiempo de ejecución busca en el registro para determinar la versión del tiempo de ejecución.|

## <a name="safemode-attribute"></a>SafeMode (atributo)

|Value|Descripción|
|-----------|-----------------|
|`false`|El código de inicio en tiempo de ejecución busca en el registro. Este es el valor predeterminado.|
|`true`|El código de inicio en tiempo de ejecución no busca en el registro.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`startup`|Contiene el `<requiredRuntime>` elemento.|

## <a name="remarks"></a>Comentarios
 Las aplicaciones compiladas para admitir solo la versión 1,0 del Runtime deben usar el `<requiredRuntime>` elemento. Las aplicaciones compiladas con la versión 1,1 o posterior del Runtime deben usar el `<supportedRuntime>` elemento.

> [!NOTE]
> Si usa la función [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) para especificar el archivo de configuración, debe usar el `<requiredRuntime>` elemento para todas las versiones del Runtime. El `<supportedRuntime>` elemento se omite cuando se usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).

 La `version` cadena de atributo debe coincidir con el nombre de la carpeta de instalación de la versión especificada del .NET Framework. Esta cadena no se interpreta. Si el código de inicio en tiempo de ejecución no encuentra una carpeta coincidente, el tiempo de ejecución no se carga; el código de inicio muestra un mensaje de error y se cierra.

> [!NOTE]
> El código de inicio de una aplicación que se hospeda en Microsoft Internet Explorer omite el `<requiredRuntime>` elemento.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de inicio](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Cómo: Configurar una aplicación para que admita .NET Framework 4 o versiones posteriores](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
