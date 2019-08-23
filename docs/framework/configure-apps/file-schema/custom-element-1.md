---
title: Elemento personalizado para SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8fae3673fe72d036802cb1a8366aaa2430c38884
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927499"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Elemento personalizado para SingleTagSectionHandler

Define la configuración de una sección de configuración personalizada que está definida \<por una sección > elemento y <xref:System.Configuration.SingleTagSectionHandler> utiliza la clase.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; *\<sectionName>*

## <a name="syntax"></a>Sintaxis

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>Atributos

Los atributos y los valores de atributo son definidos por el usuario.

## <a name="parent-element"></a>Elemento primario

|     | DESCRIPCIÓN |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

None

## <a name="remarks"></a>Comentarios

**El\<elemento sectionName >** es un elemento personalizado definido por una [ **\<sección >** ](section-element.md) etiqueta en el [ **\<elemento > configSections**](configsections-element-for-configuration.md) . El sistema de configuración devuelve <xref:System.Collections.IDictionary> un objeto cuando se <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>llama a.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara un elemento personalizado denominado  **\<sampleSection >** que contiene los valores leídos por la <xref:System.Configuration.SingleTagSectionHandler> clase:

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
