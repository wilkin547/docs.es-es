---
title: elemento <add> para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac07fc9ba6f030209a5e0d0160689fab95bc1b4a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088761"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<agregar > elemento para NameValueSectionHandler y DictionarySectionHandler

Agrega la configuración de la aplicación personalizada. Cada **\<agregar >** etiqueta contiene un par clave-valor.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<agregar >**

## <a name="syntax"></a>Sintaxis

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a>Atributos

| Atributo | Descripción |
| --------- | ----------- |
| **key**   | Atributo necesario.<br><br>Especifica el nombre de la configuración. |
| **valor** | Atributo necesario.<br><br>Especifica el valor de la configuración. |

## <a name="parent-element"></a>Elemento primario

| Elemento | Descripción |
| ------- | ------------|
| [ **\<sectionName >** Element](custom-element-2.md) | Define la configuración de las secciones de configuración personalizadas que utilizan las clases <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler>. |

## <a name="child-elements"></a>Elementos secundarios

Ninguno

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo definir una sección de configuración personalizada y usar el elemento **\<agregar >** para colocar la configuración en la sección:

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
