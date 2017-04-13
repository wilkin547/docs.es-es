---
title: "Gr&#225;ficos de doble b&#250;fer | Microsoft Docs"
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
  - "doble búfer"
  - "ejemplos [Windows Forms], gráficos de doble búfer"
  - "parpadeo, reducir con doble búfer"
  - "gráficos, de doble búfer"
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gr&#225;ficos de doble b&#250;fer
El parpadeo es un problema común al programar los gráficos.  Las operaciones de gráficos que requieren varias operaciones complejas de representación pueden hacer que las imágenes representadas parezcan parpadear o tener una apariencia poco aceptable.  Para solucionar estos problemas, .NET Framework proporciona acceso al búfer doble.  
  
 El búfer doble utiliza un búfer de memoria para solucionar los problemas de parpadeo asociados a varias operaciones de representación.  Cuando se habilita el doble búfer, todas las operaciones de representación se representan en primer lugar en un búfer de memoria en lugar de en la pantalla.  Después de finalizar todas las operaciones de representación, el búfer de memoria se copia directamente en la superficie de representación asociada.  Cómo sólo se realiza en la pantalla una operación de gráficos, se elimina el parpadeo de las imágenes asociado a las operaciones complejas de representación.  
  
## Búfer doble predeterminado  
 La forma más sencilla de utilizar el búfer doble en las aplicaciones consiste en utilizar el búfer doble predeterminado para los formularios y controles incluidos en .NET Framework.  Se puede habilitar el búfer doble predeterminado en los formularios Windows Forms y en los controles creados de Windows estableciendo la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> en `true` o mediante el método <xref:System.Windows.Forms.Control.SetStyle%2A>.  Para obtener más información, vea [Cómo: Reducir el parpadeo de los gráficos con un búfer doble en formularios y controles](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md).  
  
## Administrar manualmente gráficos almacenados en búfer  
 En aquellos escenarios de doble búfer más avanzados, como animación o administración de memoria avanzada, se pueden utilizar las clases .NET Framework para implementar la lógica de doble búfer propia.  La clase responsable de asignar y administrar búferes de gráficos individuales es la clase <xref:System.Drawing.BufferedGraphicsContext>.  Cada dominio de aplicación cuenta con su propia instancia de <xref:System.Drawing.BufferedGraphicsContext> predeterminada que administra todos los búferes dobles predeterminados para esa aplicación.  En la mayoría de los casos, habrá sólo un dominio de aplicación por aplicación, por tanto habrá por lo general un único <xref:System.Drawing.BufferedGraphicsContext> por aplicación.  La clase <xref:System.Drawing.BufferedGraphicsManager> administra las instancias de <xref:System.Drawing.BufferedGraphicsContext> predeterminadas.  Puede recuperar una referencia a la instancia de <xref:System.Drawing.BufferedGraphicsContext> predeterminada mediante la llamada a la propiedad [BufferedGraphicsManager.Current](frlrfSystemDrawingBufferedGraphicsManagerClassCurrentTopic).  También puede crear una instancia dedicada de <xref:System.Drawing.BufferedGraphicsContext>, que mejora el rendimiento de las aplicaciones con un uso intensivo de gráficos.  Para obtener más información sobre cómo crear una instancia <xref:System.Drawing.BufferedGraphicsContext>, vea [Cómo: Administrar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
## Mostrar manualmente gráficos almacenados en búfer  
 Se puede utilizar una instancia de la clase <xref:System.Drawing.BufferedGraphicsContext> para crear búferes de gráficos mediante la llamada al método [BufferedGraphicsContext.Allocate](frlrfSystemDrawingBufferedGraphicsContextClassAllocateTopic), que devuelve una instancia de la clase <xref:System.Drawing.BufferedGraphics>.  Los objetos <xref:System.Drawing.BufferedGraphics> administran un búfer de memoria asociado a la superficie de representación, como un formulario o un control.  
  
 Después de creada la instancia, la clase <xref:System.Drawing.BufferedGraphics> administra la representación a un búfer de gráficos residente en memoria.  Se pueden representar gráficos en el búfer de memoria mediante la propiedad [BufferedGraphics.Graphics](frlrfSystemDrawingBufferedGraphicsClassGraphicsTopic), que expone un objeto <xref:System.Drawing.Graphics> que representa directamente el búfer de memoria.  Puede pintar en este objeto <xref:System.Drawing.Graphics> al igual que en cualquier objeto que  <xref:System.Drawing.Graphics> represente una superficie de dibujo.  Después de que todos los gráficos se hayan dibujado en el búfer, utilice el método [BufferedGraphics.Render](frlrfSystemDrawingBufferedGraphicsClassRenderTopic) para copiar el contenido del búfer en la superficie de dibujo en la pantalla.  
  
 Para obtener más información sobre el uso de la clase <xref:System.Drawing.BufferedGraphics>, vea [Representar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md).  Para obtener más información sobre la representación de gráficos, vea [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
  
## Vea también  
 <xref:System.Drawing.BufferedGraphics>   
 <xref:System.Drawing.BufferedGraphicsContext>   
 <xref:System.Drawing.BufferedGraphicsManager>   
 [Cómo: Representar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)   
 [Cómo: Reducir el parpadeo de los gráficos con un búfer doble en formularios y controles](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)   
 [Cómo: Administrar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)