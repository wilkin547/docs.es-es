---
title: <section> elemento
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153740"
---
# <a name="section-element"></a>\<sección> elemento

Contiene una declaración de sección de configuración.

[**\<configuración>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sección>**

[**\<configuración>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sección>**

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
| **nombre**  | Especifica el nombre de la sección de configuración. |
| **tipo**  | Especifica el nombre de la clase de controlador de sección de configuración que lee la sección del archivo de configuración. El valor de tipo tiene la sintaxis "fully-qualified-section-handler-class-name, simple-assembly-name". El nombre de ensamblado simple es el nombre de archivo raíz sin la extensión de archivo *.dll.* |

## <a name="optional-attributes"></a>Atributos opcionales

Los siguientes atributos solo se aplican a las aplicaciones ASP.NET. El sistema de configuración omite estos atributos para otros tipos de aplicación.

|                     | Descripción |
| ------------------- | ----------- |
| **allowDefinition** | Especifica en qué archivo de configuración se puede utilizar la sección. Utilice uno de los valores siguientes:<br><br>**En todas partes**<br>Permite que la sección se utilice en cualquier archivo de configuración. Este es el valor predeterminado.<br>**MachineOnly**<br>Permite que la sección se utilice solo en el archivo de configuración de la máquina (*Machine.config*).<br>**MachineToApplication**<br>Permite utilizar la sección en el archivo de configuración de la máquina o en el archivo de configuración de la aplicación. |
| **allowLocation**   | Determina si la sección se ** \<** puede utilizar dentro de la ubicación>elemento. Utilice uno de los valores siguientes:<br><br>**true**<br>Permite que la sección ** \<** se utilice dentro de la ubicación>elemento. Este es el valor predeterminado.<br>**false**<br>No permite que la sección ** \<** se utilice dentro de la ubicación>elemento. |

## <a name="parent-elements"></a>Elementos primarios

|     | Descripción |
| --- | ----------- |
| [** \<configSections>** Elemento](configsections-element-for-configuration.md) | Contiene declaraciones de sección de configuración y espacio de nombres. |
| [** \<sectionGroup>** Elemento](sectiongroup-element-for-configsections.md) | Define un espacio de nombres para las secciones de configuración. |

> [!NOTE]
> Un ** \<elemento de>** de sección es un elemento secundario de ** \<configSections>** o ** \<sectionGroup>** pero no ambos.

## <a name="child-elements"></a>Elementos secundarios

None

## <a name="remarks"></a>Observaciones

Al declarar una sección de configuración, se define esencialmente un nuevo elemento para el archivo de configuración. El nuevo elemento contiene la configuración que lee un controlador <xref:System.Configuration.IConfigurationSectionHandler> de sección de configuración (es decir, una clase que implementa la interfaz). Los atributos y elementos secundarios de una sección que defina dependen del controlador de sección que utilice para leer la configuración.

Declarar un controlador de sección de configuración en el archivo *Machine.config* le permite usar la sección de configuración en cualquier archivo de configuración de la aplicación en ese equipo, a menos que el atributo **allowDefinition** especifique lo contrario.

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

Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema de archivo de configuración para .NET Framework](index.md)
