---
title: '&lt;sección&gt; elemento'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 295cb8ee77c3042dc5742fb23cf4bbcd085b4d36
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659220"
---
# <a name="section-element"></a>\<sección > elemento

Contiene una declaración de la sección de configuración.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<sección >**

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sección >**

## <a name="syntax"></a>Sintaxis

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>Atributos requeridos

|           | Descripción |
| --------- | ----------- |
| **name**  | Especifica el nombre de la sección de configuración. |
| **type**  | Especifica el nombre de la clase de controlador de sección de configuración que lee la sección del archivo de configuración. El valor de tipo tiene la sintaxis "fully-qualified-section-handler-class-name, nombre de ensamblado simple". El nombre de ensamblado simple es el nombre de archivo raíz sin el *.dll* la extensión de archivo. |

## <a name="optional-attributes"></a>Atributos opcionales

Los atributos siguientes son aplicables solo para las aplicaciones ASP.NET. El sistema de configuración omite estos atributos para otros tipos de aplicaciones.

|                     | Descripción |
| ------------------- | ----------- |
| **allowDefinition** | Especifica qué archivo de configuración se puede utilizar la sección. Utilice uno de los siguientes valores:<br><br>**Everywhere**<br>Permite la sección para usarse en cualquier archivo de configuración. Este es el valor predeterminado.<br>**MachineOnly**<br>Permite la sección que se usará solo en el archivo de configuración de máquina (*Machine.config*).<br>**MachineToApplication**<br>Permite la sección que se usará en el archivo de configuración del equipo o el archivo de configuración de la aplicación. |
| **allowLocation**   | Determina si se puede usar la sección dentro de la  **\<ubicación >** elemento. Utilice uno de los siguientes valores:<br><br>**true**<br>Permite la sección para su uso en el  **\<ubicación >** elemento. Este es el valor predeterminado.<br>**false**<br>No se permite la sección para su uso en el  **\<ubicación >** elemento. |

## <a name="parent-elements"></a>Elementos primarios

|     | Descripción |
| --- | ----------- |
| [**\<configSections>** Element](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Contiene las declaraciones de espacio de nombres y la sección de configuración. |
| [**\<sectionGroup >** elemento](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Define un espacio de nombres para las secciones de configuración. |

> [!NOTE]
> Un  **\<sección >** elemento es un elemento secundario de uno de ellos  **\<configSections >** o  **\<sectionGroup >** pero no ambos.

## <a name="child-elements"></a>Elementos secundarios

Ninguna

## <a name="remarks"></a>Comentarios

Declarar esencialmente una sección de configuración define un nuevo elemento para el archivo de configuración. El nuevo elemento contiene la configuración que una sección de configuración controlador (es decir, una clase que implementa el <xref:System.Configuration.IConfigurationSectionHandler> interfaz) lee. El controlador de sección que se utiliza para leer la configuración de dependen de los atributos y elementos secundarios de una sección que defina.

Declarar un controlador de la sección de configuración en el *Machine.config* archivo le permite usar la sección de configuración en cualquier archivo de configuración en ese equipo, a menos que el **allowDefinition**atributo especifique lo contrario.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo definir una sección de configuración y definir la configuración de esa sección:

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

Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.

## <a name="see-also"></a>Vea también

- [Esquema de archivo de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
