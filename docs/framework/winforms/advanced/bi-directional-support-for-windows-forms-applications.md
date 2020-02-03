---
title: Compatibilidad bidireccional
ms.date: 09/30/2017
helpviewer_keywords:
- globalization [Windows Forms], bi-directional support in Windows
- Windows Forms, international
- localization [Windows Forms], bi-directional support in Windows
- bi-directional language support [Windows Forms], Windows applications
- Windows Forms, bi-directional support
ms.openlocfilehash: 8b2e842fc08be78b74cede85927352fafca7bc8f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742077"
---
# <a name="bi-directional-support-for-windows-forms-applications"></a>Compatibilidad bidireccional en las aplicaciones de Windows Forms
Puede usar Visual Studio para crear aplicaciones basadas en Windows que admitan idiomas bidireccionales (de derecha a izquierda), como el árabe y el hebreo. Esto incluye formularios estándar, cuadros de diálogo, formularios MDI y todos los controles con los que puede trabajar en estos formularios, es decir, todos los objetos del espacio de nombres <xref:System.Windows.Forms.Control>.

## <a name="culture-support"></a>Compatibilidad con referencias culturales
 La configuración de referencia cultural e idioma de la interfaz de usuario determina cómo utiliza una aplicación las fechas, las horas, las monedas y otros datos. La compatibilidad con las referencias culturales y los idiomas de la interfaz de usuario es la misma con los idiomas bidireccionales que con los demás idiomas. Para obtener más información, vea [clases específicas de las referencias culturales para Windows Forms y formularios Web Forms globales](/visualstudio/ide/globalizing-and-localizing-applications).

## <a name="righttoleft-and-righttoleftlayout-properties"></a>Propiedades RightToLeft y RightToLeftLayout
 La clase base <xref:System.Windows.Forms.Control>, de la que derivan los formularios, incluye una propiedad <xref:System.Windows.Forms.Control.RightToLeft%2A> que puede establecer para cambiar el orden de lectura de un formulario y sus controles. Si establece la propiedad <xref:System.Windows.Forms.Control.RightToLeft%2A> del formulario, los controles predeterminados del formulario heredarán este ajuste. Sin embargo, también puede establecer la propiedad <xref:System.Windows.Forms.Control.RightToLeft%2A> individualmente en la mayoría de los controles. Vea también [Cómo: Mostrar texto de derecha a izquierda en Windows Forms para la globalización](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))

 El efecto de la propiedad <xref:System.Windows.Forms.Control.RightToLeft%2A> puede diferir de un control a otro. En algunos controles, la propiedad solo establece el orden de lectura, como en los controles <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.TreeView> y <xref:System.Windows.Forms.ToolTip>. En otros controles, la propiedad <xref:System.Windows.Forms.Control.RightToLeft%2A> cambia el orden de lectura y el diseño. Esto incluye los controles <xref:System.Windows.Forms.RadioButton>, <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.CheckBox>. Otros controles requieren que se aplique la propiedad <xref:System.Windows.Forms.Form.RightToLeftLayout%2A> para reflejar su diseño de derecha a izquierda. En la tabla siguiente, se proporcionan detalles sobre cómo las propiedades <xref:System.Windows.Forms.Control.RightToLeft%2A> y <xref:System.Windows.Forms.Form.RightToLeftLayout%2A> afectan a los controles individuales de los formularios Windows Forms.

