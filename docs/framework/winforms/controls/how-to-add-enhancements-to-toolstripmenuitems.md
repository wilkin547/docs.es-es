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
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="26e53-102">Procedimiento para agregar mejoras a ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="26e53-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="26e53-103">Puede mejorar la facilidad de uso <xref:System.Windows.Forms.MenuStrip> de <xref:System.Windows.Forms.ContextMenuStrip> los controles y de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="26e53-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="26e53-104">Agregue marcas de verificación para designar si una característica está activada o desactivada, por ejemplo, si se muestra una regla a lo largo del margen de una aplicación de procesamiento de texto, o para indicar el archivo de una lista de archivos que se muestra, como en el menú **ventana** .</span><span class="sxs-lookup"><span data-stu-id="26e53-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="26e53-105">Agregue imágenes que representen visualmente los comandos de menú.</span><span class="sxs-lookup"><span data-stu-id="26e53-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="26e53-106">Mostrar teclas de método abreviado para proporcionar una alternativa de teclado al mouse para realizar comandos.</span><span class="sxs-lookup"><span data-stu-id="26e53-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="26e53-107">Por ejemplo, al presionar CTRL + C se realiza el comando **copiar** .</span><span class="sxs-lookup"><span data-stu-id="26e53-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="26e53-108">Mostrar teclas de acceso para proporcionar una alternativa de teclado al mouse para la navegación del menú.</span><span class="sxs-lookup"><span data-stu-id="26e53-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="26e53-109">Por ejemplo, al presionar ALT + F, se elige el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="26e53-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="26e53-110">Mostrar barras separadoras para agrupar comandos relacionados y hacer que los menús sean más legibles.</span><span class="sxs-lookup"><span data-stu-id="26e53-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="26e53-111">Para mostrar una marca de verificación en un comando de menú</span><span class="sxs-lookup"><span data-stu-id="26e53-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="26e53-112">Establezca su <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad en `true`.</span><span class="sxs-lookup"><span data-stu-id="26e53-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="26e53-113">Esto también establece la <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> propiedad en `true`.</span><span class="sxs-lookup"><span data-stu-id="26e53-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="26e53-114">Utilice este procedimiento solo si desea que el comando de menú aparezca como activado de forma predeterminada, independientemente de si está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="26e53-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="26e53-115">Para mostrar una marca de verificación que cambia el estado con cada clic</span><span class="sxs-lookup"><span data-stu-id="26e53-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="26e53-116">Establezca la propiedad del comando <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> de menú `true`en.</span><span class="sxs-lookup"><span data-stu-id="26e53-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="26e53-117">Para agregar una imagen a un comando de menú</span><span class="sxs-lookup"><span data-stu-id="26e53-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="26e53-118">Establezca la propiedad del <xref:System.Windows.Forms.ToolStripItem.Image%2A> comando de menú en el nombre de la imagen.</span><span class="sxs-lookup"><span data-stu-id="26e53-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="26e53-119">Si la <xref:System.Windows.Forms.ToolStripItemDisplayStyle> propiedad de este comando de menú está establecida <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> en <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>o, no se puede mostrar la imagen.</span><span class="sxs-lookup"><span data-stu-id="26e53-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26e53-120">El margen de la imagen también puede mostrar una marca de verificación si lo prefiere.</span><span class="sxs-lookup"><span data-stu-id="26e53-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="26e53-121">Además, puede establecer la <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad de la imagen en `true`y la imagen aparecerá con un borde sombreado alrededor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="26e53-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="26e53-122">Para mostrar una tecla de método abreviado para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="26e53-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="26e53-123">Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> del comando de menú en la combinación de teclado deseada, como Ctrl + O para el comando de menú **abrir** , y <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> establezca la `true`propiedad en.</span><span class="sxs-lookup"><span data-stu-id="26e53-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="26e53-124">Para mostrar las teclas de método abreviado personalizadas para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="26e53-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="26e53-125">Establezca la propiedad del comando <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> de menú en la combinación de teclado deseada, como Ctrl + Mayús + O en lugar de Mayús + Ctrl + o, y <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> establezca la `true`propiedad en.</span><span class="sxs-lookup"><span data-stu-id="26e53-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="26e53-126">Para mostrar una tecla de acceso para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="26e53-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="26e53-127">Cuando establezca la <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad para el comando de menú, escriba una y comercial (&) antes de la letra que desea que esté subrayada como tecla de acceso.</span><span class="sxs-lookup"><span data-stu-id="26e53-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="26e53-128">Por ejemplo, si `&Open` escribe como <xref:System.Windows.Forms.ToolStripItem.Text%2A> la propiedad de un elemento de menú, se generará un comando de menú que aparece como <u>O</u>lápiz.</span><span class="sxs-lookup"><span data-stu-id="26e53-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="26e53-129">Para navegar a este comando de menú, presione Alt para dar el <xref:System.Windows.Forms.MenuStrip>foco al y presione la tecla de acceso del nombre del menú.</span><span class="sxs-lookup"><span data-stu-id="26e53-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="26e53-130">Cuando se abre el menú y muestra los elementos con teclas de acceso, solo tiene que presionar la tecla de acceso para seleccionar el comando de menú.</span><span class="sxs-lookup"><span data-stu-id="26e53-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26e53-131">Evite definir claves de acceso duplicadas, como la definición de ALT + F dos veces en el mismo sistema de menús.</span><span class="sxs-lookup"><span data-stu-id="26e53-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="26e53-132">No se puede garantizar el orden de selección de las claves de acceso duplicadas.</span><span class="sxs-lookup"><span data-stu-id="26e53-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="26e53-133">Para mostrar una barra de separación entre los comandos de menú</span><span class="sxs-lookup"><span data-stu-id="26e53-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="26e53-134">Después <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MenuStrip> de definir el y los elementos que contendrá, use el <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> método <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> o para agregar los comandos de menú <xref:System.Windows.Forms.ToolStripSeparator> y los controles al en el orden que desee.</span><span class="sxs-lookup"><span data-stu-id="26e53-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="26e53-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="26e53-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="26e53-136">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="26e53-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
