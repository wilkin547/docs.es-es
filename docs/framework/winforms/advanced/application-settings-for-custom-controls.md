---
title: Configuración de la aplicación para controles personalizados
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: a4e477ce1c171b514482623595b2c5565564a2cb
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040457"
---
# <a name="application-settings-for-custom-controls"></a>Configuración de la aplicación para controles personalizados
Debe completar ciertas tareas para proporcionar a los controles personalizados la capacidad de conservar la configuración de la aplicación cuando los controles se hospedan en aplicaciones de terceros.

 La mayor parte de la documentación sobre la característica de configuración de la aplicación está escrita bajo el supuesto de que está creando una aplicación independiente. Sin embargo, si va a crear un control que otros desarrolladores van a hospedar en sus aplicaciones, debe realizar algunos pasos adicionales para que el control conserve su configuración correctamente.

## <a name="application-settings-and-custom-controls"></a>Configuración de la aplicación y controles personalizados
 Para que el control conserve correctamente su configuración, debe encapsular el proceso mediante la creación de su propia clase contenedora de configuración de <xref:System.Configuration.ApplicationSettingsBase>aplicaciones dedicadas, derivada de. Además, la clase de control principal debe implementar <xref:System.Configuration.IPersistComponentSettings>. La interfaz contiene varias propiedades, así como dos métodos, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> y <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>. Si agrega el control a un formulario mediante el **Diseñador de Windows Forms** en Visual Studio, Windows Forms llamará <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automáticamente al inicializarse el control; debe llamar a <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> sí mismo en el `Dispose` método del control.

 Además, debe implementar lo siguiente para que la configuración de la aplicación para controles personalizados funcione correctamente en entornos de tiempo de diseño como Visual Studio:

1. Una clase de configuración de aplicación personalizada con un constructor que <xref:System.ComponentModel.IComponent> toma como un parámetro único. Utilice esta clase para guardar y cargar todos los valores de configuración de la aplicación. Al crear una nueva instancia de esta clase, pase el control personalizado mediante el constructor.

2. Cree esta clase de configuración personalizada una vez creado el control y colocado en un formulario, como en el controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario.

 Para obtener instrucciones sobre cómo crear una clase de configuración [personalizada, consulte Cómo: Cree la configuración](how-to-create-application-settings.md)de la aplicación.

## <a name="settings-keys-and-shared-settings"></a>Claves de configuración y configuración compartida
 Algunos controles se pueden usar varias veces en el mismo formulario. La mayoría de las veces, querrá que estos controles conserven sus propias configuraciones individuales. Con la <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> propiedad en <xref:System.Configuration.IPersistComponentSettings>, puede proporcionar una cadena única que actúe para eliminar la ambigüedad de varias versiones de un control en un formulario.

 La manera más sencilla de implementar <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> es usar la <xref:System.Windows.Forms.Control.Name%2A> propiedad <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>del control para. Cuando se carga o se guarda la configuración del control, se pasa el valor <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> de a la <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> propiedad de la <xref:System.Configuration.ApplicationSettingsBase> clase. La configuración de la aplicación usa esta clave única cuando guarda la configuración del usuario en XML. En el ejemplo de código siguiente se `<userSettings>` muestra cómo una sección puede buscar una instancia de un control `CustomControl1` personalizado denominado que guarda un valor `Text` para su propiedad.

```xml
<userSettings>
    <CustomControl1>
        <setting name="Text" serializedAs="string">
            <value>Hello, World</value>
        </setting>
    </CustomControl1>
</userSettings>
```

 Las instancias de un control que no proporcionen un valor para <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> compartirán la misma configuración.

## <a name="see-also"></a>Vea también

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [Arquitectura de configuración de la aplicación](application-settings-architecture.md)
