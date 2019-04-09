---
title: Información general sobre la propiedad AutoSize
ms.date: 03/30/2017
helpviewer_keywords:
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
ms.openlocfilehash: 6d5c4a22f186ddc5811c4a4d5e79776decea9e50
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173633"
---
# <a name="autosize-property-overview"></a>Información general sobre la propiedad AutoSize
El <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad permite a un control cambiar su tamaño, si es necesario, para alcanzar el valor especificado por el <xref:System.Windows.Forms.Control.PreferredSize%2A> propiedad. Ajustar el comportamiento de ajuste de tamaño de controles específicos estableciendo el `AutoSizeMode` propiedad.  
  
## <a name="autosize-behavior"></a>Comportamiento de AutoSize  
 Sólo algunos controles admiten la <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad. Además, algunos controles que admiten la <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad también admiten la `AutoSizeMode` propiedad.  
  
 El <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad produce un comportamiento un poco diferente, dependiendo del tipo de control y el valor de la `AutoSizeMode` propiedad, si existe la propiedad. En la tabla siguiente se describe los comportamientos que siempre son true y proporciona una breve descripción de cada uno:  
  
|Comportamiento siempre true|Descripción|  
|--------------------------|-----------------|  
|Ajuste de tamaño automático es una característica de tiempo de ejecución.|Esto significa nunca aumenta o reduce un control y, a continuación, no tiene ningún efecto adicional.|  
|Si un control cambia de tamaño, el valor de su <xref:System.Windows.Forms.Control.Location%2A> propiedad permanece constante.|Cuando el contenido de un control hacer que éste crezca, que crece el control hacia la derecha y hacia abajo. Controles no se extienden hacia la izquierda.|  
|El <xref:System.Windows.Forms.Control.Dock%2A> y <xref:System.Windows.Forms.Control.Anchor%2A> propiedades se aplican cuando <xref:System.Windows.Forms.Control.AutoSize%2A> es `true`.|El valor del control <xref:System.Windows.Forms.Control.Location%2A> propiedad se ajusta al valor correcto.<br /><br /> **Tenga en cuenta** el <xref:System.Windows.Forms.Label> control es la excepción a esta regla. Al establecer el valor de un acoplado <xref:System.Windows.Forms.Label> del control <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad `true`, el <xref:System.Windows.Forms.Label> control no se ajustará.|  
|Un control <xref:System.Windows.Forms.Control.MaximumSize%2A> y <xref:System.Windows.Forms.Control.MinimumSize%2A> propiedades siempre se respetan, independientemente del valor de su <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad.|El <xref:System.Windows.Forms.Control.MaximumSize%2A> y <xref:System.Windows.Forms.Control.MinimumSize%2A> propiedades no se ven afectadas por la <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad.|  
|No hay ningún tamaño mínimo establecido de forma predeterminada.|Esto significa que si se establece un control para reducirse en <xref:System.Windows.Forms.Control.AutoSize%2A> y no tiene contenido, el valor de su <xref:System.Windows.Forms.Control.Size%2A> propiedad es 0,0. En este caso, el control se reducirá a un punto, y no será visible.|  
|Si un control no implementa la <xref:System.Windows.Forms.Control.GetPreferredSize%2A> método, el <xref:System.Windows.Forms.Control.GetPreferredSize%2A> método devuelve el último valor asignado a la <xref:System.Windows.Forms.Control.Size%2A> propiedad.|Esto significa que esa configuración <xref:System.Windows.Forms.Control.AutoSize%2A> a `true` no tendrá ningún efecto.|  
|Un control en un <xref:System.Windows.Forms.TableLayoutPanel> celda siempre reduce para ajustarse en la celda hasta que su <xref:System.Windows.Forms.Control.MinimumSize%2A> se alcanza.|Este tamaño se aplica como un tamaño máximo. Esto no es el caso cuando la celda forma parte de un <xref:System.Windows.Forms.SizeType.AutoSize> fila o columna.|  
  
