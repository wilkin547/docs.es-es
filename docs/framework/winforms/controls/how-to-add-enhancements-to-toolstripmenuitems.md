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
ms.openlocfilehash: 68a926eba184d12d58e537d8db0a5baefb0fbe95
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719330"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="20ac4-102">Procedimiento Agregar mejoras a ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="20ac4-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="20ac4-103">Puede mejorar la facilidad de uso <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> controles de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="20ac4-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
-   <span data-ttu-id="20ac4-104">Agregar marcas de verificación para designar si una característica está activada o desactivada, por ejemplo, si se muestra una regla a lo largo del margen de una aplicación de procesamiento de texto, o para indicar qué archivo en una lista de archivos se muestra, como en un **ventana** menú.</span><span class="sxs-lookup"><span data-stu-id="20ac4-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
-   <span data-ttu-id="20ac4-105">Agregar imágenes que representan visualmente los comandos de menú.</span><span class="sxs-lookup"><span data-stu-id="20ac4-105">Add images that visually represent menu commands.</span></span>  
  
-   <span data-ttu-id="20ac4-106">Mostrar teclas de método abreviado para proporcionar una alternativa de teclado para el mouse para llevar a cabo los comandos.</span><span class="sxs-lookup"><span data-stu-id="20ac4-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="20ac4-107">Por ejemplo, al presionar CTRL+C realiza el **copia** comando.</span><span class="sxs-lookup"><span data-stu-id="20ac4-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
-   <span data-ttu-id="20ac4-108">Para mostrar las teclas de acceso para proporcionar una alternativa de teclado para el mouse para la navegación del menú.</span><span class="sxs-lookup"><span data-stu-id="20ac4-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="20ac4-109">Por ejemplo, al presionar ALT + F elige el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="20ac4-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
-   <span data-ttu-id="20ac4-110">Mostrar barras separadoras para agrupar los comandos relacionados y que los menús sean más legibles.</span><span class="sxs-lookup"><span data-stu-id="20ac4-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="20ac4-111">Para mostrar una marca de verificación en un comando de menú</span><span class="sxs-lookup"><span data-stu-id="20ac4-111">To display a check mark on a menu command</span></span>  
  
-   <span data-ttu-id="20ac4-112">Establezca su <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="20ac4-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="20ac4-113">Esto establece también el <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="20ac4-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="20ac4-114">Utilice este procedimiento sólo si desea que el comando de menú aparezca como seleccionado de forma predeterminada, independientemente de si está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="20ac4-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="20ac4-115">Para mostrar una marca de verificación que cambia el estado con cada clic</span><span class="sxs-lookup"><span data-stu-id="20ac4-115">To display a check mark that changes state with each click</span></span>  
  
-   <span data-ttu-id="20ac4-116">Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="20ac4-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="20ac4-117">Para agregar una imagen a un comando de menú</span><span class="sxs-lookup"><span data-stu-id="20ac4-117">To add an image to a menu command</span></span>  
  
-   <span data-ttu-id="20ac4-118">Establece el comando de menú <xref:System.Windows.Forms.ToolStripItem.Image%2A> propiedad en el nombre de la imagen.</span><span class="sxs-lookup"><span data-stu-id="20ac4-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="20ac4-119">Si el <xref:System.Windows.Forms.ToolStripItemDisplayStyle> propiedad de este comando de menú está establecida en <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, no se puede mostrar la imagen.</span><span class="sxs-lookup"><span data-stu-id="20ac4-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20ac4-120">El margen de la imagen también puede mostrar una marca de verificación si así lo desea.</span><span class="sxs-lookup"><span data-stu-id="20ac4-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="20ac4-121">Asimismo, puede establecer el <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad de la imagen que `true`, y aparecerá la imagen con un borde sombreado alrededor de ella en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="20ac4-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="20ac4-122">Para mostrar una tecla de método abreviado para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="20ac4-122">To display a shortcut key for a menu command</span></span>  
  
-   <span data-ttu-id="20ac4-123">Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> propiedad a la combinación de teclado deseado, por ejemplo, CTRL+A para el **abierto** comando de menú y establezca el <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="20ac4-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="20ac4-124">Para mostrar las teclas de método abreviado personalizadas para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="20ac4-124">To display custom shortcut keys for a menu command</span></span>  
  
-   <span data-ttu-id="20ac4-125">Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> propiedad a la combinación de teclado deseado, como CTRL + MAYÚS + O en lugar de CTRL + MAYÚS + O y un conjunto el <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="20ac4-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="20ac4-126">Para mostrar una tecla de acceso para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="20ac4-126">To display an access key for a menu command</span></span>  
  
-   <span data-ttu-id="20ac4-127">Al establecer el <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad para el comando de menú, escriba una y comercial (&) delante de la letra que desee que esté subrayada como la clave de acceso.</span><span class="sxs-lookup"><span data-stu-id="20ac4-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="20ac4-128">Por ejemplo, si escribe `&Open` como el <xref:System.Windows.Forms.ToolStripItem.Text%2A> dará como resultado un comando de menú que aparece como propiedad de un elemento de menú <u>O</u>lápiz.</span><span class="sxs-lookup"><span data-stu-id="20ac4-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="20ac4-129">Para navegar a este comando de menú, presione ALT para dar el foco a la <xref:System.Windows.Forms.MenuStrip>y presione la tecla de acceso del nombre del menú.</span><span class="sxs-lookup"><span data-stu-id="20ac4-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="20ac4-130">Cuando el menú se abre y muestra los elementos con las teclas de acceso, basta con presionar la tecla de acceso para seleccionar el comando de menú.</span><span class="sxs-lookup"><span data-stu-id="20ac4-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20ac4-131">Evite definir teclas de acceso duplicadas, como definir ALT+F dos veces en el mismo sistema de menú.</span><span class="sxs-lookup"><span data-stu-id="20ac4-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="20ac4-132">No se puede garantizar el orden de selección de las claves de acceso duplicadas.</span><span class="sxs-lookup"><span data-stu-id="20ac4-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="20ac4-133">Para mostrar una barra de separación entre los comandos de menú</span><span class="sxs-lookup"><span data-stu-id="20ac4-133">To display a separator bar between menu commands</span></span>  
  
-   <span data-ttu-id="20ac4-134">Después de definir su <xref:System.Windows.Forms.MenuStrip> y los elementos va a contener, utilice el <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> o <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> método para agregar los comandos de menú y <xref:System.Windows.Forms.ToolStripSeparator> controles a la <xref:System.Windows.Forms.MenuStrip> en el orden que desee.</span><span class="sxs-lookup"><span data-stu-id="20ac4-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="20ac4-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="20ac4-135">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="20ac4-136">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="20ac4-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
