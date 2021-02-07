---
description: 'Más información sobre: esquema de configuración de aplicaciones'
title: Esquema de configuración de aplicaciones
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: a98a60b0470e0fa2c03313f25de9b310f5fce785
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699355"
---
# <a name="app-settings-schema"></a>Esquema de configuración de aplicaciones

Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| Elemento | Descripción |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | Contiene **\<add>** **\<clear>** etiquetas, y **\<remove>** para controlar la configuración de la aplicación. Tiene un atributo opcional **file**. |
| [**\<add>**](add-element-for-appsettings.md) | Define un valor de configuración. Elemento secundario de **\<appSettings>** . Requiere atributos **key** y **value**. |
| [**\<clear>**](clear-element-for-appsettings.md) | Borra toda la configuración. Elemento secundario de **\<appSettings>** . No tiene atributos. |
| [**\<remove>**](remove-element-for-appsettings.md) | Quita un valor de configuración. Elemento secundario de **\<appSettings>** . Requiere un atributo **key**. |

## <a name="appsettings-element"></a>Elemento \<appSettings>

Este elemento contiene **\<add>** **\<clear>** etiquetas, y **\<remove>** para controlar la configuración de la aplicación. Define un atributo opcional para **file**.

## <a name="add-element"></a>Elemento \<add>

Agrega una configuración de aplicación personalizada como par nombre-valor a la colección de configuraciones de la aplicación. Define atributos para **key** y **value**.

## <a name="clear-element"></a>Elemento \<clear>

Quita todas las referencias a la configuración de la aplicación personalizada heredada y solo permite las referencias que se agregan a los **\<add>** elementos que siguen al **\<clear>** elemento. No define atributos.

## <a name="remove-element"></a>Elemento \<remove>

Quita de la colección de configuraciones de la aplicación una referencia a una configuración de aplicación personalizada heredada. Define un atributo para **key**.

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

## <a name="see-also"></a>Vea también

- [Introducción a la configuración de la aplicación](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [Arquitectura de configuración de la aplicación](/dotnet/desktop/winforms/advanced/application-settings-architecture)
