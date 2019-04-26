---
title: Elemento <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 9a7b25c74763c020c0e19c3f6099db9001acf773
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705420"
---
# <a name="configuration-element"></a>\<Configuración > elemento

Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.

**\<configuration>**

## <a name="syntax"></a>Sintaxis

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>Atributos

Ninguna

## <a name="parent-element"></a>Elemento primario

Ninguna

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Especifica la directiva de enlace del ensamblado en el nivel de configuración.|
| [**\<Inicio >** esquema de configuración](~/docs/framework/configure-apps/file-schema/startup/index.md) | Todos los elementos en el esquema de configuración de inicio. |
| [**\<en tiempo de ejecución >** esquema de configuración](~/docs/framework/configure-apps/file-schema/runtime/index.md) | Todos los elementos en el esquema de configuración en tiempo de ejecución. |
| [**\<System.Runtime.Remoting >** esquema de configuración](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Todos los elementos en el esquema de configuración de comunicación remota. |
| [**\<system.Net >** esquema de configuración](~/docs/framework/configure-apps/file-schema/network/index.md) | Todos los elementos en el esquema de configuración de red. |
| [**\<cryptographySettings >** esquema de configuración](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | Todos los elementos en el esquema de configuración de criptografía. |
| [**\<Configuración >** esquema de secciones](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | Todos los elementos en el esquema de configuración de la sección de configuración. |
| [Esquema de la configuración de seguimiento y depuración](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | Todos los elementos en el esquema de configuración de seguimiento y depuración. |
| [Esquema de configuración de la configuración de ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Todos los elementos en el esquema de configuración de ASP.NET, que incluye elementos de configuración de aplicaciones y sitios Web de ASP.NET. Utilizado en *Web.config* archivos. |
| [**\<webServices >** esquema de configuración](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Todos los elementos en el esquema de configuración de servicios Web. |
| [Esquema de configuración web](~/docs/framework/configure-apps/file-schema/web/index.md) | Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS. Utilizado en *aspnet.config* archivos. |

## <a name="remarks"></a>Comentarios

Cada archivo de configuración debe contener exactamente un  **\<configuración >** elemento.

## <a name="see-also"></a>Vea también

- [Esquema de archivo de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
