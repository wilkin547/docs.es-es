---
title: '<supportedRuntime> elemento de configuración: .NET'
ms.date: 04/02/2019
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: cc221c71b68c21b61b5fa27e0972b9e9156dbc3b
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558678"
---
# <a name="supportedruntime-element"></a>Elemento \<supportedRuntime>

Especifica qué Common Language Runtime versión y, opcionalmente, .NET Framework versión admitida por la aplicación.  

[\<configuration>](../configuration-element.md)  
&nbsp;&nbsp;[\<startup>](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  

## <a name="syntax"></a>Sintaxis

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|**version**|Atributo opcional.<br /><br /> Un valor de cadena que especifica la versión de Common Language Runtime (CLR) que es compatible con esta aplicación. Para obtener los valores válidos del `version` atributo, vea la sección [sobre valores de la versión en tiempo de ejecución](#version) . **Nota:**  A través del .NET Framework 3,5, el valor de "*versión del tiempo de ejecución*" tiene la forma *principal*. *secundaria*. *compilación*. A partir de la .NET Framework 4, solo se requieren los números de versión principal y secundaria (es decir, "v 4.0" en lugar de "v 4.0.30319"). Se recomienda la cadena más corta.|
|**sku**|Atributo opcional.<br /><br /> Valor de cadena que especifica la referencia de almacén (SKU), que a su vez especifica qué versión de .NET Framework es compatible con esta aplicación.<br /><br /> A partir de .NET Framework 4.0, se recomienda el uso del atributo `sku`.  Cuando está presente, indica la versión de .NET Framework que la aplicación tiene como destino.<br /><br /> Para obtener los valores válidos del atributo SKU, consulte la sección [valores de "SKU ID"](#sku) .|

## <a name="remarks"></a>Comentarios

Si el **\<supportedRuntime>** elemento no está presente en el archivo de configuración de la aplicación, se utiliza la versión del Runtime que se usa para compilar la aplicación.

**\<supportedRuntime>** Todas las aplicaciones compiladas con la versión 1,1 o posterior del tiempo de ejecución deben usar el elemento. Las aplicaciones compiladas para admitir solo la versión 1,0 del Runtime deben usar el [\<requiredRuntime>](requiredruntime-element.md) elemento.

> [!NOTE]
> Si usa la función [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) para especificar el archivo de configuración, debe usar el `<requiredRuntime>` elemento para todas las versiones del Runtime. El `<supportedRuntime>` elemento se omite cuando se usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
En el caso de aplicaciones que admiten versiones del runtime de .NET Framework 1.1 a través de la versión 3.5, cuando se admiten varias versiones del runtime, el primer elemento debería especificar la versión preferida y el último elemento la que se considera como última posibilidad. En el caso de las aplicaciones que admiten la .NET Framework 4,0 o versiones posteriores, el `version` atributo indica la versión de CLR, que es común a .NET Framework 4 y versiones posteriores, y el `sku` atributo indica la versión de .NET Framework única que tiene como destino la aplicación.

Si el **\<supportedRuntime>** elemento con el `sku` atributo está presente en el archivo de configuración y la versión de .NET Framework instalada es menor que la versión admitida especificada, la aplicación no se ejecuta y muestra un mensaje en el que se le pide que instale la versión compatible. De lo contrario, la aplicación intenta ejecutarse en cualquier versión instalada, pero puede comportarse de forma inesperada si no es totalmente compatible con esa versión. (Para conocer las diferencias de compatibilidad entre las versiones de .NET Framework, vea [compatibilidad de aplicaciones en el .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility)). Por lo tanto, se recomienda incluir este elemento en el archivo de configuración de la aplicación para facilitar el diagnóstico de errores. (El archivo de configuración generado automáticamente por Visual Studio al crear un nuevo proyecto ya lo contiene).
  
> [!NOTE]
> Si la aplicación usa rutas de activación heredadas, como la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que esas rutas de acceso activen la versión 4 de CLR en lugar de una versión anterior, o si la aplicación se compila con el .NET Framework 4 pero tiene una dependencia en un ensamblado en modo mixto creado con una versión anterior del .NET Framework, no basta con especificar el .NET Framework 4 en la lista de tiempos de ejecución admitidos. Además, en el [ \<startup> elemento](startup-element.md) del archivo de configuración, debe establecer el `useLegacyV2RuntimeActivationPolicy` atributo en `true` . Sin embargo, si se establece este atributo en, `true` todos los componentes compilados con versiones anteriores de la .NET Framework se ejecutan con el .NET Framework 4 en lugar de los tiempos de ejecución con los que se compilaron.

Se recomienda probar las aplicaciones con todas las versiones de .NET Framework en las que puedan ejecutarse.

<a name="version"></a>
## <a name="runtime-version-values"></a>Valores de "runtime version"
El `runtime` atributo especifica la versión de Common Language Runtime (CLR) necesaria para una aplicación determinada. Tenga en cuenta que todas las versiones de .NET Framework V4. x especifican el `v4.0` CLR. En la tabla siguiente se enumeran los valores válidos para el valor de *versión en tiempo de ejecución* del `version` atributo.

|Versión de .NET Framework|Atributo `version`|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3,5|"v2.0.50727"|
|4-4.8|"v4.0"|

## <a name="sku-id-values"></a><a name="sku"></a> valores de "SKU ID"

El `sku` atributo usa un moniker de la plataforma de destino (TFM) para indicar la versión de la .NET Framework que la aplicación tiene como destino y que necesita para ejecutarse. En la tabla siguiente se enumeran los valores válidos que admite el `sku` atributo, comenzando por el .NET Framework 4.

|Versión de .NET Framework|Atributo `sku`|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0, Client Profile|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, actualización 1 de la plataforma|". NETFramework, versión = v 4.0.1 "|
|4.0, Client Profile, actualización 1|". NETFramework, versión = v 4.0.1, perfil = cliente "|
|4.0, actualización 2 de la plataforma|". NETFramework, versión = v 4.0.2 "|
|4.0, Client Profile, actualización 2|". NETFramework, version = v 4.0.2, Profile = Client "|
|4.0, actualización 3 de la plataforma|". NETFramework, versión = v 4.0.3 "|
|4.0, Client Profile, actualización 3|". NETFramework, versión = v 4.0.3, perfil = cliente "|
|4.5.|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4,6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|". NETFramework, versión = v 4.6.2 "|
|4,7|". NETFramework, versión = v 4.7 "|
|4.7.1|". NETFramework, versión = v 4.7.1 "|
|4.7.2|". NETFramework, versión = v 4.7.2 "|
|4.8|". NETFramework, versión = v 4.8 "|

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo especificar la versión del runtime compatible en un archivo de configuración. El archivo de configuración indica que la aplicación tiene como destino el .NET Framework 4,7.

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

- [Esquema de la configuración de inicio](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Ejecución en paralelo en proceso](../../../deployment/in-process-side-by-side-execution.md)
