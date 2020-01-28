---
title: Arquitectura del control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742530"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="78f59-102">Arquitectura del control DataGridView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="78f59-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="78f59-103">El control <xref:System.Windows.Forms.DataGridView> y sus clases relacionadas están diseñados para ser un sistema flexible y extensible para mostrar y editar datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="78f59-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="78f59-104">Todas estas clases están contenidas en el espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> y todas se denominan con el prefijo "DataGridView".</span><span class="sxs-lookup"><span data-stu-id="78f59-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="78f59-105">Elementos de arquitectura</span><span class="sxs-lookup"><span data-stu-id="78f59-105">Architecture Elements</span></span>  
 <span data-ttu-id="78f59-106">Las clases auxiliares de <xref:System.Windows.Forms.DataGridView> principales derivan de <xref:System.Windows.Forms.DataGridViewElement>.</span><span class="sxs-lookup"><span data-stu-id="78f59-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="78f59-107">En el modelo de objetos siguiente se ilustra el <xref:System.Windows.Forms.DataGridViewElement> jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="78f59-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![Diagrama que muestra la jerarquía del modelo de objetos DataGridViewElement.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="78f59-109">La clase <xref:System.Windows.Forms.DataGridViewElement> proporciona una referencia al control <xref:System.Windows.Forms.DataGridView> primario y tiene una propiedad <xref:System.Windows.Forms.DataGridViewElement.State%2A>, que contiene un valor que representa una combinación de valores de la enumeración <xref:System.Windows.Forms.DataGridViewElementStates>.</span><span class="sxs-lookup"><span data-stu-id="78f59-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="78f59-110">En las secciones siguientes se describen con más detalle las clases complementarias de <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="78f59-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="78f59-111">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="78f59-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="78f59-112">La enumeración <xref:System.Windows.Forms.DataGridViewElementStates> contiene los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="78f59-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="78f59-113">Los valores de esta enumeración se pueden combinar con los operadores lógicos bit a bit, por lo que la propiedad <xref:System.Windows.Forms.DataGridViewElement.State%2A> puede expresar más de un estado a la vez.</span><span class="sxs-lookup"><span data-stu-id="78f59-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="78f59-114">Por ejemplo, un <xref:System.Windows.Forms.DataGridViewElement> se puede <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>y <xref:System.Windows.Forms.DataGridViewElementStates.Visible>simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="78f59-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="78f59-115">Celdas y bandas</span><span class="sxs-lookup"><span data-stu-id="78f59-115">Cells and Bands</span></span>  
 <span data-ttu-id="78f59-116">El control <xref:System.Windows.Forms.DataGridView> consta de dos tipos fundamentales de objetos: celdas y bandas.</span><span class="sxs-lookup"><span data-stu-id="78f59-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="78f59-117">Todas las celdas derivan de la clase base <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="78f59-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="78f59-118">Los dos tipos de bandas, <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.DataGridViewRow>, derivan de la clase base <xref:System.Windows.Forms.DataGridViewBand>.</span><span class="sxs-lookup"><span data-stu-id="78f59-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="78f59-119">El control <xref:System.Windows.Forms.DataGridView> interopera con varias clases, pero lo más frecuente es <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>y <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="78f59-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="78f59-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="78f59-120">DataGridViewCell</span></span>  
 <span data-ttu-id="78f59-121">La celda es la unidad fundamental de interacción para el <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="78f59-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="78f59-122">La presentación se centra en las celdas y la entrada de datos se realiza a menudo a través de las celdas.</span><span class="sxs-lookup"><span data-stu-id="78f59-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="78f59-123">Puede tener acceso a las celdas mediante el <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> colección de la clase <xref:System.Windows.Forms.DataGridViewRow> y puede tener acceso a las celdas seleccionadas mediante la colección <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> del control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="78f59-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="78f59-124">El siguiente modelo de objetos ilustra este uso y muestra el <xref:System.Windows.Forms.DataGridViewCell> jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="78f59-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![Diagrama que muestra la jerarquía del modelo de objetos DataGridViewCell.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="78f59-126">El <xref:System.Windows.Forms.DataGridViewCell> tipo es una clase base abstracta de la que se derivan todos los tipos de celda.</span><span class="sxs-lookup"><span data-stu-id="78f59-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="78f59-127"><xref:System.Windows.Forms.DataGridViewCell> y sus tipos derivados no son Windows Forms controles, sino algunos controles de Windows Forms host.</span><span class="sxs-lookup"><span data-stu-id="78f59-127"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="78f59-128">Cualquier funcionalidad de edición admitida por una celda se controla normalmente mediante un control hospedado.</span><span class="sxs-lookup"><span data-stu-id="78f59-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="78f59-129"><xref:System.Windows.Forms.DataGridViewCell> objetos no controlan sus propias características de apariencia y dibujo de la misma forma que los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="78f59-129"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="78f59-130">En su lugar, el <xref:System.Windows.Forms.DataGridView> es responsable de la apariencia de sus objetos <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="78f59-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="78f59-131">Puede influir significativamente en la apariencia y el comportamiento de las celdas interactuando con las propiedades y eventos del control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="78f59-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="78f59-132">Si tiene requisitos especiales para las personalizaciones que están más allá de las capacidades del control <xref:System.Windows.Forms.DataGridView>, puede implementar su propia clase que deriva de <xref:System.Windows.Forms.DataGridViewCell> o de una de sus clases secundarias.</span><span class="sxs-lookup"><span data-stu-id="78f59-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="78f59-133">En la lista siguiente se muestran las clases derivadas de <xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="78f59-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- <span data-ttu-id="78f59-134">Los tipos de celda personalizados</span><span class="sxs-lookup"><span data-stu-id="78f59-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="78f59-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="78f59-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="78f59-136">El esquema del almacén de datos asociado del control de <xref:System.Windows.Forms.DataGridView> se expresa en las columnas del control de <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="78f59-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="78f59-137">Puede tener acceso a las columnas del control <xref:System.Windows.Forms.DataGridView> mediante la colección <xref:System.Windows.Forms.DataGridView.Columns%2A>.</span><span class="sxs-lookup"><span data-stu-id="78f59-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="78f59-138">Puede tener acceso a las columnas seleccionadas mediante el <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="78f59-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="78f59-139">El siguiente modelo de objetos ilustra este uso y muestra el <xref:System.Windows.Forms.DataGridViewColumn> jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="78f59-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![Diagrama que muestra la jerarquía del modelo de objetos DataGridViewColumn.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="78f59-141">Algunos de los tipos de celda clave tienen tipos de columna correspondientes.</span><span class="sxs-lookup"><span data-stu-id="78f59-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="78f59-142">Se derivan de la clase base <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="78f59-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="78f59-143">En la lista siguiente se muestran las clases derivadas de <xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="78f59-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- <span data-ttu-id="78f59-144">Tipos de columna personalizados</span><span class="sxs-lookup"><span data-stu-id="78f59-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="78f59-145">Controles de edición de DataGridView</span><span class="sxs-lookup"><span data-stu-id="78f59-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="78f59-146">Las celdas que admiten la funcionalidad de edición avanzada suelen utilizar un control hospedado derivado de un control Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="78f59-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="78f59-147">Estos controles también implementan la interfaz <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="78f59-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="78f59-148">En el modelo de objetos siguiente se muestra el uso de estos controles.</span><span class="sxs-lookup"><span data-stu-id="78f59-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![Diagrama que muestra la jerarquía del modelo de objetos de control de edición de DataGridView.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="78f59-150">Los siguientes controles de edición se proporcionan con el control <xref:System.Windows.Forms.DataGridView>:</span><span class="sxs-lookup"><span data-stu-id="78f59-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="78f59-151">Para obtener información sobre cómo crear sus propios controles de edición, vea [Cómo: hospedar controles en Windows Forms celdas de DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span><span class="sxs-lookup"><span data-stu-id="78f59-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="78f59-152">En la tabla siguiente se muestra la relación entre los tipos de celda, los tipos de columna y los controles de edición.</span><span class="sxs-lookup"><span data-stu-id="78f59-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="78f59-153">Tipo de celda</span><span class="sxs-lookup"><span data-stu-id="78f59-153">Cell type</span></span>|<span data-ttu-id="78f59-154">Control hospedado</span><span class="sxs-lookup"><span data-stu-id="78f59-154">Hosted control</span></span>|<span data-ttu-id="78f59-155">Tipo de columna</span><span class="sxs-lookup"><span data-stu-id="78f59-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="78f59-156">no disponible</span><span class="sxs-lookup"><span data-stu-id="78f59-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="78f59-157">no disponible</span><span class="sxs-lookup"><span data-stu-id="78f59-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="78f59-158">no disponible</span><span class="sxs-lookup"><span data-stu-id="78f59-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="78f59-159">no disponible</span><span class="sxs-lookup"><span data-stu-id="78f59-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="78f59-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="78f59-160">DataGridViewRow</span></span>  
 <span data-ttu-id="78f59-161">La clase <xref:System.Windows.Forms.DataGridViewRow> muestra los campos de datos de un registro del almacén de datos al que está asociado el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="78f59-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="78f59-162">Puede tener acceso a las filas del control <xref:System.Windows.Forms.DataGridView> mediante la colección <xref:System.Windows.Forms.DataGridView.Rows%2A>.</span><span class="sxs-lookup"><span data-stu-id="78f59-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="78f59-163">Puede tener acceso a las filas seleccionadas mediante el <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="78f59-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="78f59-164">El siguiente modelo de objetos ilustra este uso y muestra el <xref:System.Windows.Forms.DataGridViewRow> jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="78f59-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![Diagrama que muestra la jerarquía del modelo de objetos DataGridViewRow.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="78f59-166">Puede derivar sus propios tipos de la clase <xref:System.Windows.Forms.DataGridViewRow>, aunque normalmente no será necesario.</span><span class="sxs-lookup"><span data-stu-id="78f59-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="78f59-167">El control <xref:System.Windows.Forms.DataGridView> tiene varios eventos y propiedades relacionados con las filas para personalizar el comportamiento de sus objetos <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="78f59-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="78f59-168">Si habilita la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> del control <xref:System.Windows.Forms.DataGridView>, aparece una fila especial para agregar nuevas filas como última fila.</span><span class="sxs-lookup"><span data-stu-id="78f59-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="78f59-169">Esta fila forma parte de la colección de <xref:System.Windows.Forms.DataGridView.Rows%2A>, pero tiene una funcionalidad especial que puede requerir su atención.</span><span class="sxs-lookup"><span data-stu-id="78f59-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="78f59-170">Para obtener más información, vea [usar la fila para nuevos registros en el control DataGridView de Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="78f59-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f59-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="78f59-171">See also</span></span>

- [<span data-ttu-id="78f59-172">Información general del control DataGridView</span><span class="sxs-lookup"><span data-stu-id="78f59-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="78f59-173">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="78f59-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="78f59-174">Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="78f59-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
