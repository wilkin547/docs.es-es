---
title: "Application Settings for Custom Controls | Microsoft Docs"
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
  - "custom controls [Windows Forms], application settings"
  - "application settings [Windows Forms], custom controls"
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Application Settings for Custom Controls
Debe finalizar determinadas tareas para dar a los controles personalizados la capacidad de conservar la configuración cuando se hospedan en aplicaciones de terceros.  
  
 La mayoría de la documentación sobre la característica Configuración de la aplicación se escribe suponiendo que se está creando una aplicación independiente.  Sin embargo, si está creando un control que otros desarrolladores van a hospedar en sus aplicaciones, entonces necesita realizar algunos pasos adicionales para que el control conserve la configuración correctamente.  
  
## Configuración de la aplicación y controles personalizados  
 Para que el control conserve la configuración correctamente, debe encapsular el proceso creando su propia clase contenedora específica de los valores de configuración de la aplicación, derivada de <xref:System.Configuration.ApplicationSettingsBase>.  Además, la clase de control principal debe implementar la interfaz <xref:System.Configuration.IPersistComponentSettings>.  La interfaz contiene varias propiedades así como dos métodos, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> y <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.  Si se agrega el control a un formulario utilizando el **Diseñador de Windows Forms** de Visual Studio, formularios Windows Forms llamará automáticamente a <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> cuando se inicializa el control, pero hay que llamar a <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> en el método  `Dispose` del control.  
  
 Además, debe implementar lo siguiente para que la configuración de la aplicación para los controles personalizados funcione correctamente en tiempo de diseño en entornos como Visual Studio:  
  
1.  Una clase de configuración de aplicación personalizada con un constructor que recibe un <xref:System.ComponentModel.IComponent> como parámetro único.  En esta clase, guarde y cargue toda la configuración de la aplicación.  Cuando cree una instancia nueva de esta clase, pase su control personalizado usando el constructor.  
  
2.  Cree esta clase de configuración personalizada después de crear y colocar el control en un formulario, por ejemplo, en el controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario.  
  
 Para obtener instrucciones acerca de cómo crear una clase de configuración personalizada, vea [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
## Claves de configuración y valores de configuración compartidos  
 Algunos controles se pueden utilizar varias veces dentro del mismo formulario.  En la mayoría de las ocasiones, deseará que estos controles conserven su propia configuración individual.  Con la propiedad <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> de <xref:System.Configuration.IPersistComponentSettings> puede proporcionar una cadena única que se utiliza para eliminar la ambigüedad entre varias versiones de un control en un formulario.  
  
 La manera más simple de implementar <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> es utilizar la propiedad <xref:System.Windows.Forms.Control.Name%2A> del control para <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.  Cuando carga o guarda la configuración de un control, pasa el valor de <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> a la propiedad <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> de la clase <xref:System.Configuration.ApplicationSettingsBase>.  La Configuración de la aplicación utiliza esta clave única cuando conserva los valores de configuración del usuario en XML.  El ejemplo de código siguiente muestra cómo una sección `<userSettings>` puede buscar una instancia de un control personalizado denominado `CustomControl1` que guarda una configuración para su propiedad `Text` .  
  
```  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 Cualquier instancia de un control que no proporciona un valor para <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> compartirá la misma configuración.  
  
## Vea también  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.IPersistComponentSettings>   
 [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)