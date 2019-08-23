---
title: Elemento <add> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 594ba4f289012e775e93acba98056b60bdd94cbd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927746"
---
# <a name="add-element-for-appsettings"></a>\<Agregar > elemento para \<appSettings >

Agrega una configuración de aplicación personalizada.

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**

## <a name="syntax"></a>Sintaxis

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a>Atributos

|           | DESCRIPCIÓN |
| --------- | ----------- |
| **key**   | Atributo necesario.<br><br>Especifica el nombre de la clave que se va a agregar. |
| **value** | Atributo necesario.<br><br>Especifica el valor de la clave que se va a agregar. |

## <a name="parent-element"></a>Elemento primario

|     | DESCRIPCIÓN |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación. |

## <a name="child-elements"></a>Elementos secundarios

None

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo agregar un valor de configuración personalizado para el nombre de la aplicación:

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

En el ejemplo siguiente se `<add>` usa el elemento para definir dos valores de compatibilidad en una aplicación ASP.net:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](../index.md)
