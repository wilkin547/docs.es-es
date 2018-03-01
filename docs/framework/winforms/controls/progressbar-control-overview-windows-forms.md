---
title: "Información general sobre ProgressBar (Control, formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c5ca5fd908124b0f38643c7b2833ba591be3b980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="progressbar-control-overview-windows-forms"></a>Información general sobre ProgressBar (Control, formularios Windows Forms)
> [!IMPORTANT]
>  El control <xref:System.Windows.Forms.ToolStripProgressBar> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ProgressBar>; sin embargo, el control <xref:System.Windows.Forms.ProgressBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 Los formularios Windows Forms <xref:System.Windows.Forms.ProgressBar> control indica el progreso de un proceso, mostrando un número adecuado de rectángulos dispuestos en una barra horizontal. Una vez completado el proceso, la barra se llena. Barras de progreso suelen utilizarse para dar al usuario una idea de cómo deberá esperar un proceso para completar; Por ejemplo, cuando un archivo grande se está cargando.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.ProgressBar> control sólo se puede orientar horizontalmente en el formulario.  
  
## <a name="key-properties-and-methods"></a>Métodos y propiedades claves  
 Las propiedades de clave de la <xref:System.Windows.Forms.ProgressBar> control son <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, y <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. El <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> propiedades establecen los valores máximo y mínimos que puede mostrar la barra de progreso. El <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad representa el progreso que se ha realizado para completar la operación. Puesto que la barra se muestra en el control se compone de bloques, el valor se muestra por el <xref:System.Windows.Forms.ProgressBar> control sólo se aproxima a la <xref:System.Windows.Forms.ProgressBar.Value%2A> valor actual de la propiedad. En función del tamaño de la <xref:System.Windows.Forms.ProgressBar> (control), el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad determina cuándo se debe mostrar el siguiente bloque.  
  
 La manera más común para actualizar el valor de progreso actual es escribir código para establecer el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad. En el ejemplo de la carga de un archivo grande, podría establecer el máximo para el tamaño del archivo en kilobytes. Por ejemplo, si la <xref:System.Windows.Forms.ProgressBar.Maximum%2A> propiedad se establece en 100, el <xref:System.Windows.Forms.ProgressBar.Minimum%2A> propiedad se establece en 10 y el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad se establece en 50, se mostrarán 5 rectángulos. Esto es la mitad del número que se pueden mostrar.  
  
 Sin embargo, hay otras maneras de modificar el valor mostrado por el <xref:System.Windows.Forms.ProgressBar> control, aparte de la configuración de la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad directamente. El <xref:System.Windows.Forms.ProgressBar.Step%2A> propiedad puede utilizarse para especificar un valor para aumentar la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad. A continuación, llamar a la <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> método incrementará el valor. Para cambiar el valor de incremento, puede utilizar el <xref:System.Windows.Forms.ProgressBar.Increment%2A> método y especifique un valor con el que se va a incrementar el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad.  
  
 Otro control que informa gráficamente al usuario acerca de una acción actual es el <xref:System.Windows.Forms.StatusBar> control.  
  
> [!IMPORTANT]
>  El <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> controles reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controla; sin embargo, el <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controles se conservan por compatibilidad con versiones anteriores y uso futuro, si se Elija esta opción.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ProgressBar>  
 [ProgressBar (control)](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)
