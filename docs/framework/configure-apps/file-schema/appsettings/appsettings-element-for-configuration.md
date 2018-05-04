---
title: '&lt;appSettings&gt; , elemento de &lt;configuración&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d17400536b911ce0be4d2bf105b0b4d99d0916df
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="appsettings-element-for-configuration"></a>\<appSettings > (elemento) para \<configuración >

Contiene la configuración de aplicación personalizada. Se trata de una sección de configuración predefinidos proporcionada por .NET Framework.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<appSettings >**

## <a name="syntax"></a>Sintaxis

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **file**  | Atributo opcional.<br><br>Especifica una ruta de acceso relativa a un archivo externo que contiene valores de configuración de aplicación personalizada. El archivo especificado contiene el mismo tipo de configuración que se especifican en el  **\<Agregar >**,  **\<quitar >**, y  **\<borrar >** elementos y se utiliza el mismo par de clave/valor el formato de los elementos.<br><br>La ruta de acceso especificada es relativa al archivo de configuración principal. Para una aplicación de formularios Windows Forms, ésta es la carpeta binaria (como */bin/debug*), no la ubicación del archivo de configuración de aplicación. Para aplicaciones de formularios Web Forms, la ruta de acceso es relativa a la raíz de la aplicación, donde el *web.config* archivo se encuentra.<br><br>Tenga en cuenta que el tiempo de ejecución omite el atributo si no se puede encontrar el archivo especificado. |

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [**\<Configuración >** elemento](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | Agrega una configuración de aplicación personalizada. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | Borra toda la configuración de aplicación definida previamente. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | Quita una configuración de aplicación definida previamente. |

## <a name="remarks"></a>Comentarios

El  **\<appSettings >** elemento almacena información de configuración de aplicación personalizada, como las cadenas de conexión de base de datos, las rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para un aplicación. Los pares de clave/valor especificados en la  **\<appSettings >** elemento se obtiene acceso en el código mediante la <xref:System.Configuration.ConfigurationSettings> clase.

Puede usar el **archivo** de atributo en el  **\<appSettings >** elemento de la *Web.config* y archivos de configuración de aplicación. Este atributo especifica un archivo de configuración que proporciona una configuración adicional o reemplaza la configuración especificada en el  **\<appSettings >** elemento. El **archivo** atributo se puede usar en escenarios de desarrollo en equipo de control de código fuente, como cuando un usuario desea invalidar la configuración de proyecto especificada en un archivo de configuración de aplicación.

Archivos de configuración especificados por el **archivo** atributo debe tener un nodo raíz de  **\<appSettings >** en lugar de  **\<configuración >**.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra un archivo de configuración de la aplicación externo (*custom.config*) que define una configuración de aplicación personalizada:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que usa la configuración del archivo de configuración externo y establece su propia configuración de la aplicación:

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración de máquina (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.

## <a name="see-also"></a>Vea también

[Esquema de archivos de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
