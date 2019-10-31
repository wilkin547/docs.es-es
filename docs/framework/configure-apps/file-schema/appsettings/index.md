---
title: Esquema de configuración de aplicaciones
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b931b76aa09b3f62fbd799990975268af4f7293
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119218"
---
# <a name="app-settings-schema"></a>Esquema de configuración de aplicaciones

Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<add>** ](add-element-for-appsettings.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clear>** ](clear-element-for-appsettings.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<remove>** ](remove-element-for-appsettings.md)

| Elemento | Descripción |
| ------- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Contiene etiquetas **\<add>** , **\<clear>** y **\<remove>** para controlar la configuración de aplicaciones. Tiene un atributo opcional **file**. |
| [ **\<add>** ](add-element-for-appsettings.md) | Define un valor de configuración. Elemento secundario de **\<appSettings>** . Requiere atributos **key** y **value**. |
| [ **\<clear>** ](clear-element-for-appsettings.md) | Borra toda la configuración. Elemento secundario de **\<appSettings>** . No tiene atributos. |
| [ **\<remove>** ](remove-element-for-appsettings.md) | Quita un valor de configuración. Elemento secundario de **\<appSettings>** . Requiere un atributo **key**. |

## <a name="appsettings-element"></a>Elemento \<appSettings>

Este elemento contiene etiquetas **\<add>** , **\<clear>** y **\<remove>** para controlar la configuración de aplicaciones. Define un atributo opcional para **file**.

## <a name="add-element"></a>Elemento \<add>

Agrega una configuración de aplicación personalizada como par nombre-valor a la colección de configuraciones de la aplicación. Define atributos para **key** y **value**.

## <a name="clear-element"></a>Elemento \<clear>

Quita todas las referencias a la configuración de aplicación personalizada heredada y solo permite las referencias que se agregan mediante los elementos **\<add>** que siguen al elemento **\<clear>** . No define atributos.

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

- [Introducción a la configuración de la aplicación](../../../winforms/advanced/application-settings-overview.md)
- [Arquitectura de configuración de la aplicación](../../../winforms/advanced/application-settings-architecture.md)
