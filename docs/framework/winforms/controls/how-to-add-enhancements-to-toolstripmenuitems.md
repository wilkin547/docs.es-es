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
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="375d7-102">Cómo: Agregar mejoras a ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="375d7-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="375d7-103">Puede mejorar la facilidad <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> de uso y los controles de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="375d7-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="375d7-104">Agregue marcas de verificación para designar si una entidad está activada o desactivada, como si se muestra una regla a lo largo del margen de una aplicación de procesamiento de texto o para indicar qué archivo de una lista de archivos se muestra, como en un menú **Ventana.**</span><span class="sxs-lookup"><span data-stu-id="375d7-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="375d7-105">Agregue imágenes que representen visualmente los comandos de menú.</span><span class="sxs-lookup"><span data-stu-id="375d7-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="375d7-106">Mostrar teclas de método abreviado para proporcionar una alternativa de teclado al ratón para realizar comandos.</span><span class="sxs-lookup"><span data-stu-id="375d7-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="375d7-107">Por ejemplo, al presionar CTRL+C se realiza el comando **Copiar.**</span><span class="sxs-lookup"><span data-stu-id="375d7-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="375d7-108">Visualice las teclas de acceso para proporcionar una alternativa de teclado al ratón para la navegación del menú.</span><span class="sxs-lookup"><span data-stu-id="375d7-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="375d7-109">Por ejemplo, al presionar ALT+F se selecciona el menú **Archivo.**</span><span class="sxs-lookup"><span data-stu-id="375d7-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="375d7-110">Mostrar barras separadoras para agrupar comandos relacionados y hacer que los menús sean más legibles.</span><span class="sxs-lookup"><span data-stu-id="375d7-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="375d7-111">Para mostrar una marca de verificación en un comando de menú</span><span class="sxs-lookup"><span data-stu-id="375d7-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="375d7-112">Establezca <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> su `true`propiedad en .</span><span class="sxs-lookup"><span data-stu-id="375d7-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="375d7-113">Esto también <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> establece `true`la propiedad en .</span><span class="sxs-lookup"><span data-stu-id="375d7-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="375d7-114">Utilice este procedimiento solo si desea que el comando de menú aparezca como activado de forma predeterminada, independientemente de si está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="375d7-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="375d7-115">Para mostrar una marca de verificación que cambia de estado con cada clic</span><span class="sxs-lookup"><span data-stu-id="375d7-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="375d7-116">Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> del `true`comando de menú en .</span><span class="sxs-lookup"><span data-stu-id="375d7-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="375d7-117">Para añadir una imagen a un comando de menú</span><span class="sxs-lookup"><span data-stu-id="375d7-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="375d7-118">Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Image%2A> del comando de menú en el nombre de la imagen.</span><span class="sxs-lookup"><span data-stu-id="375d7-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="375d7-119">Si <xref:System.Windows.Forms.ToolStripItemDisplayStyle> la propiedad de este <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> comando <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>de menú está establecida en o , la imagen no se puede mostrar.</span><span class="sxs-lookup"><span data-stu-id="375d7-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="375d7-120">El margen de imagen también puede mostrar una marca de verificación si así lo desea.</span><span class="sxs-lookup"><span data-stu-id="375d7-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="375d7-121">Además, puede <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> establecer la `true`propiedad de la imagen en , y la imagen aparecerá con un borde sombreado alrededor de ella en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="375d7-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="375d7-122">Para mostrar una tecla de método abreviado para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="375d7-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="375d7-123">Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> del comando de menú en la combinación de teclado deseada, <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> como `true`CTRL+O para el comando de menú **Abrir,** y establezca la propiedad en .</span><span class="sxs-lookup"><span data-stu-id="375d7-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="375d7-124">Para mostrar las teclas de método abreviado personalizadas para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="375d7-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="375d7-125">Establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> del comando de menú en la combinación de teclado deseada, como CTRL+MAYO+O en lugar de MAYÚS+CTRL+O, y establezca la propiedad en <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> . `true`</span><span class="sxs-lookup"><span data-stu-id="375d7-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="375d7-126">Para mostrar una tecla de acceso para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="375d7-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="375d7-127">Cuando establezca <xref:System.Windows.Forms.ToolStripItem.Text%2A> la propiedad para el comando de menú, escriba una y unana (&) antes de la letra que desea subrayar como clave de acceso.</span><span class="sxs-lookup"><span data-stu-id="375d7-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="375d7-128">Por ejemplo, `&Open` al <xref:System.Windows.Forms.ToolStripItem.Text%2A> escribir como la propiedad de un elemento de menú se producirá un comando de menú que aparece como lápiz <u>O.</u></span><span class="sxs-lookup"><span data-stu-id="375d7-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="375d7-129">Para navegar a este comando de menú, <xref:System.Windows.Forms.MenuStrip>presione ALT para dar el foco al archivo , y presione la tecla de acceso del nombre del menú.</span><span class="sxs-lookup"><span data-stu-id="375d7-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="375d7-130">Cuando se abre el menú y muestra elementos con teclas de acceso, sólo tiene que pulsar la tecla de acceso para seleccionar el comando de menú.</span><span class="sxs-lookup"><span data-stu-id="375d7-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="375d7-131">Evite definir claves de acceso duplicadas, como definir ALT+F dos veces en el mismo sistema de menús.</span><span class="sxs-lookup"><span data-stu-id="375d7-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="375d7-132">No se puede garantizar el orden de selección de claves de acceso duplicadas.</span><span class="sxs-lookup"><span data-stu-id="375d7-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="375d7-133">Para mostrar una barra separadora entre los comandos de menú</span><span class="sxs-lookup"><span data-stu-id="375d7-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="375d7-134">Después de <xref:System.Windows.Forms.MenuStrip> definir su y los <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> elementos que contendrá, utilice el método o <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> para agregar los comandos de menú y <xref:System.Windows.Forms.ToolStripSeparator> controles al <xref:System.Windows.Forms.MenuStrip> orden que desee.</span><span class="sxs-lookup"><span data-stu-id="375d7-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="375d7-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="375d7-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="375d7-136">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="375d7-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
