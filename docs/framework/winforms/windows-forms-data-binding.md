---
title: Enlace de datos en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: cfb4c59c76142420f479b0b16a6d80317e98d159
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486015"
---
# <a name="windows-forms-data-binding"></a><span data-ttu-id="ea9eb-102">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea9eb-102">Windows Forms Data Binding</span></span>
<span data-ttu-id="ea9eb-103">El enlace de datos en Windows Forms proporciona los medios para mostrar y realizar cambios en la información de un origen de datos en los controles del formulario.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-103">Data binding in Windows Forms gives you the means to display and make changes to information from a data source in controls on the form.</span></span> <span data-ttu-id="ea9eb-104">Puede enlazar a orígenes de datos tradicionales y a casi cualquier estructura que contenga datos.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-104">You can bind to both traditional data sources as well as almost any structure that contains data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea9eb-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ea9eb-105">In This Section</span></span>  
 [<span data-ttu-id="ea9eb-106">Enlace de datos y Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea9eb-106">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 <span data-ttu-id="ea9eb-107">Proporciona información general del enlace de datos en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-107">Provides an overview of data binding in Windows Forms.</span></span>  
  
 [<span data-ttu-id="ea9eb-108">Orígenes de datos compatibles con Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea9eb-108">Data Sources Supported by Windows Forms</span></span>](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 <span data-ttu-id="ea9eb-109">Describe los orígenes de datos que se pueden usar con Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-109">Describes the data sources that can be used with Windows Forms.</span></span>  
  
 [<span data-ttu-id="ea9eb-110">Interfaces relacionadas con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ea9eb-110">Interfaces Related to Data Binding</span></span>](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 <span data-ttu-id="ea9eb-111">Describe algunas de las interfaces usadas con el enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-111">Describes several of the interfaces used with Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="ea9eb-112">Desplazarse por datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea9eb-112">How to: Navigate Data in Windows Forms</span></span>](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)  
 <span data-ttu-id="ea9eb-113">Muestra cómo navegar por los elementos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-113">Shows how to navigate through items in a data source.</span></span>  
  
 [<span data-ttu-id="ea9eb-114">Notificación de cambios en el enlace de datos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea9eb-114">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 <span data-ttu-id="ea9eb-115">Describe los diferentes tipos de notificación de cambios para el enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-115">Describes different types of change notification for Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="ea9eb-116">Implementar la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="ea9eb-116">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 <span data-ttu-id="ea9eb-117">Muestra cómo implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-117">Shows how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="ea9eb-118">La interfaz comunica a un control enlazado los cambios de propiedad en un objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-118">The interface  communicates to a bound control the property changes on a business object</span></span>  
  
 [<span data-ttu-id="ea9eb-119">Aplicar el modelo PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="ea9eb-119">How to: Apply the PropertyNameChanged Pattern</span></span>](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 <span data-ttu-id="ea9eb-120">Se muestra cómo aplicar el *PropertyName*modelo Changed a las propiedades de un control de usuario de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-120">Shows how to apply the *PropertyName*Changed pattern to properties of a Windows Forms user control.</span></span>  
  
 [<span data-ttu-id="ea9eb-121">Implementar la interfaz ITypedList</span><span class="sxs-lookup"><span data-stu-id="ea9eb-121">How to: Implement the ITypedList Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-itypedlist-interface.md)  
 <span data-ttu-id="ea9eb-122">Muestra cómo habilitar la detección del esquema de una lista enlazable mediante la implementación de la interfaz <xref:System.ComponentModel.ITypedList>.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-122">Shows how to enable discovery of the schema for a bindable list by implementing the <xref:System.ComponentModel.ITypedList> interface.</span></span>  
  
 [<span data-ttu-id="ea9eb-123">Implementar la interfaz IListSource</span><span class="sxs-lookup"><span data-stu-id="ea9eb-123">How to: Implement the IListSource Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-ilistsource-interface.md)  
 <span data-ttu-id="ea9eb-124">Muestra cómo la implementación de la interfaz <xref:System.ComponentModel.IListSource> para crear una clase enlazable no implementa <xref:System.Collections.IList>, sino que proporciona una lista de otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-124">Shows how to implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class does not implement <xref:System.Collections.IList>, but provides a list from another location.</span></span>  
  
 [<span data-ttu-id="ea9eb-125">Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados</span><span class="sxs-lookup"><span data-stu-id="ea9eb-125">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 <span data-ttu-id="ea9eb-126">Muestra cómo controlar el evento <xref:System.Windows.Forms.BindingSource.BindingComplete> para asegurarse de que todos los controles enlazados a un origen de datos permanezcan sincronizados.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-126">Shows how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event to ensure all controls bound to a data source remain synchronized.</span></span>  
  
 [<span data-ttu-id="ea9eb-127">Garantizar que la fila seleccionada de una tabla secundaria conserva la posición correcta</span><span class="sxs-lookup"><span data-stu-id="ea9eb-127">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>](../../../docs/framework/winforms/ensure-the-selected-row-in-a-child-table-correct.md)  
 <span data-ttu-id="ea9eb-128">Muestra cómo asegurarse de que no cambie la fila seleccionada de una tabla secundaria cuando se realice un cambio en un campo de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-128">Shows how to ensure the selected row of a child table does not change, when a change is made to a field of the parent table.</span></span>  
  
 <span data-ttu-id="ea9eb-129">Consulte también [Interfaces relacionadas con enlace de datos](https://msdn.microsoft.com/library/41e17s4b\(v=vs.110\)), [Cómo: navegar por los datos en Windows Forms](https://msdn.microsoft.com/library/b63ha24w\(v=vs.110\)), [Cómo: crear un Control con enlace Simple en un formulario Windows Forms](https://msdn.microsoft.com/library/sw223a62\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="ea9eb-129">Also see [Interfaces Related to Data Binding](https://msdn.microsoft.com/library/41e17s4b\(v=vs.110\)), [How to: Navigate Data in Windows Forms](https://msdn.microsoft.com/library/b63ha24w\(v=vs.110\)), [How to: Create a Simple-Bound Control on a Windows Form](https://msdn.microsoft.com/library/sw223a62\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ea9eb-130">Referencia</span><span class="sxs-lookup"><span data-stu-id="ea9eb-130">Reference</span></span>  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 <span data-ttu-id="ea9eb-131">Describe la clase que representa el enlace entre un componente enlazable y un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-131">Describes the class that represents the binding between a bindable component and a data source.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 <span data-ttu-id="ea9eb-132">Describe la clase que encapsula un origen de datos para el enlace a controles.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-132">Describes the class that encapsulates a data source for binding to controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ea9eb-133">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ea9eb-133">Related Sections</span></span>  
 [<span data-ttu-id="ea9eb-134">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="ea9eb-134">BindingSource Component</span></span>](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 <span data-ttu-id="ea9eb-135">Contiene una lista de los temas que muestran cómo usar el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-135">Contains a list of topics that demonstrate how to use the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="ea9eb-136">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="ea9eb-136">DataGridView Control</span></span>](../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 <span data-ttu-id="ea9eb-137">Proporciona una lista de temas que muestran cómo usar un control datagrid enlazable.</span><span class="sxs-lookup"><span data-stu-id="ea9eb-137">Provides a list of topics that demonstrate how to use a bindable datagrid control.</span></span>  
  
 <span data-ttu-id="ea9eb-138">Consulte también [acceso a los datos en Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ea9eb-138">Also see [Accessing Data in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span></span>
