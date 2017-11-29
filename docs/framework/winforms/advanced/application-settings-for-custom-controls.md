---
title: "Configuración de la aplicación para controles personalizados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f8292ac459a2943376229ef62466b0a772430dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="application-settings-for-custom-controls"></a>Configuración de la aplicación para controles personalizados
Debe finalizar determinadas tareas para proporcionar a los controles personalizados la capacidad para conservar la configuración de la aplicación cuando se hospedan los controles en aplicaciones de otros fabricantes.  
  
 La mayor parte de la documentación sobre la característica de configuración de la aplicación se escribe en la suposición de que está creando una aplicación independiente. Sin embargo, si está creando un control que otros desarrolladores van a hospedar en sus aplicaciones, debe realizar algunos pasos adicionales para el control conserve la configuración correctamente.  
  
## <a name="application-settings-and-custom-controls"></a>Configuración de la aplicación y controles personalizados  
 Para que el control conservar correctamente su configuración, debe encapsular el proceso mediante la creación de sus propias aplicaciones dedicadas clase contenedora de configuración, derivado de <xref:System.Configuration.ApplicationSettingsBase>. Además, la clase de control principal debe implementar la <xref:System.Configuration.IPersistComponentSettings>. La interfaz contiene varias propiedades, así como dos métodos, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> y <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>. Si agrega el control a un formulario mediante la **Diseñador de Windows Forms** en Visual Studio, formularios Windows Forms llamará <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automáticamente cuando se inicializa el control; debe llamar a <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> usted mismo en el `Dispose` método del control.  
  
 Además, debe implementar lo siguiente en orden para la configuración de la aplicación para controles personalizados para que funcione correctamente en entornos de tiempo de diseño como Visual Studio:  
  
1.  Una clase de configuración de aplicación personalizada con un constructor que toma un <xref:System.ComponentModel.IComponent> como un solo parámetro. Utilice esta clase para guardar y cargar toda la configuración de la aplicación. Cuando se crea una nueva instancia de esta clase, pase su control personalizado usando el constructor.  
  
2.  Crear esta clase de configuración personalizada después de haber creado y colocado en un formulario, como en el formulario el control <xref:System.Windows.Forms.Form.Load> controlador de eventos.  
  
 Para obtener instrucciones sobre cómo crear una clase de configuración personalizada, consulte [Cómo: crear una configuración de aplicación](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
## <a name="settings-keys-and-shared-settings"></a>Claves de configuración y la configuración compartida  
 Algunos controles pueden utilizarse varias veces dentro del mismo formulario. La mayoría de los casos, le interesará estos controles para conservar su propia configuración individual. Con el <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> propiedad <xref:System.Configuration.IPersistComponentSettings>, puede proporcionar una cadena única que actúa para eliminar la ambigüedad de varias versiones de un control en un formulario.  
  
 La manera más sencilla de implementar <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> consiste en utilizar el <xref:System.Windows.Forms.Control.Name%2A> propiedad del control para el <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>. Al cargar o guardar la configuración del control, pase el valor de <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> en el <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> propiedad de la <xref:System.Configuration.ApplicationSettingsBase> clase. Configuración de la aplicación utiliza esta clave única cuando conserva la configuración del usuario a XML. El siguiente ejemplo de código muestra cómo un `<userSettings>` sección podría tener el aspecto de una instancia de un control personalizado denominado `CustomControl1` que guarda una configuración para su `Text` propiedad.  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 Todas las instancias de un control que no proporciona un valor para <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> compartirán la misma configuración.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.IPersistComponentSettings>  
 [Arquitectura de configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)
