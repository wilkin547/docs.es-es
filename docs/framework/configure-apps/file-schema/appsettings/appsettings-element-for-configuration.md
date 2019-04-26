---
title: Elemento <appSettings> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: dcdf8d0f11ae65353da08bba1f8d2fe5ab415c6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705563"
---
# <a name="appsettings-element-for-configuration"></a>\<appSettings > (elemento) para \<configuración >

Contiene la configuración de aplicación personalizada. Se trata de una sección de configuración predefinidos proporcionada por .NET Framework.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<appSettings>**

## <a name="syntax"></a>Sintaxis

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **file**  | Atributo opcional.<br><br>Especifica una ruta de acceso relativa a un archivo externo que contiene los valores de configuración de aplicación personalizada. El archivo especificado contiene el mismo tipo de configuración que se especifican en el  **\<Agregar >**,  **\<quitar >**, y  **\<borrar >** elementos y utiliza el mismo par de clave/valor de formato que dichos elementos.<br><br>La ruta de acceso especificada es relativa al archivo de configuración principal. Para una aplicación Windows Forms, esta es la carpeta binaria (como */bin/debug*), no la ubicación del archivo de configuración de aplicación. Las aplicaciones de formularios Web Forms, la ruta de acceso es relativa a la raíz de la aplicación, donde el *web.config* archivo se encuentra.<br><br>Tenga en cuenta que el tiempo de ejecución omite el atributo si no se puede encontrar el archivo especificado. |

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [**\<Configuración >** elemento](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | Agrega una configuración de aplicación personalizada. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | Borra todas las configuraciones de aplicación definido anteriormente. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | Quita una configuración de aplicación definido anteriormente. |

## <a name="remarks"></a>Comentarios

El  **\<appSettings >** elemento almacena información de configuración de aplicación personalizada, como las cadenas de conexión de base de datos, las rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para un aplicación. Los pares clave/valor especificados en el  **\<appSettings >** elemento son accesibles desde código mediante la <xref:System.Configuration.ConfigurationSettings> clase.

Puede usar el **archivo** atributo en el  **\<appSettings >** elemento de la *Web.config* y archivos de configuración de aplicación. Este atributo especifica un archivo de configuración que proporciona una configuración adicional o reemplaza la configuración especificada en el  **\<appSettings >** elemento. El **archivo** atributo se puede usar en escenarios de desarrollo en equipo de control de origen, como cuando un usuario desea invalidar la configuración de proyecto especificada en un archivo de configuración de la aplicación.

Los archivos de configuración especificados por el **archivo** atributo debe tener un nodo raíz de  **\<appSettings >** lugar  **\<configuración >**.

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

Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.

## <a name="see-also"></a>Vea también

- [Esquema de archivo de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
