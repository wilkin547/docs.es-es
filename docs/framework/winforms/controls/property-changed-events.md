---
title: "Eventos de cambio de propiedades | Microsoft Docs"
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
  - "controles personalizados [Windows Forms], cambios en las propiedades (utilizando el código)"
  - "propiedades [Windows Forms], cambios"
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Eventos de cambio de propiedades
Si desea que el control envíe notificaciones cuando cambia una propiedad denominada *nombreDePropiedad*, defina un evento denominado *nombreDePropiedad*`Changed` y un método denominado `On`*nombreDePropiedad*`Changed` que provoque el evento.  Según la convención de nomenclatura de los formularios Windows Forms, se debe agregar la palabra *Changed* al nombre de la propiedad.  El tipo de delegado de evento asociado para los eventos de cambio de propiedades es <xref:System.EventHandler> y el tipo de datos de evento es <xref:System.EventArgs>.  La clase base <xref:System.Windows.Forms.Control> define muchos eventos de cambio de propiedades, como <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, y otros.  Para obtener información adicional sobre los eventos, vea [Eventos](../../../../docs/standard/events/index.md) y [Eventos de los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).  
  
 Los eventos de cambio de propiedades son de utilidad ya que permiten a los consumidores de un control agregar controladores de eventos que respondan al cambio.  Si el control ha de responder a un evento de cambio de propiedades provocado por él mismo, debe invalidarse el método `On`*nombreDePropiedad*`Changed` correspondiente en vez de asociar un delegado al evento.  Los controles responden normalmente a un evento PropertyChanged actualizando otras propiedades o volviendo a dibujar toda su superficie de dibujo o parte de la misma.  
  
 En el siguiente ejemplo se muestra cómo el control personalizado `FlashTrackBar` responde a algunos de los eventos de cambio de propiedades que hereda de <xref:System.Windows.Forms.Control>.  Para obtener el ejemplo completo, vea [Cómo: Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## Vea también  
 [Eventos](../../../../docs/standard/events/index.md)   
 [Eventos de los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)   
 [Propiedades de los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)