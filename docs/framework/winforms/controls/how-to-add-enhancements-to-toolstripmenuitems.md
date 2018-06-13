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
ms.openlocfilehash: 37843d27211bd07c2749b3e6fc14ec03d7bf570d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529727"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Cómo: Agregar mejoras a ToolStripMenuItems
Puede mejorar la facilidad de uso de <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> controles de las maneras siguientes:  
  
-   Agregar marcas de verificación para designar si una característica está activada o desactivada, como si se muestra una regla junto al margen de una aplicación de procesamiento de texto, o para indicar qué archivo en una lista de archivos se muestra, en un **ventana** menú.  
  
-   Agregar imágenes que representan visualmente los comandos de menú.  
  
-   Mostrar teclas de método abreviado para proporcionar una alternativa de teclado para el mouse para llevar a cabo comandos. Por ejemplo, al presionar CTRL+C realiza el **copia** comando.  
  
-   Muestre las teclas de acceso para proporcionar una alternativa de teclado para el mouse para la exploración del menú. Por ejemplo, al presionar ALT + F elige el **archivo** menú.  
  
-   Mostrar barras separadoras para agrupar los comandos relacionados y mejorar la legibilidad de los menús.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>Para mostrar una marca de verificación en un comando de menú  
  
-   Establecer su <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad `true`.  
  
     También se configura el <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> propiedad `true`. Utilice este procedimiento únicamente si desea que el comando de menú que aparezca como seleccionado de manera predeterminada, independientemente de si está seleccionada.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Para mostrar una marca de verificación cambia el estado con cada clic  
  
-   Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad `true`.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Para agregar una imagen a un comando de menú  
  
-   Establece el comando de menú <xref:System.Windows.Forms.ToolStripItem.Image%2A> propiedad en el nombre de la imagen. Si el <xref:System.Windows.Forms.ToolStripItemDisplayStyle> propiedad de este comando de menú está establecida en <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, no se puede mostrar la imagen.  
  
> [!NOTE]
>  El margen de la imagen también puede mostrar una marca de verificación si así lo decide. Además, puede establecer la <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad de la imagen a `true`, y la imagen se mostrará con un borde sombreado alrededor de ella en tiempo de ejecución.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Para mostrar una tecla de método abreviado para un comando de menú  
  
-   Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> propiedad a la combinación de teclado deseado, por ejemplo, CTRL+A para la **abiertos** comando de menú y establezca el <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> propiedad a `true`.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Para mostrar las teclas de método abreviado personalizadas para un comando de menú  
  
-   Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> propiedad a la combinación de teclado deseado, como CTRL + MAYÚS + O en lugar de CTRL + MAYÚS + O y un conjunto el <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> propiedad `true`.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Para mostrar una tecla de acceso para un comando de menú  
  
-   Al establecer el <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad para el comando de menú, escriba una y comercial (&) delante de la letra que quiere que esté subrayada como tecla de acceso. Por ejemplo, si escribe `&Open` como el <xref:System.Windows.Forms.ToolStripItem.Text%2A> dará como resultado un comando de menú que aparece como propiedad de un elemento de menú **O**lápiz.  
  
     Para navegar a este comando de menú, presione ALT para asignar el foco a la <xref:System.Windows.Forms.MenuStrip>y presione la tecla de acceso del nombre del menú. Cuando el menú se abre y muestra los elementos con las teclas de acceso, sólo necesitará presionar la tecla de acceso para seleccionar el comando de menú.  
  
> [!NOTE]
>  Evite la definición de teclas de acceso duplicadas, como definir ALT+F dos veces en el mismo sistema de menús. No se puede garantizar el orden de selección de teclas de acceso duplicadas.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Para mostrar una barra separadora entre los comandos de menú  
  
-   Después de definir la <xref:System.Windows.Forms.MenuStrip> y los elementos va a contener, use la <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> o <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> método para agregar los comandos de menú y <xref:System.Windows.Forms.ToolStripSeparator> controles a la <xref:System.Windows.Forms.MenuStrip> en el orden que desee.  
  
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
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
