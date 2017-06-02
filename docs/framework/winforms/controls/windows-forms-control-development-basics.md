---
title: "Fundamentos de desarrollo de controles de formularios Windows Forms | Microsoft Docs"
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
  - "controles [Windows Forms], crear"
  - "controles personalizados [Windows Forms], derivación de tipos"
  - "conceptos de programación, controles de Windows Forms"
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Fundamentos de desarrollo de controles de formularios Windows Forms
Un control de formularios Windows Forms es una clase que deriva directa o indirectamente de <xref:System.Windows.Forms.Control?displayProperty=fullName>.  En la siguiente lista se describen escenarios comunes para el desarrollo de controles de formularios Windows Forms.  
  
-   Combinación de controles existentes para crear un control compuesto.  
  
     Los controles compuestos encapsulan una interfaz de usuario que se puede reutilizar como control.  Un ejemplo de control compuesto es un control formado por un cuadro de texto y un botón Restablecer.  Los diseñadores visuales ofrecen grandes posibilidades para crear controles compuestos.  Para crear un control compuesto, derive de la clase <xref:System.Windows.Forms.UserControl?displayProperty=fullName>.  La clase base <xref:System.Windows.Forms.UserControl> proporciona enrutamiento de teclado a los controles secundarios permitiéndoles trabajar como grupo.  Para obtener más información, vea [Desarrollar un control de formularios Windows Forms compuesto](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).  
  
-   Ampliación de un control existente para personalizarlo o agregarle funcionalidad.  
  
     Los botones a los que no se puede modificar el color y aquellos que tienen una propiedad adicional que controla el número de veces que se hace clic en el botón, son ejemplos de controles ampliados.  Se puede personalizar cualquier control de formularios Windows Forms derivando del mismo y reemplazando o agregando propiedades, métodos y eventos.  
  
-   Creación de un control que no combina ni amplía un control existente.  
  
     En este escenario, derive el control de la clase base <xref:System.Windows.Forms.Control>.  Las propiedades, métodos y eventos de la clase base se pueden agregar y reemplazar.  Para obtener una introducción, vea [Cómo: Desarrollar un control de formularios Windows Forms sencillo](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  
  
 La clase base para los controles de Windows Forms, <xref:System.Windows.Forms.Control>, proporciona la instalación necesaria para la presentación visual de las aplicaciones basadas en Windows del lado cliente.  <xref:System.Windows.Forms.Control> proporciona un controlador de ventana, controla el enrutamiento de mensajes y proporciona eventos de teclado y de mouse así como muchos otros eventos de la interfaz de usuario.  Dispone de un diseño avanzado y posee propiedades específicas de presentación visual, como las propiedades <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, y muchas otras.  Además, proporciona seguridad, compatibilidad para subprocesos e interoperabilidad con los controles ActiveX.  Dado que gran parte de la infraestructura la proporciona la clase base, resulta relativamente fácil desarrollar controles de formularios Windows Forms propios.  
  
## Vea también  
 [Cómo: Desarrollar un control de formularios Windows Forms sencillo](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)   
 [Desarrollar un control de formularios Windows Forms compuesto](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)   
 [Cómo: Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)   
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)