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
ms.openlocfilehash: 31b53837e24029fc7ff0b576d95c0213041a434e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927665"
---
# <a name="configsections-element-for-configuration"></a>\<elemento > configSections para \<la configuración >

Contiene la sección de configuración y las declaraciones de espacio de nombres.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; **\<configSections>**

## <a name="attributes"></a>Atributos

None

## <a name="parent-element"></a>Elemento primario

|     | DESCRIPCIÓN |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | DESCRIPCIÓN |
| --- | ----------- |
| [ **\<> de la sección**](section-element.md) | Contiene una declaración de sección de configuración. |
| [ **\<sectionGroup>** ](sectiongroup-element-for-configsections.md) | Define un espacio de nombres para las secciones de configuración. |
| [ **\<remove>** ](remove-element-for-configsections.md) | Quita una sección o grupo de sección predefinido. |
| [ **\<clear>** ](clear-element-for-configsections.md) | Borra todas las secciones y grupos de sección definidos previamente. |

## <a name="remarks"></a>Comentarios

Si este elemento se encuentra en un archivo de configuración, debe ser el primer elemento secundario del  **\<elemento Configuration >** .

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
