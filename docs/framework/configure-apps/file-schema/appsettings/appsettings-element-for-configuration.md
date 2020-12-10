---
title: Elemento <appSettings> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: 66260d15768781b7fa3d9397b8e8a7d9ad68ab95
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009799"
---
# <a name="appsettings-element-for-configuration"></a>Elemento \<appSettings> para \<configuration>

Contiene la configuración de la aplicación personalizada. Se trata de una sección de configuración predefinida proporcionada por el .NET Framework.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<appSettings>**

## <a name="syntax"></a>Syntax

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **file**  | Atributo opcional.<br><br>Especifica una ruta de acceso relativa a un archivo externo que contiene opciones de configuración de la aplicación personalizadas. El archivo especificado contiene el mismo tipo de configuración que se especifica en los **\<add>** **\<remove>** elementos, y **\<clear>** y usa el mismo formato de par clave-valor que los elementos.<br><br>La ruta de acceso especificada es relativa al archivo de configuración principal. En el caso de una aplicación Windows Forms, esta es la carpeta binaria (por ejemplo, */bin/Debug*), no la ubicación del archivo de configuración de la aplicación. En el caso de las aplicaciones de formularios Web Forms, la ruta de acceso es relativa a la raíz de la aplicación, donde se encuentra el archivo de *web.config* .<br><br>El tiempo de ejecución omite el atributo si no se encuentra el archivo especificado. |

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [**\<configuration>** Elemento](../configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<add>**](add-element-for-appsettings.md) | Agrega una configuración de aplicación personalizada. |
| [**\<clear>**](clear-element-for-appsettings.md) | Borra todos los valores de configuración de la aplicación definidos previamente. |
| [**\<remove>**](remove-element-for-appsettings.md) | Quita una configuración de aplicación definida previamente. |

## <a name="remarks"></a>Comentarios

El **\<appSettings>** elemento almacena información de configuración de la aplicación personalizada, como cadenas de conexión de base de datos, rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación. Se tiene acceso a los pares clave-valor especificados en el **\<appSettings>** elemento en el código mediante la <xref:System.Configuration.ConfigurationSettings> clase.

Puede usar el atributo **File** en el **\<appSettings>** elemento de la *Web.config* y los archivos de configuración de la aplicación. Este atributo especifica un archivo de configuración que proporciona una configuración adicional o reemplaza la configuración especificada en el **\<appSettings>** elemento. El atributo de **archivo** se puede utilizar en escenarios de desarrollo del equipo de control de código fuente, como cuando un usuario desea invalidar la configuración del proyecto especificada en un archivo de configuración de la aplicación.

Los archivos de configuración especificados por el atributo **File** deben tener un nodo raíz de **\<appSettings>** en lugar de **\<configuration>** .

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

Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y *Web.config* archivos que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema del archivo de configuración para el .NET Framework](../index.md)
