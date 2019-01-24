---
title: Procedimiento Agregar mejoras a ToolStripMenuItems
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
ms.openlocfilehash: 621b96805543abb92bc73f734f1a090d9cdb7319
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685094"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Procedimiento Agregar mejoras a ToolStripMenuItems
Puede mejorar la facilidad de uso <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> controles de las maneras siguientes:  
  
-   Agregar marcas de verificación para designar si una característica está activada o desactivada, por ejemplo, si se muestra una regla a lo largo del margen de una aplicación de procesamiento de texto, o para indicar qué archivo en una lista de archivos se muestra, como en un **ventana** menú.  
  
-   Agregar imágenes que representan visualmente los comandos de menú.  
  
-   Mostrar teclas de método abreviado para proporcionar una alternativa de teclado para el mouse para llevar a cabo los comandos. Por ejemplo, al presionar CTRL+C realiza el **copia** comando.  
  
-   Para mostrar las teclas de acceso para proporcionar una alternativa de teclado para el mouse para la navegación del menú. Por ejemplo, al presionar ALT + F elige el **archivo** menú.  
  
-   Mostrar barras separadoras para agrupar los comandos relacionados y que los menús sean más legibles.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>Para mostrar una marca de verificación en un comando de menú  
  
-   Establezca su <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad `true`.  
  
     Esto establece también el <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> propiedad `true`. Utilice este procedimiento sólo si desea que el comando de menú aparezca como seleccionado de forma predeterminada, independientemente de si está seleccionada.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Para mostrar una marca de verificación que cambia el estado con cada clic  
  
-   Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad `true`.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Para agregar una imagen a un comando de menú  
  
-   Establece el comando de menú <xref:System.Windows.Forms.ToolStripItem.Image%2A> propiedad en el nombre de la imagen. Si el <xref:System.Windows.Forms.ToolStripItemDisplayStyle> propiedad de este comando de menú está establecida en <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, no se puede mostrar la imagen.  
  
> [!NOTE]
>  El margen de la imagen también puede mostrar una marca de verificación si así lo desea. Asimismo, puede establecer el <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad de la imagen que `true`, y aparecerá la imagen con un borde sombreado alrededor de ella en tiempo de ejecución.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Para mostrar una tecla de método abreviado para un comando de menú  
  
-   Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> propiedad a la combinación de teclado deseado, por ejemplo, CTRL+A para el **abierto** comando de menú y establezca el <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> propiedad `true`.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Para mostrar las teclas de método abreviado personalizadas para un comando de menú  
  
-   Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> propiedad a la combinación de teclado deseado, como CTRL + MAYÚS + O en lugar de CTRL + MAYÚS + O y un conjunto el <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> propiedad `true`.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Para mostrar una tecla de acceso para un comando de menú  
  
-   Al establecer el <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad para el comando de menú, escriba una y comercial (&) delante de la letra que desee que esté subrayada como la clave de acceso. Por ejemplo, si escribe `&Open` como el <xref:System.Windows.Forms.ToolStripItem.Text%2A> dará como resultado un comando de menú que aparece como propiedad de un elemento de menú <u>O</u>lápiz.
  
     Para navegar a este comando de menú, presione ALT para dar el foco a la <xref:System.Windows.Forms.MenuStrip>y presione la tecla de acceso del nombre del menú. Cuando el menú se abre y muestra los elementos con las teclas de acceso, basta con presionar la tecla de acceso para seleccionar el comando de menú.  
  
> [!NOTE]
>  Evite definir teclas de acceso duplicadas, como definir ALT+F dos veces en el mismo sistema de menú. No se puede garantizar el orden de selección de las claves de acceso duplicadas.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Para mostrar una barra de separación entre los comandos de menú  
  
-   Después de definir su <xref:System.Windows.Forms.MenuStrip> y los elementos va a contener, utilice el <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> o <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> método para agregar los comandos de menú y <xref:System.Windows.Forms.ToolStripSeparator> controles a la <xref:System.Windows.Forms.MenuStrip> en el orden que desee.  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,   
    ' and the Save and Exit menu commands to the top-level File menu,   
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,   
    // and the Save and Exit menu commands to the top-level File menu,   
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
