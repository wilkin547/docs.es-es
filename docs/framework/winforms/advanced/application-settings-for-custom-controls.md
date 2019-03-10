---
title: Configuración de la aplicación para controles personalizados
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: d12caf9ed2cb80d837080badab436b2e9b0b3728
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714351"
---
# <a name="application-settings-for-custom-controls"></a>Configuración de la aplicación para controles personalizados
Debe finalizar determinadas tareas para proporcionar a los controles personalizados la capacidad de conservar la configuración de la aplicación cuando los controles se alojan en aplicaciones de terceros.  
  
 La mayoría de la documentación sobre la característica de configuración de la aplicación se escribe con la asunción de que está creando una aplicación independiente. Sin embargo, si va a crear un control que se va a hospedar otros desarrolladores en sus aplicaciones, deberá realizar algunos pasos adicionales para el control conserve la configuración correctamente.  
  
## <a name="application-settings-and-custom-controls"></a>Configuración de la aplicación y los controles personalizados  
 Para que el control conservar correctamente su configuración, debe encapsular el proceso mediante la creación de sus propias aplicaciones dedicadas clase contenedora de configuración, derivado de <xref:System.Configuration.ApplicationSettingsBase>. Además, la clase de control principal debe implementar la <xref:System.Configuration.IPersistComponentSettings>. La interfaz contiene varias propiedades, así como dos métodos, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> y <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>. Si agrega el control a un formulario mediante el **Diseñador de Windows Forms** en Visual Studio, Windows Forms llamará <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automáticamente cuando se inicializa el control; debe llamar a <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> usted mismo en el `Dispose` método del control.  
  
 Además, debe implementar lo siguiente en orden para la configuración de la aplicación para controles personalizados para que funcione correctamente en entornos de tiempo de diseño como Visual Studio:  
  
1.  Una clase de configuración de aplicación personalizada con un constructor que toma un <xref:System.ComponentModel.IComponent> como un único parámetro. Utilice esta clase para guardar y cargar toda la configuración de la aplicación. Cuando se crea una nueva instancia de esta clase, pase un control personalizado utilizando el constructor.  
  
2.  Creación de esta clase de configuración personalizada después de haber creado el control y colocado en un formulario, como en el formulario <xref:System.Windows.Forms.Form.Load> controlador de eventos.  
  
 Para obtener instrucciones sobre cómo crear una clase de configuración personalizada, vea [Cómo: Crear configuración de la aplicación](how-to-create-application-settings.md).  
  
## <a name="settings-keys-and-shared-settings"></a>Claves de configuración y la configuración compartida  
 Algunos controles pueden utilizarse varias veces dentro del mismo formulario. La mayoría de los casos, le interesará estos controles para conservar su propia configuración individual. Con el <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> propiedad <xref:System.Configuration.IPersistComponentSettings>, puede proporcionar una cadena única que actúa para eliminar la ambigüedad de varias versiones de un control en un formulario.  
  
 La manera más sencilla de implementar <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> consiste en usar el <xref:System.Windows.Forms.Control.Name%2A> propiedad del control para el <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>. Al cargar o guardar la configuración del control, pase el valor de <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> en el <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> propiedad de la <xref:System.Configuration.ApplicationSettingsBase> clase. Configuración de la aplicación utiliza esta clave única cuando conserva la configuración del usuario a XML. El siguiente ejemplo de código muestra cómo un `<userSettings>` sección puede buscar una instancia de un control personalizado denominado `CustomControl1` que guarda una configuración para su `Text` propiedad.  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 Todas las instancias de un control que no se proporciona un valor para <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> compartirán la misma configuración.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [Arquitectura de configuración de la aplicación](application-settings-architecture.md)
