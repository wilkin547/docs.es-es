---
title: "Informaci&#243;n general sobre la propiedad AutoSize | Microsoft Docs"
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
  - "cambiar de tamaño de forma automática"
  - "AutoSize (propiedad)"
  - "AutoSizeMode (propiedad)"
  - "diseño [Windows Forms], AutoSize"
  - "ajustar el tamaño, automáticamente"
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general sobre la propiedad AutoSize
La propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> permite a un control cambiar su tamaño, si es necesario, para obtener el valor especificado por la propiedad <xref:System.Windows.Forms.Control.PreferredSize%2A>.  Para ajustar el comportamiento de tamaño de controles específicos, establezca la propiedad `AutoSizeMode`.  
  
## Comportamiento de la propiedad AutoSize  
 Sólo algunos controles admiten la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>.  Además, algunos controles que admiten la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> también admiten la propiedad `AutoSizeMode`.  
  
 La propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> tiene un comportamiento algo diferente, dependiendo del tipo de control y del valor de la propiedad `AutoSizeMode`, si existe.  En la tabla siguiente se describen los comportamientos cuya condición es verdadera y se proporciona un breve descripción de cada uno:  
  
|Comportamiento siempre verdadero|Descripción|  
|--------------------------------------|-----------------|  
|El cambio automático es una característica en tiempo de ejecución.|Esto significa que nunca aumenta o reduce un control y, por tanto, no tiene ningún efecto adicional.|  
|Si un control cambia el tamaño, el valor de la propiedad <xref:System.Windows.Forms.Control.Location%2A> siempre permanece constante.|Cuando es necesario que aumente debido al contenido de un control, el control se amplía hacia la derecha y hacia abajo.  Los controles no se extienden a la izquierda.|  
|Se admiten las propiedades <xref:System.Windows.Forms.Control.Dock%2A> y <xref:System.Windows.Forms.Control.Anchor%2A> cuando <xref:System.Windows.Forms.Control.AutoSize%2A> es `true`.|El valor de la propiedad <xref:System.Windows.Forms.Control.Location%2A> del control se ajusta al valor correcto.<br /><br /> **Nota** El control <xref:System.Windows.Forms.Label> es la excepción a esta regla.  Si se establece el valor de una propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> de un control <xref:System.Windows.Forms.Label> acoplado en `true`, el control <xref:System.Windows.Forms.Label> no se ajustará.|  
|Siempre se admiten las propiedades <xref:System.Windows.Forms.Control.MaximumSize%2A> y <xref:System.Windows.Forms.Control.MinimumSize%2A> del control, sin tener en cuenta el valor de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>.|La propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> no afecta a las propiedades <xref:System.Windows.Forms.Control.MaximumSize%2A> y <xref:System.Windows.Forms.Control.MinimumSize%2A>.|  
|No hay ningún tamaño mínimo establecido de forma predeterminada.|Esto significa que si se establece un control para reducirse en <xref:System.Windows.Forms.Control.AutoSize%2A> y no tiene contenido, el valor de su propiedad <xref:System.Windows.Forms.Control.Size%2A> es 0,0.  En este caso, el control reducirá a un punto, que no será visible.|  
|Si un control no implementa el método <xref:System.Windows.Forms.Control.GetPreferredSize%2A>, este método <xref:System.Windows.Forms.Control.GetPreferredSize%2A> devuelve el último valor asignado a la propiedad <xref:System.Windows.Forms.Control.Size%2A>.|Lo que significa que el establecimiento de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> en `true` no tendrá ningún efecto.|  
|Siempre se reduce el control en una celda <xref:System.Windows.Forms.TableLayoutPanel> para ajustarse en la celda hasta que se alcance la propiedad <xref:System.Windows.Forms.Control.MinimumSize%2A>.|Este tamaño se exige como tamaño máximo.  Éste no es el caso si la celda forma parte de una fila o columna de <xref:System.Windows.Forms.SizeType>.|  
  
