---
title: 'Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245547"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="f0c46-102">Cómo: Crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="f0c46-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="f0c46-103">Puede mostrar datos relacionados mediante dos o más <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controles para crear un formulario principal-detalle.</span><span class="sxs-lookup"><span data-stu-id="f0c46-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="f0c46-104">Por ejemplo, desea mostrar una lista de clientes en uno <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>y cuando el usuario selecciona un cliente, mostrar una lista de los pedidos del cliente en un segundo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="f0c46-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="f0c46-105">Puede mostrar datos relacionados arrastrando los elementos de detalle que comparten el mismo nodo de tabla maestra de la **orígenes de datos** ventana hasta un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="f0c46-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="f0c46-106">Por ejemplo, si tiene un origen de datos que tiene una tabla denominada Customers y una tabla de pedidos relacionada, vea ambas tablas como nodos de nivel superior en la vista de árbol en el **orígenes de datos** ventana.</span><span class="sxs-lookup"><span data-stu-id="f0c46-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="f0c46-107">Expanda el nodo de los clientes para que puedan ver las columnas.</span><span class="sxs-lookup"><span data-stu-id="f0c46-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="f0c46-108">Tenga en cuenta que la última columna en la lista es un nodo expansible que representa la tabla Orders.</span><span class="sxs-lookup"><span data-stu-id="f0c46-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="f0c46-109">Este nodo representa los pedidos relacionados para un cliente.</span><span class="sxs-lookup"><span data-stu-id="f0c46-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="f0c46-110">Para mostrar datos relacionados en dos controles DataRepeater</span><span class="sxs-lookup"><span data-stu-id="f0c46-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="f0c46-111">Arrastre dos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controla desde el **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0c46-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="f0c46-112">Arrastre los controladores de tamaño y posición para el tamaño de los controles y colocarlos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="f0c46-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="f0c46-113">En el menú **Datos** , haga clic en **Mostrar orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="f0c46-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0c46-114">Si el **orígenes de datos** ventana está vacía, agregue un origen de datos a él.</span><span class="sxs-lookup"><span data-stu-id="f0c46-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="f0c46-115">Para obtener más información, vea [Agregar nuevos orígenes de datos](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="f0c46-115">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="f0c46-116">En el **orígenes de datos** ventana, seleccione el nodo de nivel superior de la tabla principal.</span><span class="sxs-lookup"><span data-stu-id="f0c46-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="f0c46-117">Cambie el tipo de colocación de la tabla maestra a detalles haciendo **detalles** en la lista desplegable en el nodo de tabla.</span><span class="sxs-lookup"><span data-stu-id="f0c46-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="f0c46-118">Arrastre el nodo de la tabla maestra a la región de la plantilla de elemento de la primera <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="f0c46-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="f0c46-119">Expanda el nodo de la tabla principal y seleccione el nodo de detalle de la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="f0c46-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="f0c46-120">Cambie el tipo de colocación de la tabla de detalles a detalles haciendo **detalles** en la lista desplegable en el nodo de tabla.</span><span class="sxs-lookup"><span data-stu-id="f0c46-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="f0c46-121">Seleccione este nodo de tabla y arrástrelo a la región de la plantilla de elemento del segundo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="f0c46-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c46-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0c46-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="f0c46-123">Introducción al control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="f0c46-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="f0c46-124">Mostrar los datos enlazados en un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="f0c46-124">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="f0c46-125">Cómo: Mostrar datos relacionados en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0c46-125">How to: Display Related Data in a Windows Forms Application</span></span>](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [<span data-ttu-id="f0c46-126">Cambiar la apariencia de un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="f0c46-126">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="f0c46-127">Solución de problemas del control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="f0c46-127">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
