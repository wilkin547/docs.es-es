---
title: "Cómo: Agregar mejoras a ToolStripMenuItems"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 075370b56ab9e73434394e15a25cd5ce6cd043bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="57657-102">Cómo: Agregar mejoras a ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="57657-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="57657-103">Puede mejorar la facilidad de uso de <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> controles de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="57657-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
-   <span data-ttu-id="57657-104">Agregar marcas de verificación para designar si una característica está activada o desactivada, como si se muestra una regla junto al margen de una aplicación de procesamiento de texto, o para indicar qué archivo en una lista de archivos se muestra, en un **ventana** menú.</span><span class="sxs-lookup"><span data-stu-id="57657-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
-   <span data-ttu-id="57657-105">Agregar imágenes que representan visualmente los comandos de menú.</span><span class="sxs-lookup"><span data-stu-id="57657-105">Add images that visually represent menu commands.</span></span>  
  
-   <span data-ttu-id="57657-106">Mostrar teclas de método abreviado para proporcionar una alternativa de teclado para el mouse para llevar a cabo comandos.</span><span class="sxs-lookup"><span data-stu-id="57657-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="57657-107">Por ejemplo, al presionar CTRL+C realiza el **copia** comando.</span><span class="sxs-lookup"><span data-stu-id="57657-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
-   <span data-ttu-id="57657-108">Muestre las teclas de acceso para proporcionar una alternativa de teclado para el mouse para la exploración del menú.</span><span class="sxs-lookup"><span data-stu-id="57657-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="57657-109">Por ejemplo, al presionar ALT + F elige el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="57657-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
-   <span data-ttu-id="57657-110">Mostrar barras separadoras para agrupar los comandos relacionados y mejorar la legibilidad de los menús.</span><span class="sxs-lookup"><span data-stu-id="57657-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="57657-111">Para mostrar una marca de verificación en un comando de menú</span><span class="sxs-lookup"><span data-stu-id="57657-111">To display a check mark on a menu command</span></span>  
  
-   <span data-ttu-id="57657-112">Establecer su <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="57657-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="57657-113">También se configura el <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="57657-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="57657-114">Utilice este procedimiento únicamente si desea que el comando de menú que aparezca como seleccionado de manera predeterminada, independientemente de si está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="57657-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="57657-115">Para mostrar una marca de verificación cambia el estado con cada clic</span><span class="sxs-lookup"><span data-stu-id="57657-115">To display a check mark that changes state with each click</span></span>  
  
-   <span data-ttu-id="57657-116">Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="57657-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="57657-117">Para agregar una imagen a un comando de menú</span><span class="sxs-lookup"><span data-stu-id="57657-117">To add an image to a menu command</span></span>  
  
-   <span data-ttu-id="57657-118">Establece el comando de menú <xref:System.Windows.Forms.ToolStripItem.Image%2A> propiedad en el nombre de la imagen.</span><span class="sxs-lookup"><span data-stu-id="57657-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="57657-119">Si el <xref:System.Windows.Forms.ToolStripItemDisplayStyle> propiedad de este comando de menú está establecida en <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, no se puede mostrar la imagen.</span><span class="sxs-lookup"><span data-stu-id="57657-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57657-120">El margen de la imagen también puede mostrar una marca de verificación si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="57657-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="57657-121">Además, puede establecer la <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad de la imagen a `true`, y la imagen se mostrará con un borde sombreado alrededor de ella en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="57657-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="57657-122">Para mostrar una tecla de método abreviado para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="57657-122">To display a shortcut key for a menu command</span></span>  
  
-   <span data-ttu-id="57657-123">Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> propiedad a la combinación de teclado deseado, por ejemplo, CTRL+A para la **abiertos** comando de menú y establezca el <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> propiedad a `true`.</span><span class="sxs-lookup"><span data-stu-id="57657-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="57657-124">Para mostrar las teclas de método abreviado personalizadas para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="57657-124">To display custom shortcut keys for a menu command</span></span>  
  
-   <span data-ttu-id="57657-125">Establece el comando de menú <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> propiedad a la combinación de teclado deseado, como CTRL + MAYÚS + O en lugar de CTRL + MAYÚS + O y un conjunto el <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="57657-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="57657-126">Para mostrar una tecla de acceso para un comando de menú</span><span class="sxs-lookup"><span data-stu-id="57657-126">To display an access key for a menu command</span></span>  
  
-   <span data-ttu-id="57657-127">Al establecer el <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad para el comando de menú, escriba una y comercial (&) delante de la letra que quiere que esté subrayada como tecla de acceso.</span><span class="sxs-lookup"><span data-stu-id="57657-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="57657-128">Por ejemplo, si escribe `&Open` como el <xref:System.Windows.Forms.ToolStripItem.Text%2A> dará como resultado un comando de menú que aparece como propiedad de un elemento de menú **O**lápiz.</span><span class="sxs-lookup"><span data-stu-id="57657-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as **O**pen.</span></span>  
  
     <span data-ttu-id="57657-129">Para navegar a este comando de menú, presione ALT para asignar el foco a la <xref:System.Windows.Forms.MenuStrip>y presione la tecla de acceso del nombre del menú.</span><span class="sxs-lookup"><span data-stu-id="57657-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="57657-130">Cuando el menú se abre y muestra los elementos con las teclas de acceso, sólo necesitará presionar la tecla de acceso para seleccionar el comando de menú.</span><span class="sxs-lookup"><span data-stu-id="57657-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57657-131">Evite la definición de teclas de acceso duplicadas, como definir ALT+F dos veces en el mismo sistema de menús.</span><span class="sxs-lookup"><span data-stu-id="57657-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="57657-132">No se puede garantizar el orden de selección de teclas de acceso duplicadas.</span><span class="sxs-lookup"><span data-stu-id="57657-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="57657-133">Para mostrar una barra separadora entre los comandos de menú</span><span class="sxs-lookup"><span data-stu-id="57657-133">To display a separator bar between menu commands</span></span>  
  
-   <span data-ttu-id="57657-134">Después de definir la <xref:System.Windows.Forms.MenuStrip> y los elementos va a contener, use la <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> o <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> método para agregar los comandos de menú y <xref:System.Windows.Forms.ToolStripSeparator> controles a la <xref:System.Windows.Forms.MenuStrip> en el orden que desee.</span><span class="sxs-lookup"><span data-stu-id="57657-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="57657-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="57657-135">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="57657-136">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="57657-136">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
