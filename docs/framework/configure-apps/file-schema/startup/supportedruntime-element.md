---
title: <supportedRuntime>elemento de configuración - .NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: e16eb098db4bce115a5f1e043829eb272c952860
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153703"
---
# <a name="supportedruntime-element"></a>\<supportedRuntime> elemento

Especifica qué versión de Common Language Runtime y, opcionalmente, la versión de .NET Framework admite la aplicación.  

[\<configuración>](../configuration-element.md)  
&nbsp;&nbsp;[\<>de inicio](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  

## <a name="syntax"></a>Sintaxis

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|**version**|Atributo opcional.<br /><br /> Un valor de cadena que especifica la versión de Common Language Runtime (CLR) que es compatible con esta aplicación. Para ver los `version` valores válidos del atributo, consulte la sección ["valores de la versión en tiempo de ejecución".](#version) **Nota:**  A través de .NET Framework 3.5, el valor "*versión en tiempo de ejecución*" toma el formato *principal.* *menor de edad*. *construir*. A partir de .NET Framework 4, solo se requieren los números de versión principal y secundaria (es decir, "v4.0" en lugar de "v4.0.30319"). Se recomienda la cadena más corta.|
|**Sku**|Atributo opcional.<br /><br /> Valor de cadena que especifica la referencia de almacén (SKU), que a su vez especifica qué versión de .NET Framework es compatible con esta aplicación.<br /><br /> A partir de .NET Framework 4.0, se recomienda el uso del atributo `sku`.  Cuando está presente, indica la versión de .NET Framework que la aplicación tiene como destino.<br /><br /> Para conocer los valores válidos del atributo sku, consulte la sección ["sku id" values.](#sku)|

## <a name="remarks"></a>Observaciones

Si ** \<** el elemento supportedRuntime>no está presente en el archivo de configuración de la aplicación, se utiliza la versión del tiempo de ejecución utilizado para compilar la aplicación.

El ** \<elemento supportedRuntime>** debe ser utilizado por todas las aplicaciones creadas con la versión 1.1 o posterior del tiempo de ejecución. Las aplicaciones creadas para admitir solo la [ \<](../startup/requiredruntime-element.md) versión 1.0 del tiempo de ejecución deben usar el elemento requiredRuntime>.

> [!NOTE]
> Si utiliza la función [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) para especificar el `<requiredRuntime>` archivo de configuración, debe utilizar el elemento para todas las versiones del tiempo de ejecución. El `<supportedRuntime>` elemento se omite cuando se utiliza [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
En el caso de aplicaciones que admiten versiones del runtime de .NET Framework 1.1 a través de la versión 3.5, cuando se admiten varias versiones del runtime, el primer elemento debería especificar la versión preferida y el último elemento la que se considera como última posibilidad. Para las aplicaciones que admiten .NET Framework `version` 4.0 o versiones posteriores, el atributo indica la versión de CLR, que es común a .NET Framework 4 y versiones posteriores, y el `sku` atributo indica la única versión de .NET Framework que la aplicación tiene como destino.

Si ** \<** el elemento supportedRuntime `sku`>con el atributo está presente en el archivo de configuración y la versión instalada de .NET Framework es inferior a la versión compatible especificada, la aplicación no se ejecuta y, en su lugar, muestra un mensaje que pide instalar la versión compatible. De lo contrario, la aplicación intenta ejecutarse en cualquier versión instalada, pero puede comportarse de forma inesperada si no es totalmente compatible con esa versión. (Para conocer las diferencias de compatibilidad entre las versiones de .NET Framework, vea Compatibilidad de [aplicaciones en .NET Framework .)](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility) Por lo tanto, se recomienda incluir este elemento en el archivo de configuración de la aplicación para facilitar el diagnóstico de errores. (El archivo de configuración generado automáticamente por Visual Studio al crear un nuevo proyecto ya lo contiene.)
  
> [!NOTE]
> Si la aplicación usa rutas de acceso de activación heredadas, como la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que esas rutas de acceso activen la versión 4 de CLR en lugar de una versión anterior, o si la aplicación se compila con .NET Framework 4 pero tiene una dependencia de un ensamblado de modo mixto compilado con una versión anterior de .NET Framework, no es suficiente especificar .NET Framework 4 en la lista de tiempos de ejecución admitidos. Además, [ \<](../startup/startup-element.md) en el elemento de inicio> `useLegacyV2RuntimeActivationPolicy` del `true`archivo de configuración, debe establecer el atributo en . Sin embargo, `true` establecer este atributo en significa que todos los componentes creados con versiones anteriores de .NET Framework se ejecutan con .NET Framework 4 en lugar de los tiempos de ejecución con los que se crearon.

Se recomienda probar las aplicaciones con todas las versiones de .NET Framework en las que puedan ejecutarse.

<a name="version"></a>
## <a name="runtime-version-values"></a>Valores de "runtime version"
El `runtime` atributo especifica la versión de Common Language Runtime (CLR) necesaria para una aplicación determinada. Tenga en cuenta que todas las versiones de .NET Framework v4.x especifican CLR. `v4.0` En la tabla siguiente se enumeran los `version` valores válidos para el valor de *versión* en tiempo de ejecución del atributo.

|Versión de .NET Framework|Atributo `version`|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3,5|"v2.0.50727"|
|4.0-4.8|"v4.0"|

## <a name="sku-id-values"></a><a name="sku"></a>Valores "sku id"

El `sku` atributo usa un moniker de marco de trabajo de destino (TFM) para indicar la versión de .NET Framework que la aplicación tiene como destino y requiere para ejecutarse. En la tabla siguiente se enumeran `sku` los valores válidos admitidos por el atributo, empezando por .NET Framework 4.

|Versión de .NET Framework|Atributo `sku`|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0, Client Profile|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, actualización 1 de la plataforma|". NETFramework,Version-v4.0.1"|
|4.0, Client Profile, actualización 1|". NETFramework,Version-v4.0.1,Profile-Client"|
|4.0, actualización 2 de la plataforma|". NETFramework,Version-v4.0.2"|
|4.0, Client Profile, actualización 2|". NETFramework,Version-v4.0.2,Profile-Client"|
|4.0, actualización 3 de la plataforma|". NETFramework,Version-v4.0.3"|
|4.0, Client Profile, actualización 3|". NETFramework,Version-v4.0.3,Profile-Client"|
|4.5.|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4.6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|". NETFramework,Version-v4.6.2"|
|4,7|". NETFramework,Version-v4.7"|
|4.7.1|". NETFramework,Version-v4.7.1"|
|4.7.2|". NETFramework,Version-v4.7.2"|
|4.8|". NETFramework,Version-v4.8"|

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo especificar la versión del runtime compatible en un archivo de configuración. El archivo de configuración indica que la aplicación tiene como destino .NET Framework 4.7.

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se puede utilizar en el archivo de configuración de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema de configuración de inicio](../startup/index.md)
- [Esquema del archivo de configuración](../index.md)
- [Ejecución en paralelo en proceso](../../../deployment/in-process-side-by-side-execution.md)
