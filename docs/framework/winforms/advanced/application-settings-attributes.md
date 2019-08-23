---
title: Atributos de configuración de la aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: b38ed931cab3a333a56dd027d5843b1c8f00dcb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916678"
---
# <a name="application-settings-attributes"></a>Atributos de configuración de la aplicación
La arquitectura de configuración de la aplicación proporciona muchos atributos que se pueden aplicar a la clase contenedor de configuración de aplicaciones o a sus propiedades individuales. Estos atributos se examinan en tiempo de ejecución mediante la infraestructura de configuración de la aplicación, a menudo específicamente el proveedor de configuración, para adaptar su funcionamiento a las necesidades indicadas del contenedor personalizado.  
  
 En la tabla siguiente se enumeran los atributos que se pueden aplicar a la clase contenedora de configuración de la aplicación, a las propiedades individuales de esta clase o a ambas. Por definición, solo se debe aplicar un atributo de ámbito único (**UserScopedSettingAttribute** o **ApplicationScopedSettingAttribute**) a cada una de las propiedades de configuración.  
  
> [!NOTE]
> Un proveedor de configuración personalizado, derivado de <xref:System.Configuration.SettingsProvider> la clase, solo es necesario para reconocer los tres atributos siguientes: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**y **DefaultSettingValueAttribute**.  
  
|Atributo|Destino|DESCRIPCIÓN|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Ambos|Especifica el nombre corto del proveedor de configuración que se va a usar para la persistencia.<br /><br /> Si no se proporciona este atributo, se supone que es <xref:System.Configuration.LocalFileSettingsProvider>el proveedor predeterminado.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Ambos|Define una propiedad como una configuración de aplicación de ámbito de usuario.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Ambos|Define una propiedad como una configuración de aplicación con ámbito de aplicación.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Propiedad|Especifica una cadena que el proveedor puede deserializar en el valor predeterminado codificado de forma rígida para esta propiedad.<br /><br /> <xref:System.Configuration.LocalFileSettingsProvider> No requiere este atributo y reemplazará cualquier valor proporcionado por este atributo si ya existe un valor persistente.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Propiedad|Proporciona la prueba descriptiva para una configuración individual, utilizada principalmente por las herramientas en tiempo de ejecución y en tiempo de diseño.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Clase|Proporciona un nombre explícito para un grupo de configuración. Si falta este atributo, <xref:System.Configuration.ApplicationSettingsBase> utiliza el nombre de la clase contenedora.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Clase|Proporciona la prueba descriptiva para un grupo de configuración, que se usa principalmente en las herramientas en tiempo de ejecución y en tiempo de diseño.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Ambos|Especifica cero o más servicios de administración que se deben proporcionar al grupo de configuración o a la propiedad. Los servicios disponibles se describen en la <xref:System.Configuration.SettingsManageability> enumeración.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Propiedad|Indica que una configuración pertenece a una categoría especial predefinida, como una cadena de conexión, que sugiere un procesamiento especial por parte del proveedor de configuración. Las categorías predefinidas para este atributo se definen mediante <xref:System.Configuration.SpecialSetting> la enumeración.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Ambos|Especifica un mecanismo de serialización preferido para una propiedad o un grupo de configuración. Los mecanismos de serialización disponibles se definen mediante <xref:System.Configuration.SettingsSerializeAs> la enumeración.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Propiedad|Especifica que un proveedor de configuración debe deshabilitar toda la funcionalidad de actualización de la aplicación para la propiedad marcada.|  
  
 La *clase* indica que el atributo solo se puede aplicar a una clase contenedora de configuración de la aplicación. La *propiedad* indica que el atributo solo se puede aplicar a las propiedades de configuración. *Ambos* indica que el atributo se puede aplicar en cualquier nivel.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- [Arquitectura de configuración de la aplicación](application-settings-architecture.md)
- [Cómo: Crear configuración de aplicación](how-to-create-application-settings.md)
