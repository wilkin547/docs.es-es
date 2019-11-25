---
title: elemento <clear> para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fff5a5c2a523480f2eaebb127ec98ff6e9908acf
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088713"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<borrar > elemento para NameValueSectionHandler y DictionarySectionHandler

Borra todos los valores de configuración definidos previamente en una sección.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**

## <a name="syntax"></a>Sintaxis

```xml
<clear />
```

## <a name="attributes"></a>Atributos

Ninguno

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ------------|
| [ **\<sectionName >** Element](custom-element-2.md) | Define la configuración de las secciones de configuración personalizadas que utilizan las clases <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler>. |

## <a name="child-elements"></a>Elementos secundarios

Ninguno

## <a name="remarks"></a>Comentarios

Puede usar el elemento **\<clear >** para quitar toda la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.

## <a name="example"></a>Ejemplo

En este ejemplo se define un archivo de configuración del equipo y un archivo de configuración de la aplicación y se muestra cómo usar el elemento **\<clear >** en un archivo de configuración de la aplicación para borrar las secciones definidas anteriormente en el archivo de configuración del equipo.

El siguiente código de archivo de configuración de máquina declara la sección **\<mi sección >** :

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

El siguiente código de archivo de configuración de la aplicación quita todos los valores de\<de la **sección >** . La aplicación no puede recuperar ninguno de los valores de configuración que se declararon en la sección **\<** sección del archivo de configuración del equipo.

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

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
