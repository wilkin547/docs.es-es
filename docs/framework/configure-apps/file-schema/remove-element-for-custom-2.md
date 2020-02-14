---
title: elemento <remove> para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214756"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<quitar > elemento de NameValueSectionHandler y DictionarySectionHandler

Quita un valor definido previamente.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<quitar >**

## <a name="syntax"></a>Sintaxis

```xml
<add remove="key" />
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **key**   | Atributo necesario.<br><br>Especifica el nombre de la configuración que se va a quitar. |

## <a name="parent-element"></a>Elemento primario

| Elemento | Descripción |
| ------- | ------------|
| [ **\<sectionName >** Element](custom-element-2.md) | Define la configuración de las secciones de configuración personalizadas que utilizan las clases <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler>. |

## <a name="child-elements"></a>Elementos secundarios

None

## <a name="remarks"></a>Observaciones

Puede usar el elemento **\<remove >** para quitar la configuración de la aplicación que se definió en un nivel superior en la jerarquía del archivo de configuración.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar el elemento **\<quitar >** de un archivo de configuración de la aplicación para quitar la configuración definida previamente en el archivo de configuración del equipo.

El siguiente código de archivo de configuración de máquina declara la sección **\<mi sección >** y le agrega dos valores, `key1` y `key2`:

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

El siguiente código de archivo de configuración de la aplicación quita el valor `key2` de **\<sección >** :

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

## <a name="see-also"></a>Consulte también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
