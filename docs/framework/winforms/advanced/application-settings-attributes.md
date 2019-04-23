---
title: Atributos de configuración de la aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: f945d8e6918c271eeb5fdf3cf9c357b1c2bbca66
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079648"
---
# <a name="application-settings-attributes"></a>Atributos de configuración de la aplicación
La arquitectura de configuración de la aplicación proporciona atributos que se pueden aplicar a la clase contenedora de configuración de aplicaciones o a sus propiedades individuales. Estos atributos se examinan en tiempo de ejecución por la infraestructura de configuración de aplicación, a menudo específicamente el proveedor de configuración para ajustar su funcionamiento a las necesidades definidas del contenedor personalizado.  
  
 En la tabla siguiente se enumera los atributos que se pueden aplicar a la clase contenedora de configuración de aplicación, las propiedades individuales de la clase o ambos. Por definición, un atributo de ámbito único,**UserScopedSettingAttribute** o **ApplicationScopedSettingAttribute**: se debe aplicar a cada propiedad de configuración.  
  
> [!NOTE]
>  Un proveedor de configuración personalizado, derivado de la <xref:System.Configuration.SettingsProvider> class, solo es necesario para que reconozca los tres atributos siguientes: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, y **DefaultSettingValueAttribute**.  
  
|Atributo|Destino|Descripción|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Ambos|Especifica el nombre corto del proveedor de configuración para usar para la persistencia.<br /><br /> Si no se proporciona este atributo, el proveedor predeterminado, <xref:System.Configuration.LocalFileSettingsProvider>, se da por hecho.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Ambos|Define una propiedad como una configuración de ámbito de usuario.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Ambos|Define una propiedad como configuración de la aplicación de ámbito de la aplicación.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Propiedad|Especifica una cadena que se pueda deserializar con el proveedor en el valor predeterminado codificado de forma rígida para esta propiedad.<br /><br /> El <xref:System.Configuration.LocalFileSettingsProvider> no requiere este atributo y reemplazará cualquier valor proporcionado por este atributo si no hay un valor ya guardado.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Propiedad|Proporciona la comprobación descriptiva para una configuración individual, utilizada principalmente por herramientas de tiempo de diseño y tiempo de ejecución.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Clase|Proporciona un nombre explícito para un grupo de configuración. Si falta este atributo, <xref:System.Configuration.ApplicationSettingsBase> utiliza el nombre de clase de contenedor.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Clase|Proporciona la prueba descriptiva para un grupo de configuraciones que se usa principalmente por herramientas en tiempo de diseño y tiempo de ejecución.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Ambos|Especifica cero o más servicios de facilidad de uso que se deben proporcionar al grupo de configuración o la propiedad. Los servicios disponibles se describen en la <xref:System.Configuration.SettingsManageability> enumeración.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Propiedad|Indica que una configuración pertenece a una categoría predefinida, especial, como una cadena de conexión que se sugiere un procesamiento especial por el proveedor de configuración. Las categorías predefinidas para este atributo se definen mediante la <xref:System.Configuration.SpecialSetting> enumeración.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Ambos|Especifica un mecanismo de serialización preferido para una propiedad o un grupo de configuración. Los mecanismos de serialización disponibles se definen mediante la <xref:System.Configuration.SettingsSerializeAs> enumeración.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Propiedad|Especifica que un proveedor de configuración debe deshabilitar la funcionalidad de actualización de todas las aplicaciones para la propiedad marcada.|  
  
 *Clase* indica que el atributo puede aplicarse únicamente a una clase contenedora de configuración de aplicación. *Propiedad* indica que el atributo puede ser aplicados únicas propiedades de configuración. *Ambos* indica que el atributo puede aplicarse en cualquier nivel.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- [Arquitectura de configuración de la aplicación](application-settings-architecture.md)
- [Cómo: Crear configuración de la aplicación](how-to-create-application-settings.md)
