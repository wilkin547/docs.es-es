---
title: Elemento <remove> para <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0695d5638589d1afe48553fe32b8d070e3938353
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119203"
---
# <a name="remove-element-for-appsettings"></a>\<quitar > elemento para \<appSettings >

Quita la configuración de la aplicación personalizada.

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<quitar >**

## <a name="syntax"></a>Sintaxis

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a>Atributo

|         | Descripción |
| ------- | ----------- |
| **key** | Atributo necesario.<br><br>Especifica el nombre de la clave que se va a quitar. |

### <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación. |

## <a name="child-elements"></a>Elementos secundarios

Ninguno

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo quitar un valor de configuración personalizado para `ApplicationName`:

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](../index.md)
