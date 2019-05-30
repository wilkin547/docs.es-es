---
title: Elemento <configSections> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d522d004630dee942e24c39a936feae7dc957bd5
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300787"
---
# <a name="configsections-element-for-configuration"></a>\<configSections > (elemento) para \<configuración >

Contiene las declaraciones de espacio de nombres y la sección de configuración.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp; **\<configSections>**

## <a name="attributes"></a>Atributos

Ninguna

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [ **\<sección >** ](~/docs/framework/configure-apps/file-schema/section-element.md) | Contiene una declaración de la sección de configuración. |
| [ **\<sectionGroup>** ](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Define un espacio de nombres para las secciones de configuración. |
| [ **\<remove>** ](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | Quita una sección predefinida o un grupo de sección. |
| [ **\<clear>** ](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | Borra todas las secciones definidas anteriormente y grupos de sección. |

## <a name="remarks"></a>Comentarios

Si este elemento está en un archivo de configuración, debe ser el primer elemento secundario de la  **\<configuración >** elemento.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo definir una sección de configuración y definir la configuración de esa sección:

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.

## <a name="see-also"></a>Vea también

- [Esquema de archivo de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
