---
title: <supportedRuntime> elemento de configuración - .NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: 2b0bce015216c2eaf2c35aee2d9174f109dff16e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59974089"
---
# <a name="supportedruntime-element"></a>\<supportedRuntime > elemento

Especifica qué versión de common language runtime y, opcionalmente, la aplicación de versión de .NET Framework admite.  

[\<configuration>](../configuration-element.md)  
&nbsp;&nbsp;[\<startup>](../startup/startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  

## <a name="syntax"></a>Sintaxis

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|**version**|Atributo opcional.<br /><br /> Un valor de cadena que especifica la versión de Common Language Runtime (CLR) que es compatible con esta aplicación. Para los valores válidos de la `version` atributo, vea el [valores "runtime version"](#version) sección. **Nota:**  A través de .NET Framework 3.5, el "*en tiempo de ejecución versión*" valor adopta la forma *principales*. *menores*. *compilar*. A partir de [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], solo se requieren los números de versión principal y secundaria "(es decir, "v4.0" en lugar de "v4.0.30319"). Se recomienda la cadena más corta.|
|**sku**|Atributo opcional.<br /><br /> Valor de cadena que especifica la referencia de almacén (SKU), que a su vez especifica qué versión de .NET Framework es compatible con esta aplicación.<br /><br /> A partir de .NET Framework 4.0, se recomienda el uso del atributo `sku`.  Cuando está presente, indica la versión de .NET Framework que la aplicación tiene como destino.<br /><br /> Para los valores válidos del atributo de sku, consulte el [valores "sku id"](#sku) sección.|

## <a name="remarks"></a>Comentarios

Si el  **\<supportedRuntime >** elemento no está presente en el archivo de configuración de aplicación, se usa la versión del tiempo de ejecución utilizado para compilar la aplicación.

El  **\<supportedRuntime >** se debe utilizar el elemento todas las aplicaciones compiladas con la versión 1.1 o posterior del tiempo de ejecución. Las aplicaciones compiladas para admitir sólo la versión 1.0 del tiempo de ejecución deben usar la [ \<requiredRuntime >](../startup/requiredruntime-element.md) elemento.

> [!NOTE]
> Si usas el [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) función para especificar el archivo de configuración, debe usar el `<requiredRuntime>` (elemento) para todas las versiones del tiempo de ejecución. El `<supportedRuntime>` elemento se omite cuando se usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
En el caso de aplicaciones que admiten versiones del runtime de .NET Framework 1.1 a través de la versión 3.5, cuando se admiten varias versiones del runtime, el primer elemento debería especificar la versión preferida y el último elemento la que se considera como última posibilidad. Para las aplicaciones que admiten el .NET Framework 4.0 o versiones posteriores, el `version` atributo indica la versión de CLR, que es común para el .NET Framework 4 y versiones posteriores, y el `sku` atributo indica la versión de .NET Framework solo que el destinos de la aplicación. 

Si el  **\<supportedRuntime >** elemento con el `sku` atributo está presente en el archivo de configuración y la versión de .NET Framework instalada es inferior, a continuación, en la versión admitida especificada, la aplicación no se ejecuta y en su lugar mostrará un mensaje preguntándole si desea instalar la versión admitida. En caso contrario, la aplicación intenta ejecutarse en cualquier versión instalada, pero puede tener un comportamiento inesperado si no es totalmente compatible con esa versión. (Las diferencias de compatibilidad entre versiones de .NET Framework, vea [compatibilidad de aplicaciones en .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility).) Por lo tanto, se recomienda que incluya este elemento en el archivo de configuración de diagnósticos de errores más fácil. (El archivo de configuración generado automáticamente por Visual Studio al crear un nuevo proyecto ya contiene lo).
  
> [!NOTE]
> Si la aplicación usa rutas de acceso de activación heredada, como la [CorBindToRuntimeEx (función)](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que esas rutas de acceso para activar la versión 4 de CLR en lugar de una versión anterior, o si la aplicación se compila con la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]pero tiene una dependencia en un ensamblado de modo mixto generado con una versión anterior de .NET Framework, no es suficiente especificar el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] en la lista de los runtimes compatibles. Además, en el [ \<Inicio > elemento](../startup/startup-element.md) en el archivo de configuración, debe establecer el `useLegacyV2RuntimeActivationPolicy` atributo `true`. Sin embargo, establecer este atributo en `true` significa que todos los componentes compilados con versiones anteriores de .NET Framework se ejecutan utilizando [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] en lugar de los runtimes con los que se compilaron.

Se recomienda probar las aplicaciones con todas las versiones de .NET Framework en las que puedan ejecutarse.

<a name="version"></a> 
## <a name="runtime-version-values"></a>Valores de "runtime version"
El `runtime` atributo especifica la versión de Common Language Runtime (CLR) que se requiere para una aplicación determinada. Tenga en cuenta que especifican todas las versiones de .NET Framework v4.x el `v4.0` CLR. La tabla siguiente enumeran los valores válidos para el *en tiempo de ejecución versión* valor de la `version` atributo.

|Versión de .NET Framework|`version` Atributo|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3.5|"v2.0.50727"|
|4.0-4.8|"v4.0"|

## <a name="sku"></a> valores de "sku id"

El `sku` atributo usa un moniker de la plataforma de destino (TFM) para indicar la versión de .NET Framework que tiene como destino de la aplicación y necesita para ejecutarse. La tabla siguiente enumeran los valores válidos que son compatibles con el `sku` atributo, a partir de .NET Framework 4.

|Versión de .NET Framework|`sku` Atributo|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0, Client Profile|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, actualización 1 de la plataforma|". NETFramework, Version = v4.0.1 "|
|4.0, Client Profile, actualización 1|". NETFramework, Version = v4.0.1, perfil = Client "|
|4.0, actualización 2 de la plataforma|". NETFramework, Version = v4.0.2 "|
|4.0, Client Profile, actualización 2|". NETFramework, Version = v4.0.2, perfil = Client "|
|4.0, actualización 3 de la plataforma|". NETFramework, Version = verze 4.0.3 "|
|4.0, Client Profile, actualización 3|". NETFramework, Version = verze 4.0.3, perfil = Client "|
|4.5|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4.6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|". NETFramework, Version = v4.6.2 "|
|4.7|". NETFramework, Version = v4.7 "|
|4.7.1|". NETFramework, Version = v4.7.1 "|
|4.7.2|". NETFramework, Version = v4.7.2 "|
|4.8|". NETFramework, Version = v4.8 "|

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

## <a name="see-also"></a>Vea también

- [Esquema de la configuración de inicio](../startup/index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Ejecución en paralelo en proceso](../../../deployment/in-process-side-by-side-execution.md)