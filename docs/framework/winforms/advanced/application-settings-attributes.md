---
title: "Application Settings Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "application settings [Windows Forms], attributes"
  - "attributes [Windows Forms], application settings"
  - "wrapper classes, application settings"
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Application Settings Attributes
La arquitectura de la configuración de la aplicación proporciona atributos que se pueden aplicar a la clase contenedora de la configuración de las aplicaciones o a sus propiedades individuales.  La arquitectura de la configuración de la aplicación examina estos atributos en tiempo de ejecución, a menudo específicamente el proveedor de configuración, para ajustar su funcionamiento a las necesidades definidas de la clase contenedora personalizada.  
  
 La tabla siguiente muestra los atributos que se pueden aplicar a la clase contenedora de la configuración de la aplicación, a las propiedades individuales de esta clase o a ambas.  Por definición, sólo un atributo de ámbito único, **UserScopedSettingAttribute** o **ApplicationScopedSettingAttribute**, se debe aplicar a cada una de las propiedades de configuración.  
  
> [!NOTE]
>  Un proveedor de configuración personalizado, derivado de la clase <xref:System.Configuration.SettingsProvider>, sólo se necesita para reconocer los tres atributos siguientes: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute** y **DefaultSettingValueAttribute**.  
  
|Atributo|Destino|Descripción|  
|--------------|-------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Ambos|Especifica el nombre corto del proveedor de configuración que se va a utilizar para persistencia.<br /><br /> Si no se proporciona este atributo, el proveedor predeterminado se supone que es <xref:System.Configuration.LocalFileSettingsProvider>.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Ambos|Define una propiedad como configuración de la aplicación de ámbito de usuario.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Ambos|Define una propiedad como configuración de la aplicación de ámbito de aplicación.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Propiedad.|Especifica una cadena que se puede deserializar por el proveedor en el valor predeterminado asignado para esta propiedad.<br /><br /> <xref:System.Configuration.LocalFileSettingsProvider> no necesita este atributo y reemplazará cualquier valor proporcionado por este atributo si ya existe un valor guardado.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Propiedad.|Proporciona la comprobación descriptiva para una configuración individual, utilizada principalmente por herramientas en tiempo de ejecución y en tiempo de diseño.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Clase|Proporciona un nombre explícito para un grupo de valores de configuración.  Si falta este atributo, <xref:System.Configuration.ApplicationSettingsBase> utiliza el nombre de la clase contenedora.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Clase|Proporciona la comprobación descriptiva para una configuración de grupo, utilizada principalmente por herramientas en tiempo de ejecución y en tiempo de diseño.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Ambos|Especifica cero o más servicios de facilidad de administración que se deberían proporcionar a la propiedad o al grupo de valores de configuración.  La enumeración <xref:System.Configuration.SettingsManageability> describe los servicios disponibles.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Propiedad.|Indica que una configuración pertenece a una categoría especial predefinida, como una cadena de conexión que sugiere que el proveedor de configuración aplique un procesamiento especial.  La enumeración <xref:System.Configuration.SpecialSetting> define las categorías predefinidas para este atributo.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Ambos|Especifica un mecanismo de serialización preferido para una propiedad o un grupo de valores de configuración.  La enumeración <xref:System.Configuration.SettingsSerializeAs> define los mecanismos de serialización disponibles.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Propiedad.|Especifica que un proveedor de valores de configuración debería deshabilitar la funcionalidad de actualización de la aplicación para la propiedad marcada.|  
  
 *Clase* indica que el atributo sólo se puede aplicar a una clase contenedora de la configuración de la aplicación.  *Propiedad* indica que el atributo se puede aplicar sólo a propiedades de configuración.  *Ambos* indica que el atributo se puede aplicar en cualquier nivel.  
  
## Vea también  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.SettingsProvider>   
 [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)   
 [How to: Create Application Settings](http://msdn.microsoft.com/es-es/53b3af80-1c02-4e35-99c6-787663148945)