---
title: "Propiedades de los controles de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], propiedades"
  - "controles personalizados [Windows Forms], información general sobre propiedades (utilizando el código)"
  - "propiedades [Windows Forms]"
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Propiedades de los controles de formularios Windows Forms
Un control de formularios Windows Forms hereda muchas propiedades de la clase base <xref:System.Windows.Forms.Control?displayProperty=fullName>.  Entre estas se incluyen propiedades como: <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A> y muchas otras.  Para obtener detalles sobre propiedades heredadas, vea <xref:System.Windows.Forms.Control?displayProperty=fullName>.  
  
 Se pueden reemplazar las propiedades heredadas en un control así como definir propiedades nuevas.  
  
## En esta sección  
 [Definir una propiedad](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 Muestra cómo implementar una propiedad para un control o componente personalizado y cómo integrar la propiedad en el entorno de diseño.  
  
 [Definir valores predeterminados con los métodos ShouldSerialize y Reset](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 Muestra cómo definir valores de propiedad predeterminados de un control o componente personalizado.  
  
 [Eventos de cambio de propiedades](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 Describe cómo habilitar notificaciones de cambio de propiedad cuando cambia un valor de propiedad.  
  
 [Cómo: Exponer propiedades de controles constituyentes](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 Muestra cómo exponer propiedades de controles constituyentes en un control compuesto personalizado.  
  
 [Implementación de métodos en controles personalizados](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 Describe cómo implementar métodos en controles y componentes personalizados.  
  
## Referencia  
 <xref:System.Windows.Forms.UserControl>  
 Documenta la clase base para implementar controles compuestos.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 Documenta el atributo que especifica el <xref:System.ComponentModel.TypeConverter> que se va a utilizar para un tipo de propiedad personalizado.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 Documenta el atributo que especifica el <xref:System.Drawing.Design.UITypeEditor> que se va a utilizar para una propiedad personalizada.  
  
## Secciones relacionadas  
 [Atributos en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 Describe los atributos que puede aplicar a propiedades u otros miembros de los controles y componentes personalizados.  
  
 [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md)  
 Ofrece una lista de los atributos de metadatos que se deben aplicar a los componentes y controles para que los diseñadores visuales los muestren correctamente en tiempo de diseño.  
  
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)  
 Describe cómo se implementan las clases, como los editores y diseñadores, que proporcionan compatibilidad en tiempo de diseño.