|Control/componente|Efecto de la propiedad RightToLeft|Efecto de la propiedad RightToLeftLayout|¿Requiere la creación de reflejos?|
|------------------------|------------------------------------|------------------------------------------|-------------------------|
|<xref:System.Windows.Forms.Button>|Establece el orden de lectura de derecha a izquierda. Invierte <xref:System.Windows.Forms.ButtonBase.TextAlign%2A>, <xref:System.Windows.Forms.ButtonBase.ImageAlign%2A> y <xref:System.Windows.Forms.ButtonBase.TextImageRelation%2A>|Sin efecto|No|
|<xref:System.Windows.Forms.CheckBox>|La casilla se muestra en el lado derecho del texto|Sin efecto|No|
|<xref:System.Windows.Forms.CheckedListBox>|Todas las casillas se muestran en el lado derecho del texto|Sin efecto|No|
|<xref:System.Windows.Forms.ColorDialog>|No se ve afectada, depende del idioma del sistema operativo|Sin efecto|No|
|<xref:System.Windows.Forms.ComboBox>|Los elementos del control de cuadro combinado se alinean a la derecha|Sin efecto|No|
|<xref:System.Windows.Forms.ContextMenu>|Aparece alineado a la derecha con el orden de lectura de derecha a izquierda|Sin efecto|No|
|<xref:System.Windows.Forms.DataGrid>|Aparece alineado a la derecha con el orden de lectura de derecha a izquierda|Sin efecto|No|
|<xref:System.Windows.Forms.DataGridView>|Afecta al orden de lectura de derecha a izquierda y al diseño de los controles|Sin efecto|No|
|<xref:System.Windows.Forms.DateTimePicker>|No se ve afectada, depende del idioma del sistema operativo|Refleja el control|Sí|
|<xref:System.Windows.Forms.DomainUpDown>|Alinea a la izquierda los botones de arriba y abajo|Sin efecto|No|
|<xref:System.Windows.Forms.ErrorProvider>|No compatible|Sin efecto|No|
|<xref:System.Windows.Forms.FontDialog>|Depende del idioma del sistema operativo|Sin efecto|No|
|<xref:System.Windows.Forms.Form>|Establece el orden de lectura de derecha a izquierda e invierte las barras de desplazamiento|Refleja el formulario|Sí|
|<xref:System.Windows.Forms.GroupBox>|El título se muestra alineado a la derecha. Los controles secundarios pueden heredar esta propiedad.|Use <xref:System.Windows.Forms.TableLayoutPanel> dentro del control para admitir la creación de reflejos de derecha a izquierda|No|
|<xref:System.Windows.Forms.HScrollBar>|Comienza con el cuadro de desplazamiento (el control) alineado a la derecha|Sin efecto|No|
|<xref:System.Windows.Forms.ImageList>|No se requiere|Sin efecto|No|
|<xref:System.Windows.Forms.Label>|Se muestra alineado a la derecha. Invierte <xref:System.Windows.Forms.Label.TextAlign%2A> y <xref:System.Windows.Forms.Label.ImageAlign%2A>|Sin efecto|No|
|<xref:System.Windows.Forms.LinkLabel>|Se muestra alineado a la derecha. Invierte <xref:System.Windows.Forms.Label.TextAlign%2A> y <xref:System.Windows.Forms.Label.ImageAlign%2A>|Sin efecto|No|
|<xref:System.Windows.Forms.ListBox>|Los elementos se alinean a la derecha|Sin efecto|No|
|<xref:System.Windows.Forms.ListView>|Establece el orden de lectura de derecha a izquierda y los elementos permanecen alineados a la izquierda|Refleja el control|Sí|
|<xref:System.Windows.Forms.MainMenu>|Se muestra alineado a la derecha con el orden de lectura de derecha a izquierda en tiempo de ejecución (no en tiempo de diseño)|Sin efecto|No|
|<xref:System.Windows.Forms.MaskedTextBox>|Muestra el texto de derecha a izquierda.|Sin efecto|No|
|<xref:System.Windows.Forms.MonthCalendar>|No se ve afectada, depende del idioma del sistema operativo|Refleja el control|Sí|
|<xref:System.Windows.Forms.NotifyIcon>|No compatible|No compatible|No|
|<xref:System.Windows.Forms.NumericUpDown>|Los botones de arriba y abajo se alinean a la izquierda|Sin efecto|No|
|<xref:System.Windows.Forms.OpenFileDialog>|En los sistemas operativos de derecha a izquierda, al establecer la propiedad <xref:System.Windows.Forms.Control.RightToLeft> del formulario contenedor en <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType> se localiza el cuadro de diálogo |Sin efecto|No|
|<xref:System.Windows.Forms.PageSetupDialog>|No se ve afectada, depende del idioma del sistema operativo|Sin efecto|No|
|<xref:System.Windows.Forms.Panel>|Los controles secundarios pueden heredar esta propiedad|Use <xref:System.Windows.Forms.TableLayoutPanel> dentro del control para admitir la disposición de derecha a izquierda|Sí|
|<xref:System.Windows.Forms.PictureBox>|No compatible|Sin efecto|No|
|<xref:System.Windows.Forms.PrintDialog>|No se ve afectada, depende del idioma del sistema operativo|Sin efecto|No|
|<xref:System.Drawing.Printing.PrintDocument>|La barra de desplazamiento vertical se alinea a la izquierda y la barra de desplazamiento horizontal comienza a la izquierda|Sin efecto|No|
|<xref:System.Windows.Forms.PrintPreviewDialog>|No compatible|No compatible|No|
|<xref:System.Windows.Forms.ProgressBar>|No le afecta esta propiedad|Refleja el control|Sí|
|<xref:System.Windows.Forms.RadioButton>|El botón de radio se muestra en el lado derecho del texto|Sin efecto|No|
|<xref:System.Windows.Forms.RichTextBox>|Los elementos de control que incluyen texto se muestran de derecha a izquierda con el orden de lectura de derecha a izquierda|Sin efecto|No|
|<xref:System.Windows.Forms.SaveFileDialog>|No se ve afectada, depende del idioma del sistema operativo|Sin efecto|No|
|<xref:System.Windows.Forms.SplitContainer>|Se invierte el diseño del panel, la barra de desplazamiento vertical aparece a la izquierda y la barra de desplazamiento horizontal comienza desde la derecha|Use <xref:System.Windows.Forms.TableLayoutPanel> para reflejar el orden de los controles secundarios|No|
|<xref:System.Windows.Forms.Splitter>|No compatible|Sin efecto|No|
|<xref:System.Windows.Forms.StatusBar>|No se admite: utilice <xref:System.Windows.Forms.StatusStrip> en su lugar|Ningún efecto: utilice <xref:System.Windows.Forms.StatusStrip> en su lugar|No|
|<xref:System.Windows.Forms.TabControl>|No le afecta esta propiedad|Refleja el control|Sí|
|<xref:System.Windows.Forms.TextBox>|Muestra el texto de derecha a izquierda con el orden de lectura de derecha a izquierda|Sin efecto|No|
|<xref:System.Windows.Forms.Timer>|No se requiere|No se requiere|No|
|<xref:System.Windows.Forms.ToolBar>|No le afecta esta propiedad: use <xref:System.Windows.Forms.ToolStrip> en su lugar|Ningún efecto: utilice <xref:System.Windows.Forms.ToolStrip> en su lugar|Sí|
|<xref:System.Windows.Forms.ToolTip>|Establece el orden de lectura de derecha a izquierda|Sin efecto|No|
|<xref:System.Windows.Forms.TrackBar>|El desplazamiento o el seguimiento comienza a la derecha. Cuando <xref:System.Windows.Forms.TrackBar.Orientation%2A> es vertical, los tics se producen desde la derecha|Sin efecto|No|
|<xref:System.Windows.Forms.TreeView>|Establece el orden de lectura de derecha a izquierda solamente|Refleja el control|Sí|
|<xref:System.Windows.Forms.UserControl>|La barra de desplazamiento vertical aparece a la izquierda y la barra de desplazamiento horizontal tiene el control a la derecha|Sin compatibilidad directa: use <xref:System.Windows.Forms.TableLayoutPanel>|No|
|<xref:System.Windows.Forms.VScrollBar>|Se muestra en el lado izquierdo, en lugar del derecho, de los controles desplazables|Sin efecto|No|

