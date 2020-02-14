---
title: Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215475"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>Elemento personalizado para NameValueSectionHandler y DictionarySectionHandler

Define la configuración de las secciones de configuración personalizadas que utilizan las clases <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler>.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp; **\<sectionName >**

## <a name="attributes"></a>Atributos

None

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [ **\<agregar >** ](add-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler>  | Agrega la configuración de la aplicación personalizada. |
| [ **\<quitar >** ](remove-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> | Quita un valor definido previamente. |
| [ **\<borrar >** ](clear-element-for-custom-2.md) para <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> | Borra todos los valores de configuración definidos previamente en una sección. |

## <a name="remarks"></a>Observaciones

El elemento **\<sectionName >** es un elemento personalizado definido por una **sección de\<>** etiqueta del elemento\<**configSections >** .

En la tabla siguiente se muestra el tipo de objeto que devuelve el método ConfigurationSettings. GetConfig para cada controlador de sección de configuración:

| Controlador de la sección de configuración                        | Tipo de valor devuelto                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo declarar secciones que usan las clases <xref:System.Configuration.DictionarySectionHandler> y <xref:System.Configuration.NameValueSectionHandler>.

El primer elemento personalizado es **\<dictionarySample >** , que contiene los valores leídos por la clase <xref:System.Configuration.DictionarySectionHandler> en el ensamblado de `System.dll`. El segundo elemento personalizado es **\<mi sección >** , que contiene los valores leídos por la clase <xref:System.Configuration.NameValueSectionHandler> en el ensamblado de `System.dll`.

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