## Propiedad AutoSizeMode  
 La propiedad `AutoSizeMode` proporciona un control más detallado sobre el comportamiento predeterminado de <xref:System.Windows.Forms.Control.AutoSize%2A>.  La propiedad `AutoSizeMode` especifica cómo un control se ajusta a su contenido.  Por ejemplo, el contenido podría ser el texto en un control <xref:System.Windows.Forms.Button> o los controles secundarios en un contenedor.  
  
 En la tabla siguiente se muestra la configuración de <xref:System.Windows.Forms.AutoSizeMode> y una descripción del comportamiento que provoca cada configuración.  
  
|Configuración de AutoSizeMode|Comportamiento|  
|-----------------------------------|--------------------|  
|GrowAndShrink|El control aumenta o se reduce para ajustar su contenido.<br /><br /> Se admiten los valores de las propiedades <xref:System.Windows.Forms.Control.MinimumSize%2A> y <xref:System.Windows.Forms.Control.MaximumSize%2A>, pero se omite el valor actual de la propiedad <xref:System.Windows.Forms.Control.Size%2A>.<br /><br /> Es el mismo comportamiento que los controles con la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> y sin la propiedad `AutoSizeMode`.|  
|GrowOnly|El control aumenta lo necesario para ajustar el contenido, pero no se reducirá más que el valor especificado por la propiedad <xref:System.Windows.Forms.Control.Size%2A>.<br /><br /> Éste es el valor predeterminado de `AutoSizeMode`.|  
  
## Controles que admiten la propiedad AutoSize  
 En la tabla siguiente se muestran los controles que admiten las propiedades <xref:System.Windows.Forms.Control.AutoSize%2A> y `AutoSizeMode`.  
  
|Compatibilidad con AutoSize|Tipo de control|  
|---------------------------------|---------------------|  
|-   Se admite la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>.<br />-   Ninguna propiedad `AutoSizeMode`.|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox> \(<xref:System.Windows.Forms.TextBox> base\)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|-   Se admite la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>.<br />-   Se admite la propiedad `AutoSizeMode`.|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|-   Ninguna propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>.|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## Propiedad AutoSize en el entorno de diseño  
 En la tabla siguiente se describe el comportamiento del tamaño de un control en tiempo de diseño, basado en el valor de las propiedades <xref:System.Windows.Forms.Control.AutoSize%2A> y `AutoSizeMode`.  
  
 Reemplace la propiedad <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> para determinar si un control determinado se encuentra en un estado cuyo tamaño pueda ser modificado por el usuario.  En la tabla siguiente "no puede" significa únicamente <xref:System.Windows.Forms.Design.SelectionRules>, "puede" significa <xref:System.Windows.Forms.Design.SelectionRules> y <xref:System.Windows.Forms.Design.SelectionRules>.  
  
|Valores de configuración de AutoSize|Gesto de ajuste de tamaño en tiempo de diseño|  
|------------------------------------------|---------------------------------------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   Ninguna propiedad `AutoSizeMode`.|El usuario no puede cambiar el tamaño del control en tiempo de diseño, salvo en los controles siguientes:<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   `AutoSizeMode` \= <xref:System.Windows.Forms.AutoSizeMode>|El usuario no puede cambiar el tamaño del control en tiempo de diseño.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   `AutoSizeMode` \= <xref:System.Windows.Forms.AutoSizeMode>|El usuario puede cambiar el tamaño del control en tiempo de diseño.  Cuando se establece la propiedad <xref:System.Windows.Forms.Control.Size%2A>, el usuario sólo puede aumentar el tamaño del control.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `false` o la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> está oculta.|El usuario puede cambiar el tamaño del control en tiempo de diseño.|  
  
> [!NOTE]
>  Para aumentar la productividad, el Diseñador de Windows Forms sombrea la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> para la clase <xref:System.Windows.Forms.Form>.  En tiempo de diseño, el formulario se comporta como si la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> se estableciera en `false`, sin tener en cuenta su configuración real.  En el tiempo de ejecución, no se realiza ningún cambio especial y la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> se aplica tal como se ha especificado en la configuración de las propiedades.  
  
## Vea también  
 <xref:System.Windows.Forms.Control.AutoSize%2A>   
 <xref:System.Windows.Forms.Control.PreferredSize%2A>   
 <xref:System.Windows.Forms.Control.GetPreferredSize%2A>