---
title: Atributos de configuración de la aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: d52549546bc838d8d38da33b9bb9931488795064
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518354"
---
# <a name="application-settings-attributes"></a>Atributos de configuración de la aplicación
La arquitectura de configuración de la aplicación proporciona muchos de los atributos que se pueden aplicar a la clase de contenedor de configuración de aplicaciones o a sus propiedades individuales. Estos atributos se examinan en tiempo de ejecución por la infraestructura de configuración de aplicación, a menudo específicamente el proveedor de configuración para ajustar su funcionamiento a las necesidades definidas del contenedor personalizado.  
  
 En la tabla siguiente se enumera los atributos que se pueden aplicar a la clase de contenedor de configuración de aplicación, las propiedades individuales de la clase o ambos. Por definición, un atributo de ámbito único:**UserScopedSettingAttribute** o **ApplicationScopedSettingAttribute**: se debe aplicar a cada propiedad de configuración.  
  
> [!NOTE]
>  Un proveedor de configuración personalizado, derivado de la <xref:System.Configuration.SettingsProvider> clase, solo es necesaria para reconocer los tres atributos siguientes: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, y **DefaultSettingValueAttribute**.  
  
|Atributo|Destino|Descripción|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Ambos|Especifica el nombre corto del proveedor de configuración que se usará para la persistencia.<br /><br /> Si no se proporciona este atributo, el proveedor predeterminado, <xref:System.Configuration.LocalFileSettingsProvider>, se da por hecho.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Ambos|Define una propiedad como una configuración de aplicación de ámbito de usuario.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Ambos|Define una propiedad como una configuración de aplicación de ámbito de la aplicación.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Property|Especifica una cadena que se puede deserializar por el proveedor en el valor predeterminado codificado de forma rígida para esta propiedad.<br /><br /> El <xref:System.Configuration.LocalFileSettingsProvider> no requiere este atributo y reemplazará cualquier valor proporcionado por este atributo si hay un valor ya guardado.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Property|Proporciona la comprobación descriptiva para una configuración individual, utilizada principalmente por herramientas en tiempo de diseño y tiempo de ejecución.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Clase|Proporciona un nombre explícito para un grupo de configuración. Si este atributo no se encuentra, <xref:System.Configuration.ApplicationSettingsBase> utiliza el nombre de clase de contenedor.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Clase|Proporciona la comprobación descriptiva para un grupo de configuración, que se usa principalmente por herramientas en tiempo de diseño y tiempo de ejecución.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Ambos|Especifica cero o más servicios de facilidad de uso que se deben proporcionar para la propiedad o un grupo de configuración. Los servicios disponibles se describen en la <xref:System.Configuration.SettingsManageability> enumeración.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Property|Indica que una configuración pertenece a una categoría especial predefinida, como una cadena de conexión, que se sugiere un procesamiento especial por el proveedor de configuración. Las categorías predefinidas para este atributo se definen mediante el <xref:System.Configuration.SpecialSetting> enumeración.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Ambos|Especifica un mecanismo de serialización preferido para una propiedad o un grupo de configuración. Los mecanismos de serialización disponibles se definen mediante el <xref:System.Configuration.SettingsSerializeAs> enumeración.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Property|Especifica que un proveedor de configuración debe deshabilitar todas las funciones de actualización de aplicación para la propiedad marcada.|  
  
 *Clase* indica que el atributo se puede aplicar únicamente a una clase contenedora de configuración de aplicación. *Propiedad* indica que el atributo puede ser aplicada únicas propiedades de configuración. *Ambos* indica que el atributo se puede aplicar en cualquier nivel.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 [Arquitectura de configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [Cómo: Crear la configuración de la aplicación](http://msdn.microsoft.com/library/53b3af80-1c02-4e35-99c6-787663148945)
