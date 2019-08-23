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
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921246"
---
# <a name="configuration-element"></a>\<elemento Configuration >

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

|     | DESCRIPCIÓN |
| --- | ----------- |
| [ **\<assemblyBinding>** ](assemblybinding-element-for-configuration.md) | Especifica la directiva de enlace del ensamblado en el nivel de configuración.|
| [esquema de configuración de > de inicio  **\<** ](./startup/index.md) | Todos los elementos del esquema de configuración de inicio. |
| [esquema de configuración de **> en tiempo de ejecución \<** ](./runtime/index.md) | Todos los elementos del esquema de configuración de tiempo de ejecución. |
| [esquema de configuración de **System. Runtime. Remoting > \<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Todos los elementos del esquema de configuración de comunicación remota. |
| [esquema de configuración de **> .net del sistema \<** ](./network/index.md) | Todos los elementos del esquema de configuración de red. |
| [cryptographySettings esquema de configuración de >  **\<** ](./cryptography/index.md) | Todos los elementos del esquema de configuración de cifrado. |
| [esquema de secciones de Configuration >  **\<** ](configuration-sections-schema.md) | Todos los elementos del esquema de configuración de la sección de configuración. |
| [Esquema de la configuración de seguimiento y depuración](./trace-debug/index.md) | Todos los elementos del esquema de configuración de seguimiento y depuración. |
| [Esquema de opciones de configuración de ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Todos los elementos del esquema de configuración ASP.NET, que incluye elementos para configurar sitios web y aplicaciones de ASP.NET. Se usa en los archivos *Web. config* . |
| [esquema de configuración de > de servicios WebService  **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Todos los elementos del esquema de configuración de servicios Web. |
| [Esquema de configuración web](./web/index.md) | Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS. Se usa en los archivos *Aspnet. config* . |

## <a name="remarks"></a>Comentarios

Cada archivo de configuración debe contener exactamente  **\<** un elemento de > de configuración.

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
