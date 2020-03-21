---
title: Elemento <clear> para <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155432"
---
# <a name="clear-element-for-configsections"></a>\<claro> \<elemento para configSections>

Borra todas las secciones y grupos de secciones definidos anteriormente.

&nbsp; &nbsp; &nbsp; [** \<configuración>**](configuration-element.md) &nbsp; &nbsp; &nbsp;>**>>>>de>\<** [** \<**](configsections-element-for-configuration.md)

## <a name="syntax"></a>Sintaxis

```xml
<clear/>
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **nombre**  | Atributo necesario.<br><br>Especifica el nombre de la sección o grupo de secciones que se va a quitar. |

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [** \<configSections>** Elemento](configsections-element-for-configuration.md) | Contiene declaraciones de sección de configuración y espacio de nombres. |

## <a name="child-elements"></a>Elementos secundarios

None

## <a name="remarks"></a>Observaciones

El elemento ** \<>claro** quita todas las secciones y grupos de secciones de la aplicación que se definieron anteriormente en el archivo de configuración actual o en un nivel superior de la jerarquía de archivos de configuración.

## <a name="example"></a>Ejemplo

En este ejemplo se define un archivo de configuración ** \<** de máquina y un archivo de configuración de la aplicación y se muestra cómo utilizar el elemento>claro en un archivo de configuración de la aplicación para borrar las secciones definidas anteriormente en el archivo de configuración del equipo.

El siguiente código de archivo de configuración del equipo declara dos secciones, ** \<sampleSection>** y ** \<anotherSampleSection>**, que se leen antes del archivo de configuración de la aplicación:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

El siguiente código de archivo de configuración de la aplicación borra todas las secciones declaradas anteriormente. La aplicación no puede usar ni recuperar la configuración en ninguna de las secciones que se declararon en el archivo de configuración del equipo. Sin embargo, puede usar la configuración de ** \<otroSection>** porque viene después del ** \<elemento de>claro.**

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema de archivo de configuración para .NET Framework](index.md)
