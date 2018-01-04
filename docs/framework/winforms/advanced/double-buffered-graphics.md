---
title: "Gráficos de doble búfer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double buffering
- graphics [Windows Forms], double-buffered
- flicker [Windows Forms], reducing with double buffering
- examples [Windows Forms], double-buffered graphics
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7e4445b0a729eb1f826d17340db02f0c56149b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="double-buffered-graphics"></a>Gráficos de doble búfer
El parpadeo es un problema frecuente al programar gráficos. Las operaciones gráficas que requieren varias operaciones de pintura complejas pueden hacer que las imágenes representadas parezcan parpadear o tengan un aspecto de algún modo inaceptable. Para resolver estos problemas, .NET Framework proporciona acceso al almacenamiento en doble búfer.  
  
 El almacenamiento en doble búfer usa un búfer de memoria para solucionar los problemas de parpadeo asociados a varias operaciones de pintura. Cuando se habilita el almacenamiento en doble búfer, todas las operaciones de pintura se representan primero en un búfer de memoria en lugar de la superficie de dibujo en la pantalla. Una vez completadas todas las operaciones de pintura, el búfer de memoria se copia directamente en la superficie de dibujo asociada a él. Como solo se realiza una única operación gráfica en la pantalla, se elimina el parpadeo de las imágenes asociado a las operaciones de pintura complejas.  
  
## <a name="default-double-buffering"></a>Almacenamiento en doble búfer predeterminado  
 La manera más fácil de usar el almacenamiento en doble búfer en la aplicación consiste en usar el almacenamiento en doble búfer predeterminado para formularios y controles que ofrece .NET Framework. Se puede habilitar de forma predeterminada el doble búfer para los formularios Windows Forms y controles creados de Windows estableciendo el <xref:System.Windows.Forms.Control.DoubleBuffered%2A> propiedad `true` o mediante la <xref:System.Windows.Forms.Control.SetStyle%2A> método. Para más información, consulte [How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md) (Cómo: Reducir el parpadeo de gráficos con almacenamiento en doble búfer de formularios y controles).  
  
## <a name="manually-managing-buffered-graphics"></a>Administración manual de gráficos almacenados en búfer  
 En el caso de escenarios de almacenamiento en doble búfer más avanzados, como animación y administración avanzada de memoria, puede usar las clases de .NET Framework para implementar su propia lógica de almacenamiento en doble búfer. La clase responsable de asignar y administrar los búferes de gráficos individuales es la <xref:System.Drawing.BufferedGraphicsContext> clase. Cada dominio de aplicación tiene su propio valor predeterminado <xref:System.Drawing.BufferedGraphicsContext> instancia que administra todos de manera predeterminada el doble búfer para esa aplicación. En la mayoría de los casos habrá un único dominio de aplicación por aplicación, por lo que generalmente es un valor predeterminado <xref:System.Drawing.BufferedGraphicsContext> por aplicación. Predeterminado <xref:System.Drawing.BufferedGraphicsContext> instancias administradas por el <xref:System.Drawing.BufferedGraphicsManager> clase. Puede recuperar una referencia a la predeterminada <xref:System.Drawing.BufferedGraphicsContext> instancia mediante una llamada a la <xref:System.Drawing.BufferedGraphicsManager.Current%2A>. También puede crear una dedicado <xref:System.Drawing.BufferedGraphicsContext> instancia, lo que puede mejorar el rendimiento de aplicaciones intensivas gráficamente. Para obtener información sobre cómo crear un <xref:System.Drawing.BufferedGraphicsContext> de la instancia, consulte [Cómo: Manually Manage Buffered Graphics](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
## <a name="manually-displaying-buffered-graphics"></a>Presentación manual de gráficos almacenados en búfer  
 Puede usar una instancia de la <xref:System.Drawing.BufferedGraphicsContext> clase para crear búferes de gráficos mediante una llamada a la <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A?displayProperty=nameWithType>, que devuelve una instancia de la <xref:System.Drawing.BufferedGraphics> clase. Un <xref:System.Drawing.BufferedGraphics> objeto administra un búfer de memoria que está asociado a una superficie de representación, como un formulario o control.  
  
 Una vez que se crea una instancia, la <xref:System.Drawing.BufferedGraphics> clase administra la representación a un búfer de gráficos residente en memoria. Pueden representar gráficos en el búfer de memoria a través de la <xref:System.Drawing.BufferedGraphics.Graphics%2A>, que expone un <xref:System.Drawing.Graphics> objeto que representa directamente el búfer de memoria. Puede dibujar a este <xref:System.Drawing.Graphics> objeto igual que haría para un <xref:System.Drawing.Graphics> objeto que representa una superficie de dibujo. Después de han dibujado todos los gráficos en el búfer, puede usar el <xref:System.Drawing.BufferedGraphics.Render%2A?displayProperty=nameWithType> para copiar el contenido del búfer en la superficie de dibujo en la pantalla.  
  
 Para obtener más información sobre el uso de la <xref:System.Drawing.BufferedGraphics> de clases, consulte [manualmente representar gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md). Para más información sobre la representación de gráficos, vea [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.BufferedGraphics>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 <xref:System.Drawing.BufferedGraphicsManager>  
 [Representar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 [Reducir el parpadeo de los gráficos con un búfer doble en formularios y controles](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 [Administrar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
