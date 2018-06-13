---
title: '&lt;quitar&gt; elemento para NameValueSectionHandler y DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 61f1c98d3f12b5aa1d25595ca28328602683b073
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742918"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Quitar > (elemento) para NameValueSectionHandler y DictionarySectionHandler

Quita un valor definido anteriormente.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Quitar >**

## <a name="syntax"></a>Sintaxis

```xml
<add remove="key" />
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **key**   | Atributo necesario.<br><br>Especifica el nombre de la configuración para quitar. |

## <a name="parent-element"></a>Elemento primario

| Elemento | Descripción |
| ------- | ------------|
| [**\<sectionName >** elemento](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Define los valores de las secciones de configuración personalizada que utilizan el <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> clases. |

## <a name="child-elements"></a>Elementos secundarios

Ninguna

## <a name="remarks"></a>Comentarios

Puede usar el  **\<quitar >** elemento que se va a quitar la configuración de la aplicación que se han definido en un nivel superior en la jerarquía de archivos de configuración.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo utilizar el  **\<quitar >** elemento en un archivo de configuración de aplicación para quitar los valores definidos anteriormente en el archivo de configuración del equipo.

El siguiente código de archivo de configuración del equipo declara la sección  **\<mySection >** y agrega dos configuraciones, `key1` y `key2`, a él:

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

El siguiente código de archivo de configuración de la aplicación quita el `key2` de  **\<mySection >**:

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración de máquina (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.

## <a name="see-also"></a>Vea también

[Esquema de archivos de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
