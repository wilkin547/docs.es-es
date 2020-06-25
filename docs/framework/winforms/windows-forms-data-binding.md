---
title: Enlace de datos
description: Obtenga información sobre cómo usar el enlace de datos en Windows Forms para mostrar y realizar cambios en la información de un origen de datos en los controles del formulario.
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: 3dfce24147caf9b138916ca8dc3b7a9010439f58
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325547"
---
# <a name="windows-forms-data-binding"></a><span data-ttu-id="7593d-103">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7593d-103">Windows Forms Data Binding</span></span>
<span data-ttu-id="7593d-104">El enlace de datos en Windows Forms proporciona los medios para mostrar y realizar cambios en la información de un origen de datos en los controles del formulario.</span><span class="sxs-lookup"><span data-stu-id="7593d-104">Data binding in Windows Forms gives you the means to display and make changes to information from a data source in controls on the form.</span></span> <span data-ttu-id="7593d-105">Puede enlazar a orígenes de datos tradicionales y a casi cualquier estructura que contenga datos.</span><span class="sxs-lookup"><span data-stu-id="7593d-105">You can bind to both traditional data sources as well as almost any structure that contains data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7593d-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7593d-106">In This Section</span></span>  
 [<span data-ttu-id="7593d-107">Enlace de datos y formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7593d-107">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)  
 <span data-ttu-id="7593d-108">Proporciona información general del enlace de datos en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7593d-108">Provides an overview of data binding in Windows Forms.</span></span>  
  
 [<span data-ttu-id="7593d-109">Orígenes de datos compatibles con formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7593d-109">Data Sources Supported by Windows Forms</span></span>](data-sources-supported-by-windows-forms.md)  
 <span data-ttu-id="7593d-110">Describe los orígenes de datos que se pueden usar con Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7593d-110">Describes the data sources that can be used with Windows Forms.</span></span>  
  
 [<span data-ttu-id="7593d-111">Interfaces relacionadas con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="7593d-111">Interfaces Related to Data Binding</span></span>](interfaces-related-to-data-binding.md)  
 <span data-ttu-id="7593d-112">Describe algunas de las interfaces usadas con el enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7593d-112">Describes several of the interfaces used with Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="7593d-113">Procedimiento para desplazarse por los datos en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7593d-113">How to: Navigate Data in Windows Forms</span></span>](how-to-navigate-data-in-windows-forms.md)  
 <span data-ttu-id="7593d-114">Muestra cómo navegar por los elementos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7593d-114">Shows how to navigate through items in a data source.</span></span>  
  
 [<span data-ttu-id="7593d-115">Notificación de cambios en el enlace de datos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7593d-115">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)  
 <span data-ttu-id="7593d-116">Describe los diferentes tipos de notificación de cambios para el enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7593d-116">Describes different types of change notification for Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="7593d-117">Procedimiento para implementar la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="7593d-117">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)  
 <span data-ttu-id="7593d-118">Muestra cómo implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="7593d-118">Shows how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="7593d-119">La interfaz comunica a un control enlazado los cambios de propiedad en un objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="7593d-119">The interface  communicates to a bound control the property changes on a business object</span></span>  
  
 [<span data-ttu-id="7593d-120">Procedimiento para aplicar el patrón PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="7593d-120">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)  
 <span data-ttu-id="7593d-121">Muestra cómo aplicar el patrón *PropertyName*Changed a las propiedades de un control de usuario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7593d-121">Shows how to apply the *PropertyName*Changed pattern to properties of a Windows Forms user control.</span></span>  
  
 [<span data-ttu-id="7593d-122">Procedimiento para implementar la interfaz ITypedList</span><span class="sxs-lookup"><span data-stu-id="7593d-122">How to: Implement the ITypedList Interface</span></span>](how-to-implement-the-itypedlist-interface.md)  
 <span data-ttu-id="7593d-123">Muestra cómo habilitar la detección del esquema de una lista enlazable mediante la implementación de la interfaz <xref:System.ComponentModel.ITypedList>.</span><span class="sxs-lookup"><span data-stu-id="7593d-123">Shows how to enable discovery of the schema for a bindable list by implementing the <xref:System.ComponentModel.ITypedList> interface.</span></span>  
  
 [<span data-ttu-id="7593d-124">Procedimiento para implementar la interfaz IListSource</span><span class="sxs-lookup"><span data-stu-id="7593d-124">How to: Implement the IListSource Interface</span></span>](how-to-implement-the-ilistsource-interface.md)  
 <span data-ttu-id="7593d-125">Muestra cómo la implementación de la interfaz <xref:System.ComponentModel.IListSource> para crear una clase enlazable no implementa <xref:System.Collections.IList>, sino que proporciona una lista de otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="7593d-125">Shows how to implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class does not implement <xref:System.Collections.IList>, but provides a list from another location.</span></span>  
  
 [<span data-ttu-id="7593d-126">Procedimiento para garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados</span><span class="sxs-lookup"><span data-stu-id="7593d-126">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](multiple-controls-bound-to-data-source-synchronized.md)  
 <span data-ttu-id="7593d-127">Muestra cómo controlar el evento <xref:System.Windows.Forms.BindingSource.BindingComplete> para asegurarse de que todos los controles enlazados a un origen de datos permanezcan sincronizados.</span><span class="sxs-lookup"><span data-stu-id="7593d-127">Shows how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event to ensure all controls bound to a data source remain synchronized.</span></span>  
  
 [<span data-ttu-id="7593d-128">Procedimiento para garantizar que la fila seleccionada de una tabla secundaria conserve la posición correcta</span><span class="sxs-lookup"><span data-stu-id="7593d-128">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>](ensure-the-selected-row-in-a-child-table-correct.md)  
 <span data-ttu-id="7593d-129">Muestra cómo asegurarse de que no cambie la fila seleccionada de una tabla secundaria cuando se realice un cambio en un campo de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="7593d-129">Shows how to ensure the selected row of a child table does not change, when a change is made to a field of the parent table.</span></span>  
  
 <span data-ttu-id="7593d-130">Vea también [interfaces relacionadas con el enlace de datos](interfaces-related-to-data-binding.md), [Cómo: navegar por los datos en Windows Forms](how-to-navigate-data-in-windows-forms.md)y [Cómo: crear un control de enlace simple en Windows Forms](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="7593d-130">Also see [Interfaces Related to Data Binding](interfaces-related-to-data-binding.md), [How to: Navigate Data in Windows Forms](how-to-navigate-data-in-windows-forms.md), and [How to: Create a Simple-Bound Control on a Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7593d-131">Referencia</span><span class="sxs-lookup"><span data-stu-id="7593d-131">Reference</span></span>  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 <span data-ttu-id="7593d-132">Describe la clase que representa el enlace entre un componente enlazable y un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7593d-132">Describes the class that represents the binding between a bindable component and a data source.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 <span data-ttu-id="7593d-133">Describe la clase que encapsula un origen de datos para el enlace a controles.</span><span class="sxs-lookup"><span data-stu-id="7593d-133">Describes the class that encapsulates a data source for binding to controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7593d-134">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7593d-134">Related Sections</span></span>  
 [<span data-ttu-id="7593d-135">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="7593d-135">BindingSource Component</span></span>](./controls/bindingsource-component.md)  
 <span data-ttu-id="7593d-136">Contiene una lista de los temas que muestran cómo usar el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="7593d-136">Contains a list of topics that demonstrate how to use the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="7593d-137">Control DataGridView</span><span class="sxs-lookup"><span data-stu-id="7593d-137">DataGridView Control</span></span>](./controls/datagridview-control-windows-forms.md)  
 <span data-ttu-id="7593d-138">Proporciona una lista de temas que muestran cómo usar un control datagrid enlazable.</span><span class="sxs-lookup"><span data-stu-id="7593d-138">Provides a list of topics that demonstrate how to use a bindable datagrid control.</span></span>  
  
 <span data-ttu-id="7593d-139">Vea también el [acceso a los datos en Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="7593d-139">Also see [Accessing Data in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span></span>
