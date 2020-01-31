---
title: Información general sobre el control ProgressBar
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: a0c4a0401d06614ab3ad148b932ebc64080c592c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741282"
---
# <a name="progressbar-control-overview-windows-forms"></a>Información general sobre ProgressBar (Control, formularios Windows Forms)
> [!IMPORTANT]
> El control <xref:System.Windows.Forms.ToolStripProgressBar> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ProgressBar>; sin embargo, el control <xref:System.Windows.Forms.ProgressBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 El control Windows Forms <xref:System.Windows.Forms.ProgressBar> indica el progreso de un proceso al mostrar un número adecuado de rectángulos organizados en una barra horizontal. Una vez completado el proceso, se rellena la barra. Las barras de progreso se utilizan normalmente para proporcionar al usuario una idea de cuánto tiempo se debe esperar para que se complete un proceso; por ejemplo, cuando se carga un archivo grande.  
  
> [!NOTE]
> El control <xref:System.Windows.Forms.ProgressBar> solo se puede orientar horizontalmente en el formulario.  
  
## <a name="key-properties-and-methods"></a>Propiedades y métodos clave  
 Las propiedades clave del control <xref:System.Windows.Forms.ProgressBar> son <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>y <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Las propiedades <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> establecen los valores máximo y mínimo que puede mostrar la barra de progreso. La propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> representa el progreso que se ha realizado para completar la operación. Dado que la barra mostrada en el control se compone de bloques, el valor que muestra el control <xref:System.Windows.Forms.ProgressBar> solo se aproxima al valor actual de la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A>. En función del tamaño del control <xref:System.Windows.Forms.ProgressBar>, la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> determina cuándo se debe mostrar el bloque siguiente.  
  
 La forma más común de actualizar el valor de progreso actual es escribir código para establecer la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A>. En el ejemplo de carga de un archivo grande, puede establecer el máximo en el tamaño del archivo en kilobytes. Por ejemplo, si la propiedad <xref:System.Windows.Forms.ProgressBar.Maximum%2A> está establecida en 100, la propiedad <xref:System.Windows.Forms.ProgressBar.Minimum%2A> está establecida en 10 y la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> está establecida en 50, se mostrarán 5 rectángulos. Esta es la mitad del número que se puede mostrar.  
  
 Sin embargo, hay otras formas de modificar el valor mostrado por el control <xref:System.Windows.Forms.ProgressBar>, además de establecer la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> directamente. La propiedad <xref:System.Windows.Forms.ProgressBar.Step%2A> se puede utilizar para especificar un valor para incrementar la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A>. A continuación, al llamar al método <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> se incrementará el valor. Para modificar el valor de incremento, puede utilizar el método <xref:System.Windows.Forms.ProgressBar.Increment%2A> y especificar un valor con el que incrementar la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A>.  
  
 Otro control que informa gráficamente al usuario sobre una acción actual es el control de <xref:System.Windows.Forms.StatusBar>.  
  
> [!IMPORTANT]
> Los controles <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel>; sin embargo, los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ProgressBar>
- [ProgressBar (control)](progressbar-control-windows-forms.md)
