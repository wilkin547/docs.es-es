---
title: 'Cómo: Agregar mejoras a ToolStripMenuItems'
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
ms.openlocfilehash: 61a79b9bbe101d7bf694240bdffdecee5187adf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182322"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Cómo: Agregar mejoras a ToolStripMenuItems
Puede mejorar la facilidad <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> de uso y los controles de las siguientes maneras:  
  
- Agregue marcas de verificación para designar si una entidad está activada o desactivada, como si se muestra una regla a lo largo del margen de una aplicación de procesamiento de texto o para indicar qué archivo de una lista de archivos se muestra, como en un menú **Ventana.**  
  
- Agregue imágenes que representen visualmente los comandos de menú.  
  
- Mostrar teclas de método abreviado para proporcionar una alternativa de teclado al ratón para realizar comandos. Por ejemplo, al presionar CTRL+C se realiza el comando **Copiar.**  
  
- Visualice las teclas de acceso para proporcionar una alternativa de teclado al ratón para la navegación del menú. Por ejemplo, al presionar ALT+F se selecciona el menú **Archivo.**  
  
- Mostrar barras separadoras para agrupar comandos relacionados y hacer que los menús sean más legibles.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>Para mostrar una marca de verificación en un comando de menú  
  
- Establezca <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> su `true`propiedad en .  
  
     Esto también <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> establece `true`la propiedad en . Utilice este procedimiento solo si desea que el comando de menú aparezca como activado de forma predeterminada, independientemente de si está seleccionado.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Para mostrar una marca de verificación que cambia de estado con cada clic  
  
- Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> del `true`comando de menú en .  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Para añadir una imagen a un comando de menú  
  
- Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Image%2A> del comando de menú en el nombre de la imagen. Si <xref:System.Windows.Forms.ToolStripItemDisplayStyle> la propiedad de este <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> comando <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>de menú está establecida en o , la imagen no se puede mostrar.  
  
> [!NOTE]
> El margen de imagen también puede mostrar una marca de verificación si así lo desea. Además, puede <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> establecer la `true`propiedad de la imagen en , y la imagen aparecerá con un borde sombreado alrededor de ella en tiempo de ejecución.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Para mostrar una tecla de método abreviado para un comando de menú  
  
- Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> del comando de menú en la combinación de teclado deseada, <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> como `true`CTRL+O para el comando de menú **Abrir,** y establezca la propiedad en .  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Para mostrar las teclas de método abreviado personalizadas para un comando de menú  
  
- Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> del comando de menú en la combinación de teclado deseada, como CTRL+MAYO+O en lugar de MAYÚS+CTRL+O, y establezca la propiedad en <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> . `true`  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Para mostrar una tecla de acceso para un comando de menú  
  
- Cuando establezca <xref:System.Windows.Forms.ToolStripItem.Text%2A> la propiedad para el comando de menú, escriba una y unana (&) antes de la letra que desea subrayar como clave de acceso. Por ejemplo, `&Open` al <xref:System.Windows.Forms.ToolStripItem.Text%2A> escribir como la propiedad de un elemento de menú se producirá un comando de menú que aparece como lápiz <u>O.</u>
  
     Para navegar a este comando de menú, <xref:System.Windows.Forms.MenuStrip>presione ALT para dar el foco al archivo , y presione la tecla de acceso del nombre del menú. Cuando se abre el menú y muestra elementos con teclas de acceso, sólo tiene que pulsar la tecla de acceso para seleccionar el comando de menú.  
  
> [!NOTE]
> Evite definir claves de acceso duplicadas, como definir ALT+F dos veces en el mismo sistema de menús. No se puede garantizar el orden de selección de claves de acceso duplicadas.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Para mostrar una barra separadora entre los comandos de menú  
  
- Después de <xref:System.Windows.Forms.MenuStrip> definir su y los <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> elementos que contendrá, utilice el método o <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> para agregar los comandos de menú y <xref:System.Windows.Forms.ToolStripSeparator> controles al <xref:System.Windows.Forms.MenuStrip> orden que desee.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
