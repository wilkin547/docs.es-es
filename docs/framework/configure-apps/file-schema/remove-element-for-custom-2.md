---
title: <remove>elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: cd338ff2d613be31ab1524f6baed6107f803a688
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920948"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<quitar > elemento de NameValueSectionHandler y DictionarySectionHandler

Quita un valor definido previamente.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**

## <a name="syntax"></a>Sintaxis

```xml
<add remove="key" />
```

## <a name="attribute"></a>Atributo

|           | DESCRIPCIÓN |
| --------- | ----------- |
| **key**   | Atributo necesario.<br><br>Especifica el nombre de la configuración que se va a quitar. |

## <a name="parent-element"></a>Elemento primario

| Elemento | DESCRIPCIÓN |
| ------- | ------------|
| [ **sectionName>\<** elemento](custom-element-2.md) | Define la configuración de las secciones de configuración personalizadas <xref:System.Configuration.NameValueSectionHandler> que <xref:System.Configuration.DictionarySectionHandler> utilizan las clases y. |

## <a name="child-elements"></a>Elementos secundarios

None

## <a name="remarks"></a>Comentarios

Puede usar el  **\<elemento Remove >** para quitar la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar el elemento  **\<Remove >** en un archivo de configuración de la aplicación para quitar la configuración definida previamente en el archivo de configuración del equipo.

El siguiente código de archivo de configuración de máquina declara  **\<** la sección de la sección > y le `key1` agrega `key2`dos valores de configuración:

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

El siguiente código de archivo de configuración de `key2` la aplicación quita la configuración de  **\<la sección >** :

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
