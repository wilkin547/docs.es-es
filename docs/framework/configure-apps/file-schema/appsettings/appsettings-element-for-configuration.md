---
title: Elemento <appSettings> para <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: 47d7648aae08544890a4dd2e42cedbf68a8acc72
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214735"
---
# <a name="appsettings-element-for-configuration"></a>\<elemento > appSettings para la configuración de \<>

Contiene la configuración de la aplicación personalizada. Se trata de una sección de configuración predefinida proporcionada por el .NET Framework.

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp; **\<appSettings >**

## <a name="syntax"></a>Sintaxis

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **file**  | Atributo opcional.<br><br>Especifica una ruta de acceso relativa a un archivo externo que contiene opciones de configuración de la aplicación personalizadas. El archivo especificado contiene el mismo tipo de configuración que se especifica en el **\<agregar >** , **\<quitar >** y **\<borrar** elementos de > y usa el mismo formato de par clave-valor que los elementos.<br><br>La ruta de acceso especificada es relativa al archivo de configuración principal. En el caso de una aplicación Windows Forms, esta es la carpeta binaria (por ejemplo, */bin/Debug*), no la ubicación del archivo de configuración de la aplicación. En el caso de las aplicaciones de formularios Web Forms, la ruta de acceso es relativa a la raíz de la aplicación, donde se encuentra el archivo *Web. config* .<br><br>Tenga en cuenta que el tiempo de ejecución omite el atributo si no se puede encontrar el archivo especificado. |

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [ **> de configuración de\<** Element](../configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [ **\<add>** ](add-element-for-appsettings.md) | Agrega una configuración de aplicación personalizada. |
| [ **\<clear>** ](clear-element-for-appsettings.md) | Borra todos los valores de configuración de la aplicación definidos previamente. |
| [ **\<remove>** ](remove-element-for-appsettings.md) | Quita una configuración de aplicación definida previamente. |

## <a name="remarks"></a>Observaciones

El elemento **\<appSettings >** almacena información de configuración de la aplicación personalizada, como cadenas de conexión de base de datos, rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación. Se tiene acceso a los pares clave-valor especificados en el elemento **\<appSettings >** en el código mediante la clase <xref:System.Configuration.ConfigurationSettings>.

Puede usar el atributo **File** en el elemento **\<appSettings >** de los archivos *Web. config* y de configuración de la aplicación. Este atributo especifica un archivo de configuración que proporciona una configuración adicional o reemplaza la configuración especificada en el elemento **\<appSettings >** . El atributo de **archivo** se puede utilizar en escenarios de desarrollo del equipo de control de código fuente, como cuando un usuario desea invalidar la configuración del proyecto especificada en un archivo de configuración de la aplicación.

Los archivos de configuración especificados por el atributo **File** deben tener un nodo raíz de **\<appSettings >** en lugar de **\<> de configuración**.

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

Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Consulte también

- [Esquema del archivo de configuración para el .NET Framework](../index.md)
