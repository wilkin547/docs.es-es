---
title: <remove> (elemento para <configSections>)
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 9ceffd3194c7df41f12ac6cd6b589602965b4920
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279102"
---
# <a name="remove-element-for-configsections"></a>\<Quitar > (elemento) para \<configSections >

Quita una sección predefinida o un grupo de sección.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Sintaxis

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **name**  | Atributo necesario.<br><br>Especifica el nombre de la sección o el grupo de sección para quitar. |

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [**\<configSections>** Element](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Contiene las declaraciones de espacio de nombres y la sección de configuración. |

## <a name="child-elements"></a>Elementos secundarios

Ninguna

## <a name="remarks"></a>Comentarios

Puede usar el  **\<quitar >** elemento para quitar las secciones y grupos de la aplicación que se han definido en un nivel superior de la jerarquía del archivo de configuración.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo usar el  **\<quitar >** elemento en un archivo de configuración de aplicación para quitar una sección definida anteriormente en el archivo de configuración del equipo.

El siguiente código de archivo de configuración del equipo declara la sección  **\<sampleSection >**:

```xml
<!-- Machine.config file -->
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

El siguiente código de archivo de configuración de la aplicación se quita la  **\<sampleSection >** sección. Después de la eliminación, la aplicación no puede recuperar la configuración de  **\<sampleSection >**.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.

## <a name="see-also"></a>Vea también

- [Esquema de archivo de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
