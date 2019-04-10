---
title: Filtrar para habilitar la vista en mosaico en un control ListView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tile view feature
- tiling
- Windows Forms, controls
- ListView control [Windows Forms], tile view
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
ms.openlocfilehash: 0d47eddbc1d9a4efc7f1e4644136ac6621088396
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215032"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a><span data-ttu-id="85dac-102">Filtrar para habilitar la vista en mosaico en un control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85dac-102">How to: Enable Tile View in a Windows Forms ListView Control</span></span>
<span data-ttu-id="85dac-103">Con la característica de vista de mosaico del control <xref:System.Windows.Forms.ListView>, puede proporcionar equilibrio visual entre la información gráfica y de texto.</span><span class="sxs-lookup"><span data-stu-id="85dac-103">With the tile view feature of the <xref:System.Windows.Forms.ListView> control, you can provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="85dac-104">La información de texto que se muestra para un elemento en la vista de mosaico es igual que la información de columna definida para la vista de detalles.</span><span class="sxs-lookup"><span data-stu-id="85dac-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="85dac-105">La vista de mosaico funciona en combinación con las características de marca de inserción o agrupación del control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="85dac-105">Tile view works in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="85dac-106">La vista de mosaico usa un icono de 32 x 32 píxeles y varias líneas de texto, tal y como se muestra en las siguientes imágenes.</span><span class="sxs-lookup"><span data-stu-id="85dac-106">The tile view uses a 32 x 32 pixel icon and several lines of text, as shown in the following images.</span></span>  
  
 <span data-ttu-id="85dac-107">![Vista en mosaico en un ListView Control](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "icono Ver iconos y texto")</span><span class="sxs-lookup"><span data-stu-id="85dac-107">![Tile View in a ListView Control](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>  
 
 <span data-ttu-id="85dac-108">Para habilitar la vista de mosaico, establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> en <xref:System.Windows.Forms.View.Tile>.</span><span class="sxs-lookup"><span data-stu-id="85dac-108">To enable tile view, set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Tile>.</span></span> <span data-ttu-id="85dac-109">Puede ajustar el tamaño de los mosaicos estableciendo la propiedad <xref:System.Windows.Forms.ListView.TileSize%2A>, y el número de líneas de texto que se muestran en el mosaico ajustando la colección <xref:System.Windows.Forms.ListView.Columns%2A>.</span><span class="sxs-lookup"><span data-stu-id="85dac-109">You can adjust the size of the tiles by setting the <xref:System.Windows.Forms.ListView.TileSize%2A> property, and the number of text lines displayed in the tile by adjusting the <xref:System.Windows.Forms.ListView.Columns%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85dac-110">La vista de mosaico solo está disponible en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="85dac-110">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="85dac-111">En sistemas operativos anteriores, el código relacionado con la vista de mosaico no tiene ningún efecto y el control <xref:System.Windows.Forms.ListView> se muestra en la vista de iconos grandes.</span><span class="sxs-lookup"><span data-stu-id="85dac-111">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="85dac-112">Para obtener más información, consulta <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="85dac-112">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-set-tile-view-programmatically"></a><span data-ttu-id="85dac-113">Para establecer la vista de mosaico mediante programación</span><span class="sxs-lookup"><span data-stu-id="85dac-113">To set tile view programmatically</span></span>  
  
1.  <span data-ttu-id="85dac-114">Use la enumeración <xref:System.Windows.Forms.View> del control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="85dac-114">Use the <xref:System.Windows.Forms.View> enumeration of the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a><span data-ttu-id="85dac-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85dac-115">Example</span></span>  
 <span data-ttu-id="85dac-116">En el siguiente ejemplo de código completo se muestra la vista de mosaico con mosaicos modificados para mostrar tres líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="85dac-116">The following complete code example demonstrates Tile view with tiles modified to show three lines of text.</span></span> <span data-ttu-id="85dac-117">El tamaño del mosaico se ha adaptado para evitar el ajuste de línea.</span><span class="sxs-lookup"><span data-stu-id="85dac-117">The tile size has been adjusted to prevent line-wrapping.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="85dac-118">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="85dac-118">Compiling the Code</span></span>  
 <span data-ttu-id="85dac-119">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="85dac-119">This example requires:</span></span>  
  
-   <span data-ttu-id="85dac-120">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="85dac-120">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="85dac-121">Un archivo de icono llamado book.ico en el mismo directorio que el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="85dac-121">An icon file named book.ico in the same directory as the executable file.</span></span>  
  
 <span data-ttu-id="85dac-122">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="85dac-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="85dac-123">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="85dac-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85dac-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="85dac-124">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="85dac-125">Control ListView</span><span class="sxs-lookup"><span data-stu-id="85dac-125">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="85dac-126">Información general sobre el control ListView</span><span class="sxs-lookup"><span data-stu-id="85dac-126">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
