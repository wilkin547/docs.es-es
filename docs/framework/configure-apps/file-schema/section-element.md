---
description: 'Más información acerca de: <section> elemento'
title: <section> elemento
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 7756f7ee3be2391a0d068708f3719083640b5595
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639944"
---
# <a name="section-element"></a>Elemento \<section>

Contiene una declaración de sección de configuración.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a>Sintaxis

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>Atributos necesarios

|           | Descripción |
| --------- | ----------- |
| **name**  | Especifica el nombre de la sección de configuración. |
| **type**  | Especifica el nombre de la clase de controlador de la sección de configuración que lee la sección del archivo de configuración. El valor de tipo tiene la sintaxis "Full-Qualified-Section-Handler-Class-Name, simple-Assembly-name". El nombre de ensamblado simple es el nombre de archivo raíz sin la extensión de archivo *. dll* . |

## <a name="optional-attributes"></a>Atributos opcionales

Los atributos siguientes solo son aplicables a las aplicaciones ASP.NET. El sistema de configuración omite estos atributos para otros tipos de aplicaciones.

|                     | Descripción |
| ------------------- | ----------- |
| **allowDefinition** | Especifica el archivo de configuración en el que se puede usar la sección. Utilice uno de los valores siguientes:<br><br>**En todas partes**<br>Permite que la sección se use en cualquier archivo de configuración. Este es el valor predeterminado.<br>**MachineOnly**<br>Permite que la sección se use solo en el archivo de configuración del equipo (*Machine.config*).<br>**MachineToApplication**<br>Permite usar la sección en el archivo de configuración del equipo o en el archivo de configuración de la aplicación. |
| **allowLocation**   | Determina si la sección se puede usar dentro del **\<location>** elemento. Utilice uno de los valores siguientes:<br><br>**true**<br>Permite que la sección se use dentro del **\<location>** elemento. Este es el valor predeterminado.<br>**false**<br>No permite el uso de la sección dentro del **\<location>** elemento. |

## <a name="parent-elements"></a>Elementos primarios

|     | Descripción |
| --- | ----------- |
| [**\<configSections>** Elemento](configsections-element-for-configuration.md) | Contiene la sección de configuración y las declaraciones de espacio de nombres. |
| [**\<sectionGroup>** Element](sectiongroup-element-for-configsections.md) | Define un espacio de nombres para las secciones de configuración. |

> [!NOTE]
> Un **\<section>** elemento es un elemento secundario de **\<configSections>** o, **\<sectionGroup>** pero no ambos.

## <a name="child-elements"></a>Elementos secundarios

Ninguno

## <a name="remarks"></a>Observaciones

Al declarar una sección de configuración, básicamente se define un nuevo elemento para el archivo de configuración. El nuevo elemento contiene la configuración que lee un controlador de sección de configuración (es decir, una clase que implementa la <xref:System.Configuration.IConfigurationSectionHandler> interfaz). Los atributos y elementos secundarios de una sección que se define dependen del controlador de la sección que se usa para leer la configuración.

Declarar un controlador de sección de configuración en el archivo *Machine.config* le permite usar la sección de configuración en cualquier archivo de configuración de la aplicación de ese equipo, a menos que el atributo **allowDefinition** especifique lo contrario.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo definir una sección de configuración y definir la configuración de esa sección:

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler"
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y *Web.config* archivos que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
