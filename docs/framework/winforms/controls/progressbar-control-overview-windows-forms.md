---
title: Información general sobre ProgressBar (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: 7dd434492cd688527ddbce5aaffa442a0b40a9e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968316"
---
# <a name="progressbar-control-overview-windows-forms"></a>Información general sobre ProgressBar (Control, formularios Windows Forms)
> [!IMPORTANT]
> El control <xref:System.Windows.Forms.ToolStripProgressBar> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ProgressBar>; sin embargo, el control <xref:System.Windows.Forms.ProgressBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 El control <xref:System.Windows.Forms.ProgressBar> Windows Forms indica el progreso de un proceso mostrando un número adecuado de rectángulos organizados en una barra horizontal. Una vez completado el proceso, se rellena la barra. Las barras de progreso se utilizan normalmente para proporcionar al usuario una idea de cuánto tiempo se debe esperar para que se complete un proceso; por ejemplo, cuando se carga un archivo grande.  
  
> [!NOTE]
> El <xref:System.Windows.Forms.ProgressBar> control solo se puede orientar horizontalmente en el formulario.  
  
## <a name="key-properties-and-methods"></a>Propiedades y métodos clave  
 Las <xref:System.Windows.Forms.ProgressBar> propiedades clave del control son <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>y <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Las <xref:System.Windows.Forms.ProgressBar.Minimum%2A> propiedades <xref:System.Windows.Forms.ProgressBar.Maximum%2A> y establecen los valores máximo y mínimo que puede mostrar la barra de progreso. La <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad representa el progreso que se ha realizado para completar la operación. Dado que la barra mostrada en el control se compone de bloques, el valor que <xref:System.Windows.Forms.ProgressBar> muestra el control solo se <xref:System.Windows.Forms.ProgressBar.Value%2A> aproxima al valor actual de la propiedad. En función del tamaño del <xref:System.Windows.Forms.ProgressBar> control, la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad determina cuándo se debe mostrar el bloque siguiente.  
  
 La forma más común de actualizar el valor de progreso actual es escribir código para establecer la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad. En el ejemplo de carga de un archivo grande, puede establecer el máximo en el tamaño del archivo en kilobytes. Por ejemplo, si la <xref:System.Windows.Forms.ProgressBar.Maximum%2A> propiedad se establece en 100, la <xref:System.Windows.Forms.ProgressBar.Minimum%2A> propiedad se establece en 10 y la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad se establece en 50, se mostrarán 5 rectángulos. Esta es la mitad del número que se puede mostrar.  
  
 Sin embargo, hay otras formas de modificar el valor que muestra el <xref:System.Windows.Forms.ProgressBar> control, además de establecer la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad directamente. La <xref:System.Windows.Forms.ProgressBar.Step%2A> propiedad se puede utilizar para especificar un valor para incrementar la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad. A continuación, al <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> llamar al método se incrementará el valor. Para modificar el valor de incremento, puede usar el <xref:System.Windows.Forms.ProgressBar.Increment%2A> método y especificar un valor con el que incrementar la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad.  
  
 Otro control que informa gráficamente al usuario sobre una acción actual es el <xref:System.Windows.Forms.StatusBar> control.  
  
> [!IMPORTANT]
> Los <xref:System.Windows.Forms.StatusStrip> controles <xref:System.Windows.Forms.ToolStripStatusLabel> y reemplazan y agregan funcionalidad <xref:System.Windows.Forms.StatusBar> a <xref:System.Windows.Forms.StatusBarPanel> los controles y; sin <xref:System.Windows.Forms.StatusBar> embargo <xref:System.Windows.Forms.StatusBarPanel> , los controles y se conservan por compatibilidad con versiones anteriores y uso futuro, si Elija.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ProgressBar>
- [ProgressBar (control)](progressbar-control-windows-forms.md)
