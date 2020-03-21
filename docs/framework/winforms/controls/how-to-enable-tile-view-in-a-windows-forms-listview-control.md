---
title: Habilitar vista de mosaico en ListView Control
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
ms.openlocfilehash: 1478ba5e4f175cd7d9ec7ab5c3c4bc9050ce02fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182153"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a><span data-ttu-id="fa6c9-102">Cómo: Habilitar la vista en mosaico en un control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa6c9-102">How to: Enable Tile View in a Windows Forms ListView Control</span></span>
<span data-ttu-id="fa6c9-103">Con la característica de vista de mosaico del control <xref:System.Windows.Forms.ListView>, puede proporcionar equilibrio visual entre la información gráfica y de texto.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-103">With the tile view feature of the <xref:System.Windows.Forms.ListView> control, you can provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="fa6c9-104">La información de texto que se muestra para un elemento en la vista de mosaico es igual que la información de columna definida para la vista de detalles.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="fa6c9-105">La vista de mosaico funciona en combinación con las características de marca de inserción o agrupación del control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-105">Tile view works in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="fa6c9-106">La vista de mosaico usa un icono de 32 x 32 píxeles y varias líneas de texto, tal y como se muestra en las siguientes imágenes.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-106">The tile view uses a 32 x 32 pixel icon and several lines of text, as shown in the following images.</span></span>  
  
 <span data-ttu-id="fa6c9-107">![Vista en mosaico de un control ListView](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "Texto e iconos de la vista de mosaico")</span><span class="sxs-lookup"><span data-stu-id="fa6c9-107">![Tile View in a ListView Control](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>  

 <span data-ttu-id="fa6c9-108">Para habilitar la vista de mosaico, establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> en <xref:System.Windows.Forms.View.Tile>.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-108">To enable tile view, set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Tile>.</span></span> <span data-ttu-id="fa6c9-109">Puede ajustar el tamaño de los mosaicos estableciendo la propiedad <xref:System.Windows.Forms.ListView.TileSize%2A>, y el número de líneas de texto que se muestran en el mosaico ajustando la colección <xref:System.Windows.Forms.ListView.Columns%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-109">You can adjust the size of the tiles by setting the <xref:System.Windows.Forms.ListView.TileSize%2A> property, and the number of text lines displayed in the tile by adjusting the <xref:System.Windows.Forms.ListView.Columns%2A> collection.</span></span>  
  
### <a name="to-set-tile-view-programmatically"></a><span data-ttu-id="fa6c9-110">Para establecer la vista de mosaico mediante programación</span><span class="sxs-lookup"><span data-stu-id="fa6c9-110">To set tile view programmatically</span></span>  
  
1. <span data-ttu-id="fa6c9-111">Use la enumeración <xref:System.Windows.Forms.View> del control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-111">Use the <xref:System.Windows.Forms.View> enumeration of the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a><span data-ttu-id="fa6c9-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa6c9-112">Example</span></span>  
 <span data-ttu-id="fa6c9-113">En el siguiente ejemplo de código completo se muestra la vista de mosaico con mosaicos modificados para mostrar tres líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-113">The following complete code example demonstrates Tile view with tiles modified to show three lines of text.</span></span> <span data-ttu-id="fa6c9-114">El tamaño del mosaico se ha adaptado para evitar el ajuste de línea.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-114">The tile size has been adjusted to prevent line-wrapping.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa6c9-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="fa6c9-115">Compiling the Code</span></span>  
 <span data-ttu-id="fa6c9-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="fa6c9-116">This example requires:</span></span>  
  
- <span data-ttu-id="fa6c9-117">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-117">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="fa6c9-118">Un archivo de icono llamado book.ico en el mismo directorio que el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-118">An icon file named book.ico in the same directory as the executable file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6c9-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa6c9-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="fa6c9-120">Control ListView</span><span class="sxs-lookup"><span data-stu-id="fa6c9-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="fa6c9-121">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="fa6c9-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
