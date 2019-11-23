---
title: Elemento <configSections> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6024144b6f12df22369366f04c3cbad02c5011d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119015"
---
# <a name="configsections-element-for-configuration"></a>\<elemento > configSections para la configuración de \<>

Contiene la sección de configuración y las declaraciones de espacio de nombres.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; **\<configSections>**

## <a name="attributes"></a>Atributos

Ninguno

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [ **\<sección >** ](section-element.md) | Contiene una declaración de sección de configuración. |
| [ **\<sectionGroup>** ](sectiongroup-element-for-configsections.md) | Define un espacio de nombres para las secciones de configuración. |
| [ **\<remove>** ](remove-element-for-configsections.md) | Quita una sección o grupo de sección predefinido. |
| [ **\<clear>** ](clear-element-for-configsections.md) | Borra todas las secciones y grupos de sección definidos previamente. |

## <a name="remarks"></a>Comentarios

Si este elemento se encuentra en un archivo de configuración, debe ser el primer elemento secundario del elemento **\<configuration >** .

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:

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

Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
