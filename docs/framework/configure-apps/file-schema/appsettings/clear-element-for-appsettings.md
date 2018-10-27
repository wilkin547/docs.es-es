---
title: '&lt;Borrar&gt; (elemento) para &lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: bc52e3149c213925ea64a8421ee65befeea4161e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184223"
---
# <a name="clear-element-for-appsettings"></a>\<Borrar > (elemento) para \<appSettings >

Borra la configuración de aplicación personalizada.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Borrar >**

## <a name="syntax"></a>Sintaxis

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>Atributos

Ninguna

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | Contiene la configuración de aplicación personalizada, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración de aplicación personalizada. |

## <a name="child-elements"></a>Elementos secundarios

Ninguna

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo borrar la configuración personalizada:

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>Vea también

- [Esquema de archivo de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
