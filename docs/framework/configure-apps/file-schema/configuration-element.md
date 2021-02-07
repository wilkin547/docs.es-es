---
description: 'Más información acerca de: <configuration> elemento'
title: <configuration> (elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: ee48a45ddb987201e84213a0d7674da004951ab1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699003"
---
# <a name="configuration-element"></a>Elemento \<configuration>

Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.

**\<configuration>**

## <a name="syntax"></a>Sintaxis

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>Atributos

None

## <a name="parent-element"></a>Elemento primario

None

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | Especifica la directiva de enlace del ensamblado en el nivel de configuración.|
| [**\<startup>** Esquema de configuración](./startup/index.md) | Todos los elementos del esquema de configuración de inicio. |
| [**\<runtime>** Esquema de configuración](./runtime/index.md) | Todos los elementos del esquema de configuración de tiempo de ejecución. |
| [**\<system.runtime.remoting>** Esquema de configuración](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Todos los elementos del esquema de configuración de comunicación remota. |
| [**\<system.Net>** Esquema de configuración](./network/index.md) | Todos los elementos del esquema de configuración de red. |
| [**\<cryptographySettings>** Esquema de configuración](./cryptography/index.md) | Todos los elementos del esquema de configuración de cifrado. |
| [**\<configuration>** Esquema de secciones](configuration-sections-schema.md) | Todos los elementos del esquema de configuración de la sección de configuración. |
| [Esquema de configuración de seguimiento y depuración](./trace-debug/index.md) | Todos los elementos del esquema de configuración de seguimiento y depuración. |
| [Esquema de opciones de configuración de ASP.NET](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Todos los elementos del esquema de configuración ASP.NET, que incluye elementos para configurar sitios web y aplicaciones de ASP.NET. Se usa en archivos de *Web.config* . |
| [**\<webServices>** Esquema de configuración](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Todos los elementos del esquema de configuración de servicios Web. |
| [Esquema de configuración Web](./web/index.md) | Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS. Se usa en archivos de *aspnet.config* . |

## <a name="remarks"></a>Observaciones

Cada archivo de configuración debe contener exactamente un **\<configuration>** elemento.

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
