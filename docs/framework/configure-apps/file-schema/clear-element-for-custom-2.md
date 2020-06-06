---
title: <clear>elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: f6d860f35d22002030ffa3d09dd0d8a96116bf5e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214742"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<clear>elemento para NameValueSectionHandler y DictionarySectionHandler

Borra todos los valores de configuración definidos previamente en una sección.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Sintaxis

```xml
<clear />
```

## <a name="attributes"></a>Atributos

None

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ------------|
| [**\<sectionName>** Element](custom-element-2.md) | Define la configuración de las secciones de configuración personalizadas que utilizan las <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> clases y. |

## <a name="child-elements"></a>Elementos secundarios

None

## <a name="remarks"></a>Observaciones

Puede usar el **\<clear>** elemento para quitar toda la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.

## <a name="example"></a>Ejemplo

En este ejemplo se define un archivo de configuración del equipo y un archivo de configuración de la aplicación y se muestra cómo usar el **\<clear>** elemento en un archivo de configuración de la aplicación para borrar las secciones definidas anteriormente en el archivo de configuración del equipo.

El siguiente código de archivo de configuración de máquina declara la sección **\<mySection>** :

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

El siguiente código de archivo de configuración de la aplicación quita todos los valores de **\<mySection>** . La aplicación no puede recuperar ninguno de los valores de configuración que se declararon en la **\<mySection>** sección del archivo de configuración del equipo.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
