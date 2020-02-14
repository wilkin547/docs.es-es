---
title: Elemento personalizado para SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 1d0431085a04d3fb817dfe0883779acc4d693084
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214789"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Elemento personalizado para SingleTagSectionHandler

Define la configuración de una sección de configuración personalizada que se define mediante una \<sección > elemento y utiliza la clase <xref:System.Configuration.SingleTagSectionHandler>.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; *\<sectionName >*

## <a name="syntax"></a>Sintaxis

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>Atributos

Los atributos y los valores de atributo son definidos por el usuario.

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

None

## <a name="remarks"></a>Observaciones

El elemento **\<sectionName >** es un elemento personalizado definido por una [**sección de\<>** ](section-element.md) etiqueta del elemento\<[**configSections >** ](configsections-element-for-configuration.md) . El sistema de configuración devuelve un objeto <xref:System.Collections.IDictionary> cuando se llama a <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara un elemento personalizado denominado **\<> sampleSection** que contiene la configuración leída por la clase <xref:System.Configuration.SingleTagSectionHandler>:

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
