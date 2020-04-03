---
title: Elemento personalizado para SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635396"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Elemento personalizado para SingleTagSectionHandler

Define la configuración en una sección \<de configuración personalizada <xref:System.Configuration.SingleTagSectionHandler> definida por una sección> elemento y utiliza la clase.

sección &nbsp; &nbsp;de configuración [** \<>Nombre**](configuration-element.md) * \<>*

## <a name="syntax"></a>Sintaxis

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a>Atributos

Los atributos y los valores de atributo están definidos por el usuario.

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [**\<configuración>**](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

None

## <a name="remarks"></a>Observaciones

El ** \<** elemento de>sectionName es [** \<**](section-element.md) un elemento personalizado definido por una etiqueta de>de sección en el [** \<elemento>configSections.**](configsections-element-for-configuration.md) El sistema de <xref:System.Collections.IDictionary> configuración devuelve <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>un objeto cuando se llama a .

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara un elemento personalizado <xref:System.Configuration.SingleTagSectionHandler> denominado ** \<sampleSection>** que contiene la configuración leída por la clase:

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

Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Vea también

- [Esquema de archivo de configuración para .NET Framework](index.md)
