---
title: Elemento <appSettings> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155536"
---
# <a name="appsettings-element-for-configuration"></a>\<appSettings> \<elemento para la configuración>

Contiene la configuración de la aplicación personalizada. Esta es una sección de configuración predefinida proporcionada por .NET Framework.

configuración &nbsp; &nbsp;>[** \<**](../configuration-element.md) ** \<appSettings>**

## <a name="syntax"></a>Sintaxis

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **Archivo**  | Atributo opcional.<br><br>Especifica una ruta de acceso relativa a un archivo externo que contiene valores de configuración de aplicación personalizados. El archivo especificado contiene el mismo tipo de ** \< **configuración que se especifica en la>de agregar , ** \<quitar>** y ** \<borrar>** elementos y utiliza el mismo formato de par clave/valor que esos elementos.<br><br>La ruta especificada es relativa al archivo de configuración principal. Para una aplicación de windows Forms, esta es la carpeta binaria (como */bin/debug*), no la ubicación del archivo de configuración de la aplicación. Para las aplicaciones de formularios Web Forms, la ruta de acceso es relativa a la raíz de la aplicación, donde se encuentra el archivo *web.config.*<br><br>El tiempo de ejecución omite el atributo si no se puede encontrar el archivo especificado. |

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [** \<configuración>** Elemento](../configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<añadir>**](add-element-for-appsettings.md) | Agrega una configuración de aplicación personalizada. |
| [**\<>claro**](clear-element-for-appsettings.md) | Borra todos los valores de aplicación definidos anteriormente. |
| [**\<eliminar>**](remove-element-for-appsettings.md) | Quita una configuración de aplicación definida previamente. |

## <a name="remarks"></a>Observaciones

El elemento ** \<appSettings>** almacena información de configuración de la aplicación personalizada, como cadenas de conexión de base de datos, rutas de acceso de archivo, direcciones URL de servicio Web XML o cualquier otra información de configuración personalizada para una aplicación. Los pares clave/valor especificados en el <xref:System.Configuration.ConfigurationSettings> ** \<** elemento de>appSettings se tienen acceso en el código mediante la clase.

Puede usar el atributo **file** en el ** \<** elemento appSettings>de los archivos *web.config* y de configuración de la aplicación. Este atributo especifica un archivo de configuración que proporciona valores adicionales o reemplaza la configuración especificada en el ** \<elemento de>appSettings.** El atributo **de archivo** se puede usar en escenarios de desarrollo de equipo de control de código fuente, como cuando un usuario desea invalidar la configuración del proyecto especificada en un archivo de configuración de la aplicación.

Los archivos de configuración especificados por el atributo **file** deben tener un nodo raíz de ** \<appSettings>** en lugar de ** \<la configuración>**.

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

Este elemento se puede utilizar en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine.config*) y los archivos *Web.config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema de archivo de configuración para .NET Framework](../index.md)
