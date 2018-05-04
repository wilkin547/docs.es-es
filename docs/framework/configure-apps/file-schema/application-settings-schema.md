---
title: Esquema de la configuración de aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7af6342e9c05fc4e6c1bf4daac59db14ccdf22c7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="application-settings-schema"></a>Esquema de la configuración de aplicación

Configuración de la aplicación que una aplicación de formularios Windows Forms o ASP.NET almacenar y recuperar la configuración de ámbito de la aplicación y ámbito de usuario. En este contexto, un *configuración* es cualquier fragmento de información que puede ser específicos de la aplicación o específica del usuario actual, cualquier cosa, desde una cadena de conexión de base de datos al usuario preferido del tamaño de ventana predeterminado.

De forma predeterminada, usa la configuración de la aplicación en una aplicación de formularios Windows Forms el <xref:System.Configuration.LocalFileSettingsProvider> (clase), que utiliza el sistema de configuración de .NET para almacenar la configuración en un archivo de configuración XML. Para obtener más información acerca de los archivos utilizados por la configuración de la aplicación, consulte [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).

Configuración de la aplicación define los elementos siguientes como parte de los archivos de configuración que se utiliza.

| Elemento                    | Descripción                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings >** | Todos los contiene  **\<configuración >** etiquetas específicas para la aplicación.                         |
| **\<userSettings >**        | Todos los contiene  **\<configuración >** etiquetas específicas para el usuario actual.                        |
| **\<Configuración >**             | Define un valor de configuración. Elemento secundario del  **\<applicationSettings >** o  **\<userSettings >**. |
| **\<value>**               | Define un valor de configuración. Elemento secundario de  **\<configuración >**.                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings > elemento

Este elemento contiene todas las  **\<configuración >** etiquetas que son específicas de una instancia de la aplicación en un equipo cliente. No define atributos.

## <a name="usersettings-element"></a>\<userSettings > elemento

Este elemento contiene todas las  **\<configuración >** etiquetas que son específicas del usuario que está utilizando actualmente la aplicación. No define atributos.

## <a name="setting-element"></a>\<Configuración > elemento

Este elemento define un valor. Tiene los siguientes atributos.

| Atributo        | Descripción |
| ---------------- | ----------- |
| **name**         | Requerido. El identificador único de la configuración. La configuración creada con Visual Studio se guarda con el nombre `ProjectName.Properties.Settings`. |
| **serializedAs** | Requerido. Formato que se va a usar para serializar el valor en texto. Los valores válidos son:<br><br>- `string`. El valor se serializa como una cadena con un <xref:System.ComponentModel.TypeConverter>.<br>- `xml`. El valor se serializa utilizando la serialización XML.<br>- `binary`. El valor se serializa como binario codificado en texto utilizando la serialización binaria.<br />- `custom`. El proveedor de configuración tiene un conocimiento inherente de esta configuración y serializa y deserializa lo. |

## <a name="value-element"></a>\<valor > elemento

Este elemento contiene el valor de una configuración.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra un archivo de configuración de aplicación que define dos configuraciones de ámbito de la aplicación y dos configuraciones de ámbito de usuario:

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

[Introducción a la configuración de la aplicación](~/docs/framework/winforms/advanced/application-settings-overview.md)   
[Arquitectura de configuración de la aplicación](~/docs/framework/winforms/advanced/application-settings-architecture.md)
