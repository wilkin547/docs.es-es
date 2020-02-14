---
title: Elemento <configSections> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 5b71eb81769db1188f97b1646a608df172ff56c5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214822"
---
# <a name="configsections-element-for-configuration"></a>\<elemento > configSections para la configuración de \<>

Contiene la sección de configuración y las declaraciones de espacio de nombres.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; **\<configSections >**

## <a name="attributes"></a>Atributos

None

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [ **\<sección >** ](section-element.md) | Contiene una declaración de sección de configuración. |
| [ **\<sectionGroup >** ](sectiongroup-element-for-configsections.md) | Define un espacio de nombres para las secciones de configuración. |
| [ **\<remove>** ](remove-element-for-configsections.md) | Quita una sección o grupo de sección predefinido. |
| [ **\<clear>** ](clear-element-for-configsections.md) | Borra todas las secciones y grupos de sección definidos previamente. |

## <a name="remarks"></a>Observaciones

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

## <a name="see-also"></a>Consulte también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