## <a name="encoding"></a>Encoding
 Los formularios Windows Forms admiten Unicode, por lo que puede incluir cualquier juego de caracteres al crear aplicaciones bidireccionales. Sin embargo, no todos los controles de formularios Windows Forms admiten Unicode en todas las plataformas.

## <a name="gdi"></a>GDI+
 Puede usar GDI+ para dibujar texto con el orden de lectura de derecha a izquierda. El método <xref:System.Drawing.Graphics.DrawString%2A>, que se utiliza para dibujar texto, admite un parámetro `StringFormat` que puede establecer como el miembro <xref:System.Drawing.StringFormatFlags.DirectionRightToLeft> de la enumeración <xref:System.Drawing.StringFormatFlags> con el fin de invertir el punto de origen del texto.

## <a name="common-dialog-boxes"></a>Cuadros de diálogo comunes
 Las herramientas del sistema, como el cuadro de diálogo Abrir archivo, están bajo el control de Windows. Heredan los elementos de idioma del sistema operativo. Si está utilizando una versión de Windows con la configuración de idioma correcta, estos cuadros de diálogo funcionarán correctamente con los idiomas bidireccionales.

 De forma similar, los cuadros de mensaje pasan por el sistema operativo y admiten texto bidireccional. Los títulos de los botones de los cuadros de mensaje se basan en la configuración de idioma vigente. De forma predeterminada, los cuadros de mensaje no utilizan el orden de lectura de derecha a izquierda, pero puede especificar un parámetro para cambiar el orden de lectura cuando se muestran los cuadros de mensaje.

