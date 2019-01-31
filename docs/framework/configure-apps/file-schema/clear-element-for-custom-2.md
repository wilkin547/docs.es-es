---
title: <clear> elemento para NameValueSectionHandler y DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ad3ac93b2a7f92cd33787620fc0caa2b632aa072
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281884"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Borrar > elemento para NameValueSectionHandler y DictionarySectionHandler

Borra todos los valores definidos anteriormente en una sección.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Sintaxis

```xml
<clear />
```

## <a name="attributes"></a>Atributos

Ninguna

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ------------|
| [**\<sectionName >** elemento](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Define los valores de las secciones de configuración personalizada que utilicen el <xref:System.Configuration.NameValueSectionHandler> y <xref:System.Configuration.DictionarySectionHandler> clases. |

## <a name="child-elements"></a>Elementos secundarios

Ninguna

## <a name="remarks"></a>Comentarios

Puede usar el  **\<borrar >** elemento para quitar toda la configuración de la aplicación que se han definido en un nivel superior de la jerarquía del archivo de configuración.

## <a name="example"></a>Ejemplo

Este ejemplo define un archivo de configuración del equipo y un archivo de configuración de aplicación y se muestra cómo usar el  **\<borrar >** elemento en un archivo de configuración de aplicación para borrar las secciones definidas anteriormente en el archivo de configuración del equipo.

El siguiente código de archivo de configuración del equipo declara la sección  **\<mySection >**:

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

El siguiente código de archivo de configuración de la aplicación quita todos los valores de  **\<mySection >**. La aplicación no puede recuperar la configuración que se han declarado en la en la  **\<mySection >** sección del archivo de configuración del equipo.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.

## <a name="see-also"></a>Vea también

- [Esquema de archivo de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