## <a name="autosizemode-property"></a>AutoSizeMode (propiedad)  
 El `AutoSizeMode` propiedad proporciona un mayor control sobre los valores predeterminados <xref:System.Windows.Forms.Control.AutoSize%2A> comportamiento. El `AutoSizeMode` propiedad especifica cómo un control se ajusta a su contenido. El contenido, por ejemplo, podría ser el texto para un <xref:System.Windows.Forms.Button> control o los controles secundarios de un contenedor.  
  
 La tabla siguiente muestra el <xref:System.Windows.Forms.AutoSizeMode> configuración y una descripción del comportamiento provoca cada configuración.  
  
|Configuración de AutoSizeMode|Comportamiento|  
|--------------------------|--------------|  
|GrowAndShrink|El control se expande o se reduce para ajustar su contenido.<br /><br /> El <xref:System.Windows.Forms.Control.MinimumSize%2A> y <xref:System.Windows.Forms.Control.MaximumSize%2A> se respetan los valores, pero el valor actual de la <xref:System.Windows.Forms.Control.Size%2A> propiedad se omite.<br /><br /> Este es el mismo comportamiento que los controles con el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad y no `AutoSizeMode` propiedad.|  
|GrowOnly|El control expande todo lo necesario para abarcar su contenido, pero no se reducirá más pequeño que el valor especificado por su <xref:System.Windows.Forms.Control.Size%2A> propiedad.<br /><br /> Este es el valor predeterminado de la clase `AutoSizeMode`.|  
  
## <a name="controls-that-support-the-autosize-property"></a>Controles que admiten la propiedad AutoSize  
 En la tabla siguiente se enumera los controles que admiten la <xref:System.Windows.Forms.Control.AutoSize%2A> y `AutoSizeMode` propiedades.  
  
|Compatibilidad con AutoSize|Tipo de control|  
|----------------------|------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> admitidos la propiedad.<br />-Ningún `AutoSizeMode` propiedad.|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox> (<xref:System.Windows.Forms.TextBox> base)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> admitidos la propiedad.<br />-   `AutoSizeMode` admitidos la propiedad.|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|-Ningún <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad.|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## <a name="autosize-in-the-design-environment"></a>AutoSize en el entorno de diseño  
 La tabla siguiente describe el comportamiento de ajuste de tamaño de un control en tiempo de diseño, en función del valor de su <xref:System.Windows.Forms.Control.AutoSize%2A> y `AutoSizeMode` propiedades.  
  
 Invalidar el <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> propiedad para determinar si un control determinado está en un estado de usuario de tamaño variable. En la tabla siguiente, "no" significa <xref:System.Windows.Forms.Design.SelectionRules.Moveable> sólo, "puede" significa <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> y <xref:System.Windows.Forms.Design.SelectionRules.Moveable>.  
  
|Configuración de la propiedad AutoSize|Ajuste de tamaño en tiempo de diseño|  
|-----------------------|---------------------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-Ningún `AutoSizeMode` propiedad.|El usuario no puede cambiar el tamaño del control en tiempo de diseño, excepto los siguientes controles:<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>|El usuario no puede cambiar el tamaño del control en tiempo de diseño.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>|El usuario puede cambiar el tamaño del control en tiempo de diseño. Cuando el <xref:System.Windows.Forms.Control.Size%2A> propiedad está establecida, el usuario solo puede aumentar el tamaño del control.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`, o <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad está oculta.|Usuario puede cambiar el tamaño del control en tiempo de diseño.|  
  
> [!NOTE]
>  Para maximizar la productividad, las sombras del Diseñador de Windows Forms el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad para el <xref:System.Windows.Forms.Form> clase. En tiempo de diseño, el formulario se comporta como si la <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad está establecida en `false`, independientemente de su configuración real. En tiempo de ejecución, no se realiza ningún cambio especial y el <xref:System.Windows.Forms.Control.AutoSize%2A> se aplica la propiedad tal y como especifica el valor de propiedad.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.PreferredSize%2A>
- <xref:System.Windows.Forms.Control.GetPreferredSize%2A>