## <a name="righttoleft-scrollbars-and-scrollablecontrol"></a>RightToLeft, Scrollbars y ScrollableControl
 Actualmente hay una limitación en Windows Forms que impide que todas las clases derivadas de <xref:System.Windows.Forms.ScrollableControl> actúen correctamente cuando <xref:System.Windows.Forms.Control.RightToLeft%2A> está habilitado y <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> se establece como <xref:System.Windows.Forms.RightToLeft.Yes>. Por ejemplo, supongamos que coloca un control como <xref:System.Windows.Forms.Panel>, o una clase de contenedor derivada de <xref:System.Windows.Forms.Panel> (como <xref:System.Windows.Forms.FlowLayoutPanel> o <xref:System.Windows.Forms.TableLayoutPanel>), en el formulario. Si establece <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> en el contenedor como <xref:System.Windows.Forms.RightToLeft.Yes> y, luego, establece la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> en uno o varios de los controles del contenedor como <xref:System.Windows.Forms.AnchorStyles.Right>, no aparecerá ninguna barra de desplazamiento en ningún momento. La clase derivada de <xref:System.Windows.Forms.ScrollableControl> actúa como si <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> estuviera establecida como <xref:System.Windows.Forms.RightToLeft.No>.

 Actualmente, la única solución es anidar <xref:System.Windows.Forms.ScrollableControl> dentro de otro <xref:System.Windows.Forms.ScrollableControl>. Por ejemplo, si necesita que <xref:System.Windows.Forms.TableLayoutPanel> funcione en esta situación, puede colocarlo dentro de un control <xref:System.Windows.Forms.Panel> y establecer <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> en el <xref:System.Windows.Forms.Panel> como <xref:System.Windows.Forms.RightToLeft.Yes>.

## <a name="mirroring"></a>Creación de reflejo
 La *creación de reflejos* consiste en invertir el diseño de los elementos de la interfaz de usuario para que fluyan de derecha a izquierda. En un formulario Windows Forms reflejado, por ejemplo, los botones Minimizar, Maximizar y Cerrar aparecen en el extremo izquierdo de la barra de título, en lugar del extremo derecho.

 Al configurar la propiedad <xref:System.Windows.Forms.Control.RightToLeft%2A> de un formulario o un control como `true`, se invierte el orden de lectura de los elementos de un formulario, pero esta configuración no invierte el diseño de manera que quede de derecha a izquierda, es decir, no provoca la creación de un reflejo. Por ejemplo, al establecer esta propiedad, los botones **Minimizar**, **Maximizar** y **Cerrar** de la barra de título del formulario no se mueven a la izquierda del formulario. Del mismo modo, algunos controles, como el control <xref:System.Windows.Forms.TreeView>, deben reflejarse para cambiar su apariencia y ser adecuados para el árabe o el hebreo. Puede reflejar estos controles configurando la propiedad <xref:System.Windows.Forms.Form.RightToLeftLayout%2A>.

 Puede crear versiones reflejadas de los siguientes controles:

- <xref:System.Windows.Forms.ColumnHeader.ListView%2A>

- <xref:System.Windows.Forms.Panel>

- <xref:System.Windows.Forms.StatusBar>

- <xref:System.Windows.Forms.TabControl>

- <xref:System.Windows.Forms.TabPage>

- <xref:System.Windows.Forms.ToolBar>

- <xref:System.Windows.Forms.TreeView>

 Algunos controles están sellados, de modo que no puede derivar un nuevo control de ellos: por ejemplo, los controles <xref:System.Windows.Forms.ImageList> y <xref:System.Windows.Forms.ProgressBar>.

## <a name="see-also"></a>Consulte también

- [Compatibilidad bidireccional para aplicaciones web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/6eedwbtt(v=vs.100))
