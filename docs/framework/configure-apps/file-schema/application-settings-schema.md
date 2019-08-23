---
title: Esquema de configuración de la aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 89a08434332b0242fe57e9dcaa3b3ebcc5692d06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927760"
---
# <a name="application-settings-schema"></a>Esquema de configuración de la aplicación

La configuración de la aplicación permite que una aplicación Windows Forms o ASP.NET almacene y recupere la configuración del ámbito de la aplicación y del ámbito del usuario. En este contexto, un *valor* es cualquier parte de la información que pueda ser específica de la aplicación o específica del usuario actual, desde una cadena de conexión de base de datos hasta el tamaño de ventana predeterminado preferido del usuario.

De forma predeterminada, la configuración de la aplicación en una <xref:System.Configuration.LocalFileSettingsProvider> aplicación Windows Forms usa la clase, que utiliza el sistema de configuración de .net para almacenar la configuración en un archivo de configuración XML. Para obtener más información acerca de los archivos que usa la configuración de la aplicación, consulte [arquitectura de configuración](../../winforms/advanced/application-settings-architecture.md)de la aplicación.

La configuración de la aplicación define los elementos siguientes como parte de los archivos de configuración que usa.

| Elemento                    | DESCRIPCIÓN                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | Contiene toda  **\<la configuración >** etiquetas específicas de la aplicación.                         |
| **\<userSettings>**        | Contiene toda  **\<la configuración >** etiquetas específicas del usuario actual.                        |
| **\<setting>**             | Define un valor de configuración. Elemento secundario de la  **\<> ApplicationSettings** o  **\<de la > UserSettings**. |
| **\<value>**               | Define el valor de una configuración. Secundario de  **\<la configuración >** .                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings (elemento >)

Este elemento contiene toda  **\<la configuración >** etiquetas que son específicas de una instancia de la aplicación en un equipo cliente. No define atributos.

## <a name="usersettings-element"></a>\<elemento > userSettings

Este elemento contiene toda  **\<la configuración >** etiquetas que son específicas del usuario que está utilizando actualmente la aplicación. No define atributos.

## <a name="setting-element"></a>\<establecer > elemento

Este elemento define un valor de configuración. Tiene los siguientes atributos.

| Atributo        | DESCRIPCIÓN |
| ---------------- | ----------- |
| **name**         | Necesario. IDENTIFICADOR único de la configuración. La configuración creada a través de Visual Studio se guarda `ProjectName.Properties.Settings`con el nombre. |
| **serializedAs** | Necesario. Formato que se va a usar para serializar el valor en el texto. Los valores válidos son:<br><br>- `string`. El valor se serializa como una cadena mediante <xref:System.ComponentModel.TypeConverter>.<br>- `xml`. El valor se serializa mediante la serialización XML.<br>- `binary`. El valor se serializa como binario codificado por texto mediante la serialización binaria.<br />- `custom`. El proveedor de configuración tiene un conocimiento inherente de esta configuración y serializa y deserializa. |

## <a name="value-element"></a>\<elemento > de valor

Este elemento contiene el valor de un parámetro.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra un archivo de configuración de la aplicación que define dos valores de ámbito de aplicación y dos valores de ámbito de usuario:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Introducción a la configuración de la aplicación](../../winforms/advanced/application-settings-overview.md)
- [Arquitectura de configuración de la aplicación](../../winforms/advanced/application-settings-architecture.md)
