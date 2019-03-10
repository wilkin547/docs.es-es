---
title: Información general sobre ProgressBar (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: db0a43534080d630323d8c1c95759fd2dcc04a85
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707951"
---
# <a name="progressbar-control-overview-windows-forms"></a>Información general sobre ProgressBar (Control, formularios Windows Forms)
> [!IMPORTANT]
>  El control <xref:System.Windows.Forms.ToolStripProgressBar> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ProgressBar>; sin embargo, el control <xref:System.Windows.Forms.ProgressBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 Los formularios de Windows <xref:System.Windows.Forms.ProgressBar> control indica el progreso de un proceso al mostrar un número adecuado de rectángulos dispuestos en una barra horizontal. Una vez completado el proceso, la barra está llena. Barras de progreso se utilizan normalmente para proporcionar al usuario una idea de cuánto deberá esperar un proceso se complete; Por ejemplo, cuando un archivo grande se está cargando.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.ProgressBar> control sólo puede estar orientado horizontalmente en el formulario.  
  
## <a name="key-properties-and-methods"></a>Los métodos y propiedades de clave  
 Las propiedades de clave de la <xref:System.Windows.Forms.ProgressBar> control son <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, y <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. El <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> propiedades establecen los valores máximo y mínimos que puede mostrar la barra de progreso. El <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad representa el progreso que se ha realizado para completar la operación. Dado que la barra mostrada en el control se compone de bloques, el valor que muestra la <xref:System.Windows.Forms.ProgressBar> control sólo se aproxima a la <xref:System.Windows.Forms.ProgressBar.Value%2A> valor actual de la propiedad. En función del tamaño de la <xref:System.Windows.Forms.ProgressBar> (control), el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad determina cuándo se debe mostrar el siguiente bloque.  
  
 La manera más común para actualizar el valor de progreso actual es escribir código para establecer el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad. En el ejemplo de la carga de un archivo grande, puede establecer el valor máximo para el tamaño del archivo en kilobytes. Por ejemplo, si la <xref:System.Windows.Forms.ProgressBar.Maximum%2A> propiedad se establece en 100, el <xref:System.Windows.Forms.ProgressBar.Minimum%2A> propiedad se establece en 10 y el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad se establece en 50, se mostrarán 5 rectángulos. Esto es la mitad del número que se puede mostrar.  
  
 Sin embargo, hay otras maneras de modificar el valor mostrado por el <xref:System.Windows.Forms.ProgressBar> control, aparte de la configuración de la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad directamente. El <xref:System.Windows.Forms.ProgressBar.Step%2A> propiedad puede usarse para especificar un valor que se va a incrementar el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad. A continuación, llamar a la <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> método incrementará el valor. Para variar el valor de incremento, puede usar el <xref:System.Windows.Forms.ProgressBar.Increment%2A> método y especifique un valor con el que se va a incrementar el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad.  
  
 Otro control que informa gráficamente al usuario acerca de una acción actual es el <xref:System.Windows.Forms.StatusBar> control.  
  
> [!IMPORTANT]
>  El <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> controles reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controla; sin embargo, el <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controles se conservan por compatibilidad con versiones anteriores y uso futuro, si se Elija esta opción.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ProgressBar>
- [ProgressBar (control)](progressbar-control-windows-forms.md)
