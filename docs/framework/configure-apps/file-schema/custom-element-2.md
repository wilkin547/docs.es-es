---
title: Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215475"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler

Define la configuración de las secciones de configuración personalizadas que utilizan las <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> clases y.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a>Atributos

None

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<add>**](add-element-for-custom-2.md)para <xref:System.Configuration.NameValueSectionHandler> y<xref:System.Configuration.DictionarySectionHandler>  | Agrega la configuración de la aplicación personalizada. |
| [**\<remove>**](remove-element-for-custom-2.md)para <xref:System.Configuration.NameValueSectionHandler> y<xref:System.Configuration.DictionarySectionHandler> | Quita un valor definido previamente. |
| [**\<clear>**](clear-element-for-custom-2.md)para <xref:System.Configuration.NameValueSectionHandler> y<xref:System.Configuration.DictionarySectionHandler> | Borra todos los valores de configuración definidos previamente en una sección. |

## <a name="remarks"></a>Comentarios

El **\<sectionName>** elemento es un elemento personalizado definido por una **\<section>** etiqueta en el **\<configSections>** elemento.

En la tabla siguiente se muestra el tipo de objeto que devuelve el método ConfigurationSettings. GetConfig para cada controlador de sección de configuración:

| Controlador de la sección de configuración                        | Tipo de valor devuelto                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo declarar secciones que utilizan <xref:System.Configuration.DictionarySectionHandler> las <xref:System.Configuration.NameValueSectionHandler> clases y.

El primer elemento personalizado es **\<dictionarySample>** , que contiene la configuración leída por la <xref:System.Configuration.DictionarySectionHandler> clase en el `System.dll` ensamblado. El segundo elemento personalizado es **\<mySection>** , que contiene la configuración leída por la <xref:System.Configuration.NameValueSectionHandler> clase en el `System.dll` ensamblado.

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
