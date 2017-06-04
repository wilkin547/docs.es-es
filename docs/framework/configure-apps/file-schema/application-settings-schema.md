---
title: "Esquema de la configuraci&#243;n de la aplicaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "configuración de la aplicación, esquema [formularios Windows Forms]"
  - "esquema de configuración [.NET Framework], configuración de la aplicación"
  - "esquema de configuración de la aplicación"
  - "Windows Forms, esquema de configuración de la aplicación"
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
caps.latest.revision: 3
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 3
---
# Esquema de la configuraci&#243;n de la aplicaci&#243;n
La configuración de la aplicación permite que una aplicación de Windows Forms o ASP.NET almacene y recupere la configuración de ámbito de aplicación y la configuración de ámbito de usuario.  En este contexto, un "valor de configuración" es un fragmento de información que puede ser específico de la aplicación o específico del usuario actual, desde una cadena de conexión a base de datos hasta el tamaño de ventana preferido del usuario.  
  
 De forma predeterminada, la configuración de una aplicación de Windows Forms utiliza <xref:System.Configuration.LocalFileSettingsProvider>, que utiliza el sistema de configuración de .NET para almacenar la configuración en un archivo de configuración XML.  Para obtener más información sobre los archivos utilizados por la configuración de la aplicación, vea [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md).  
  
 La configuración de la aplicación define los elementos que se muestran a continuación como la parte de los archivos de configuración que utiliza.  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|Elemento `<applicationSettings>`|Contiene todas las etiquetas `<setting>` específicas de la aplicación.|  
|Elemento `<userSettings>`|Contiene todas las etiquetas `<setting>` específicas del usuario actual.|  
|Elemento `<setting>`|Define un valor de configuración.  Elemento secundario de `<applicationSettings>` o `<userSettings>`.|  
|Elemento `<value>`|Define el valor de una configuración.  Elemento secundario de `<setting>`.|  
  
## \<elemento\> de los applicationSettings  
 Este elemento contiene todas \<las etiquetas\> de valores específicos de una instancia de la aplicación en un equipo cliente.  No define ningún atributo.  
  
## \<elemento\> de los userSettings  
 Este elemento contiene todas las \<etiquetas\> de valores que son específicas del usuario que está utilizando actualmente la aplicación.  No define ningún atributo.  
  
## \<elemento del valor\>  
 Este elemento define un valor de configuración.  Tiene los atributos siguientes.  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`name`|Obligatorio.  Id. único del valor de configuración.  Las configuraciones creadas a través de Visual Studio se guardan con el nombre de `ProjectName``.Properties .Settings`.|  
|`serializedAs`|Obligatorio.  Formato que se va a utilizar para serializar el valor en texto.  Los valores válidos son:<br /><br /> -   `string`.  El valor se serializa como una cadena utilizando <xref:System.ComponentModel.TypeConverter>.<br />-   `xml`.  El valor se serializa utilizando la serialización XML.<br />-   `binary`.  El valor se serializa como binario codificado en texto utilizando la serialización binaria.<br />-   `custom`.  El proveedor de configuración posee un conocimiento inherente de esta configuración, y la serializará y deserializará.<br />-   Para utilizar la serialización binaria o personalizada, deberá definir su propia clase de configuración y utilizar <xref:System.Configuration.SettingsSerializeAsAttribute> para especificar la serialización binaria o personalizada.|  
  
## \<elemento del valor\>  
 Este elemento contiene el valor de una configuración.  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra un archivo de configuración de la aplicación que define dos configuraciones de ámbito de aplicación y dos configuraciones de ámbito de usuario.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <configSections>  
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >  
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </sectionGroup>  
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >  
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
  
## Vea también  
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)