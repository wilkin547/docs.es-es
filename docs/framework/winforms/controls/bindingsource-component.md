---
title: Componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717601"
---
# <a name="bindingsource-component"></a><span data-ttu-id="5713e-102">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="5713e-102">BindingSource Component</span></span>
<span data-ttu-id="5713e-103">Encapsula un origen de datos para el enlace a controles.</span><span class="sxs-lookup"><span data-stu-id="5713e-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="5713e-104">El componente <xref:System.Windows.Forms.BindingSource> sirve para dos propósitos.</span><span class="sxs-lookup"><span data-stu-id="5713e-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="5713e-105">Primero, proporciona una capa de direccionamiento indirecto cuando los controles de un formulario se enlazan a datos.</span><span class="sxs-lookup"><span data-stu-id="5713e-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="5713e-106">Esto se logra enlazando el componente <xref:System.Windows.Forms.BindingSource> a su origen de datos y, después, enlazando los controles del formulario al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="5713e-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="5713e-107">Toda interacción posterior con los datos, incluida la navegación, la ordenación, el filtrado y la actualización, se lleva a cabo mediante llamadas al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="5713e-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="5713e-108">Segundo, el componente <xref:System.Windows.Forms.BindingSource> puede actuar como un origen de datos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="5713e-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="5713e-109">Al agregar un tipo al componente <xref:System.Windows.Forms.BindingSource> con el método <xref:System.Windows.Forms.BindingSource.Add%2A> se crea una lista de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="5713e-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5713e-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5713e-110">In This Section</span></span>  
 [<span data-ttu-id="5713e-111">Información general sobre el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="5713e-111">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)  
 <span data-ttu-id="5713e-112">Presenta los conceptos generales del componente <xref:System.Windows.Forms.BindingSource>, que permite enlazar un origen de datos a un control.</span><span class="sxs-lookup"><span data-stu-id="5713e-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="5713e-113">Cómo: Enlazar controles de formularios Windows Forms a valores de la base de datos DBNull</span><span class="sxs-lookup"><span data-stu-id="5713e-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="5713e-114">Muestra cómo controlar un valor <xref:System.DBNull> desde el origen de datos mediante el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="5713e-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="5713e-115">Cómo: Ordenar y filtrar datos ADO.NET con el Windows Forms BindingSource (componente)</span><span class="sxs-lookup"><span data-stu-id="5713e-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="5713e-116">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para aplicar ordenaciones y filtros a los datos mostrados.</span><span class="sxs-lookup"><span data-stu-id="5713e-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="5713e-117">Cómo: Enlazar a un servicio Web mediante el componente BindingSource de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="5713e-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="5713e-118">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para enlazar a un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="5713e-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="5713e-119">Cómo: Controlar errores y excepciones que se producen con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="5713e-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="5713e-120">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para controlar correctamente los errores que ocurren en una operación de enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="5713e-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="5713e-121">Cómo: Enlazar un Control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="5713e-121">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="5713e-122">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar a un tipo.</span><span class="sxs-lookup"><span data-stu-id="5713e-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="5713e-123">Cómo: Enlazar un Control de Windows Forms a un objeto Factory</span><span class="sxs-lookup"><span data-stu-id="5713e-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="5713e-124">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar a un objeto o método de generador.</span><span class="sxs-lookup"><span data-stu-id="5713e-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="5713e-125">Cómo: Personalizar elemento con el componente BindingSource de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5713e-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="5713e-126">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para crear nuevos elementos y agregarlos a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5713e-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="5713e-127">Cómo: Provocar notificaciones de cambios mediante el método BindingSource ResetItem</span><span class="sxs-lookup"><span data-stu-id="5713e-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="5713e-128">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para generar eventos de notificación de cambios para orígenes de datos que no admiten la notificación de cambios.</span><span class="sxs-lookup"><span data-stu-id="5713e-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="5713e-129">Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="5713e-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="5713e-130">Muestra cómo usar un tipo que hereda de la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> con un control <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="5713e-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="5713e-131">Cómo: Reflejar las actualizaciones del origen de datos en un Control de Windows Forms con BindingSource</span><span class="sxs-lookup"><span data-stu-id="5713e-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="5713e-132">Muestra cómo responder a los cambios en el origen de datos mediante el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="5713e-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="5713e-133">Cómo: Compartir datos enlazados entre formularios mediante el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="5713e-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="5713e-134">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> enlazar varios formularios al mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5713e-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5713e-135">Referencia</span><span class="sxs-lookup"><span data-stu-id="5713e-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="5713e-136">Proporciona documentación de referencia para el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="5713e-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="5713e-137">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="5713e-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5713e-138">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5713e-138">Related Sections</span></span>  
 [<span data-ttu-id="5713e-139">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5713e-139">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="5713e-140">Contiene vínculos a temas que describen la arquitectura de enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5713e-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="5713e-141">Vea también [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="5713e-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
