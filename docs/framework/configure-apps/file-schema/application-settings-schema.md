---
title: Esquema de configuración de la aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242834"
---
# <a name="application-settings-schema"></a>Esquema de configuración de la aplicación

La configuración de la aplicación permite que una aplicación de Windows Forms o ASP.NET almacene y recupere la configuración de ámbito de aplicación y de ámbito de usuario. En este contexto, una *configuración* es cualquier elemento de información que puede ser específico de la aplicación o específico del usuario actual, desde una cadena de conexión de base de datos hasta el tamaño de ventana predeterminado preferido del usuario.

De forma predeterminada, la configuración de <xref:System.Configuration.LocalFileSettingsProvider> la aplicación en una aplicación de windows Forms usa la clase, que usa el sistema de configuración de .NET para almacenar la configuración en un archivo de configuración XML. Para obtener más información acerca de los archivos utilizados por la configuración de la aplicación, consulte Arquitectura de [configuración](../../winforms/advanced/application-settings-architecture.md)de la aplicación .

La configuración de la aplicación define los siguientes elementos como parte de los archivos de configuración que utiliza.

| Elemento                    | Descripción                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | Contiene ** \<** todas las>etiquetas específicas de la aplicación.                         |
| **\<userSettings>**        | Contiene ** \<** todas las etiquetas de>de configuración específicas del usuario actual.                        |
| **\<ajuste de>**             | Define un valor de configuración. Hijo de ** \<applicationSettings>** o ** \<userSettings>**. |
| **\<>de valor**               | Define el valor de una configuración. Hijo ** \< **de la configuración>.                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings> elemento

Este elemento ** \<** contiene todas las etiquetas de configuración>que son específicas de una instancia de la aplicación en un equipo cliente. No define atributos.

## <a name="usersettings-element"></a>\<userSettings> elemento

Este elemento ** \<** contiene todas las etiquetas de>de configuración que son específicas del usuario que está utilizando actualmente la aplicación. No define atributos.

## <a name="setting-element"></a>\<ajuste> elemento

Este elemento define un valor. Tiene los siguientes atributos.

| Atributo        | Descripción |
| ---------------- | ----------- |
| **name**         | Necesario. El identificador único de la configuración. La configuración creada a través `ProjectName.Properties.Settings`de Visual Studio se guarda con el nombre . |
| **serializeAs** | Necesario. El formato que se va a utilizar para serializar el valor en texto. Los valores válidos son:<br><br>- `string`. El valor se serializa como <xref:System.ComponentModel.TypeConverter>una cadena mediante un archivo .<br>- `xml`. El valor se serializa mediante la serialización XML.<br>- `binary`. El valor se serializa como binario codificado por texto mediante la serialización binaria.<br />- `custom`. El proveedor de configuración tiene un conocimiento inherente de esta configuración y la serializa y deserializa. |

## <a name="value-element"></a>\<valor> elemento

Este elemento contiene el valor de un valor.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra un archivo de configuración de aplicación que define dos valores de ámbito de aplicación y dos valores de ámbito de usuario:

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

## <a name="see-also"></a>Consulte también

- [Introducción a la configuración de la aplicación](../../winforms/advanced/application-settings-overview.md)
- [Arquitectura de configuración de la aplicación](../../winforms/advanced/application-settings-architecture.md)
