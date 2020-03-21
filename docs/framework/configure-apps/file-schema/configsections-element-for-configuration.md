---
title: Elemento <configSections> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155354"
---
# <a name="configsections-element-for-configuration"></a>\<configSections> \<elemento para la configuración>

Contiene declaraciones de sección de configuración y espacio de nombres.

configuración &nbsp; &nbsp;>[** \<**](configuration-element.md) ** \<configSections>**

## <a name="attributes"></a>Atributos

None

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [**\<configuración>**](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<sección>**](section-element.md) | Contiene una declaración de sección de configuración. |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | Define un espacio de nombres para las secciones de configuración. |
| [**\<eliminar>**](remove-element-for-configsections.md) | Quita una sección o un grupo de secciones predefinidos. |
| [**\<>claro**](clear-element-for-configsections.md) | Borra todas las secciones y grupos de secciones definidos anteriormente. |

## <a name="remarks"></a>Observaciones

Si este elemento está en un archivo de configuración, debe ser el primer elemento secundario del elemento ** \<de configuración>.**

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

Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema de archivo de configuración para .NET Framework](index.md)
