---
title: Elemento <clear> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d321f3169344e9aa40d65b1722a533549de5315a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088736"
---
# <a name="clear-element-for-appsettings"></a>\<borrar > elemento para \<appSettings >

Borra la configuración personalizada de la aplicación.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**

## <a name="syntax"></a>Sintaxis

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>Atributos

Ninguno

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Contiene la configuración de la aplicación personalizada, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración de la aplicación personalizada. |

## <a name="child-elements"></a>Elementos secundarios

Ninguno

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo borrar las opciones de configuración personalizadas:

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](../index.md)
