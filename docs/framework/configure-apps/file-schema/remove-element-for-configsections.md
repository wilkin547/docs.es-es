---
title: Elemento <remove> para <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154535"
---
# <a name="remove-element-for-configsections"></a>\<eliminar> \<elemento para configSections>

Quita una sección o un grupo de secciones predefinidos.

[**\<configuración>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<eliminar>**

## <a name="syntax"></a>Sintaxis

```xml
<remove name="section name or section group name" />
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

Puede usar ** \<** el elemento remove>para quitar secciones y grupos de secciones de la aplicación que se definieron en un nivel superior en la jerarquía de archivos de configuración.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente ** \<** se muestra cómo utilizar el elemento remove>en un archivo de configuración de aplicación para quitar una sección definida previamente en el archivo de configuración del equipo.

El siguiente código de archivo de configuración del equipo declara la sección ** \<sampleSection>: **

```xml
<!-- Machine.config file -->
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

El siguiente código de archivo ** \<** de configuración de la aplicación quita la sección sampleSection>. Después de la eliminación, la aplicación no puede recuperar la configuración de ** \<sampleSection>**.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema de archivo de configuración para .NET Framework](index.md)
