---
title: Procedimiento para agregar mejoras a ToolStripMenuItems
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
ms.openlocfilehash: 9e95c3623bf9bad8395f586392a0557ad1cde880
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912586"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Procedimiento para agregar mejoras a ToolStripMenuItems
Puede mejorar la facilidad de uso <xref:System.Windows.Forms.MenuStrip> de <xref:System.Windows.Forms.ContextMenuStrip> los controles y de las siguientes maneras:  
  
- Agregue marcas de verificación para designar si una característica está activada o desactivada, por ejemplo, si se muestra una regla a lo largo del margen de una aplicación de procesamiento de texto, o para indicar el archivo de una lista de archivos que se muestra, como en el menú **ventana** .  
  
- Agregue imágenes que representen visualmente los comandos de menú.  
  
- Mostrar teclas de método abreviado para proporcionar una alternativa de teclado al mouse para realizar comandos. Por ejemplo, al presionar CTRL + C se realiza el comando **copiar** .  
  
- Mostrar teclas de acceso para proporcionar una alternativa de teclado al mouse para la navegación del menú. Por ejemplo, al presionar ALT + F, se elige el menú **archivo** .  
  
- Mostrar barras separadoras para agrupar comandos relacionados y hacer que los menús sean más legibles.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>Para mostrar una marca de verificación en un comando de menú  
  
- Establezca su <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad en `true`.  
  
     Esto también establece la <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> propiedad en `true`. Utilice este procedimiento solo si desea que el comando de menú aparezca como activado de forma predeterminada, independientemente de si está seleccionado.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Para mostrar una marca de verificación que cambia el estado con cada clic  
  
- Establezca la propiedad del comando <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> de menú `true`en.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Para agregar una imagen a un comando de menú  
  
- Establezca la propiedad del <xref:System.Windows.Forms.ToolStripItem.Image%2A> comando de menú en el nombre de la imagen. Si la <xref:System.Windows.Forms.ToolStripItemDisplayStyle> propiedad de este comando de menú está establecida <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> en <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>o, no se puede mostrar la imagen.  
  
> [!NOTE]
> El margen de la imagen también puede mostrar una marca de verificación si lo prefiere. Además, puede establecer la <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad de la imagen en `true`y la imagen aparecerá con un borde sombreado alrededor en tiempo de ejecución.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Para mostrar una tecla de método abreviado para un comando de menú  
  
- Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> del comando de menú en la combinación de teclado deseada, como Ctrl + O para el comando de menú **abrir** , y <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> establezca la `true`propiedad en.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Para mostrar las teclas de método abreviado personalizadas para un comando de menú  
  
- Establezca la propiedad del comando <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> de menú en la combinación de teclado deseada, como Ctrl + Mayús + O en lugar de Mayús + Ctrl + o, y <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> establezca la `true`propiedad en.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Para mostrar una tecla de acceso para un comando de menú  
  
- Cuando establezca la <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad para el comando de menú, escriba una y comercial (&) antes de la letra que desea que esté subrayada como tecla de acceso. Por ejemplo, si `&Open` escribe como <xref:System.Windows.Forms.ToolStripItem.Text%2A> la propiedad de un elemento de menú, se generará un comando de menú que aparece como <u>O</u>lápiz.
  
     Para navegar a este comando de menú, presione Alt para dar el <xref:System.Windows.Forms.MenuStrip>foco al y presione la tecla de acceso del nombre del menú. Cuando se abre el menú y muestra los elementos con teclas de acceso, solo tiene que presionar la tecla de acceso para seleccionar el comando de menú.  
  
> [!NOTE]
> Evite definir claves de acceso duplicadas, como la definición de ALT + F dos veces en el mismo sistema de menús. No se puede garantizar el orden de selección de las claves de acceso duplicadas.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Para mostrar una barra de separación entre los comandos de menú  
  
- Después <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MenuStrip> de definir el y los elementos que contendrá, use el <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> método <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> o para agregar los comandos de menú <xref:System.Windows.Forms.ToolStripSeparator> y los controles al en el orden que desee.  
  
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
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
