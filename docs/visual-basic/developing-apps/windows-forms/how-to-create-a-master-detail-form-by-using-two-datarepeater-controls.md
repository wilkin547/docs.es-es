---
title: 'Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590912"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="d7b7c-102">Cómo: Crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d7b7c-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="d7b7c-103">Puede mostrar datos relacionados mediante dos o más <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controles para crear un formulario principal-detalle.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="d7b7c-104">Por ejemplo, desea mostrar una lista de clientes en una <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>y cuando el usuario selecciona un cliente, mostrar una lista de los pedidos del cliente en un segundo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="d7b7c-105">Puede mostrar datos relacionados arrastrando elementos de detalle que comparten el mismo nodo de tabla principal desde la **orígenes de datos** ventana en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="d7b7c-106">Por ejemplo, si tiene un origen de datos que tiene una tabla Customers y una tabla de pedidos relacionada, vea ambas tablas como nodos de nivel superior en la vista de árbol en el **orígenes de datos** ventana.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="d7b7c-107">Expanda el nodo de los clientes para que pueda ver las columnas.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="d7b7c-108">Tenga en cuenta que la última columna de la lista es un nodo expansible que representa la tabla Orders.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="d7b7c-109">Este nodo representa los pedidos relacionados para un cliente.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="d7b7c-110">Para mostrar datos relacionados en dos controles DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7b7c-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="d7b7c-111">Arrastre dos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controla desde el **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="d7b7c-112">Arrastre los controladores de tamaño y posición para cambiar el tamaño de los controles y colocarlos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="d7b7c-113">En el menú **Datos** , haga clic en **Mostrar orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7b7c-114">Si el **orígenes de datos** ventana está vacía, agregue un origen de datos a él.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="d7b7c-115">Para obtener más información, vea [Agregar nuevos orígenes de datos](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="d7b7c-115">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="d7b7c-116">En el **orígenes de datos** ventana, seleccione el nodo de nivel superior de la tabla principal.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="d7b7c-117">Cambie el tipo drop de la tabla principal a detalles haciendo clic en **detalles** en la lista desplegable en el nodo de tabla.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="d7b7c-118">Arrastre el nodo de tabla principal a la región de la plantilla de elemento de la primera <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="d7b7c-119">Expanda el nodo de tabla principal y seleccione el nodo de detalle de la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="d7b7c-120">Cambie el tipo de colocación de la tabla de detalle a detalles haciendo clic en **detalles** en la lista desplegable en el nodo de tabla.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="d7b7c-121">Seleccione este nodo de tabla y arrástrelo a la región de la plantilla de elemento del segundo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b7c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7b7c-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="d7b7c-123">Introducción al control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7b7c-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d7b7c-124">Mostrar los datos enlazados en un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7b7c-124">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d7b7c-125">Cómo: Mostrar datos relacionados en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7b7c-125">How to: Display Related Data in a Windows Forms Application</span></span>](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [<span data-ttu-id="d7b7c-126">Cambiar la apariencia de un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7b7c-126">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d7b7c-127">Solución de problemas del control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7b7c-127">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
