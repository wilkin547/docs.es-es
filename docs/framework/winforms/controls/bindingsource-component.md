---
title: Componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683423"
---
# <a name="bindingsource-component"></a><span data-ttu-id="cbaac-102">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="cbaac-102">BindingSource Component</span></span>
<span data-ttu-id="cbaac-103">Encapsula un origen de datos para el enlace a controles.</span><span class="sxs-lookup"><span data-stu-id="cbaac-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="cbaac-104">El componente <xref:System.Windows.Forms.BindingSource> sirve para dos propósitos.</span><span class="sxs-lookup"><span data-stu-id="cbaac-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="cbaac-105">Primero, proporciona una capa de direccionamiento indirecto cuando los controles de un formulario se enlazan a datos.</span><span class="sxs-lookup"><span data-stu-id="cbaac-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="cbaac-106">Esto se logra enlazando el componente <xref:System.Windows.Forms.BindingSource> a su origen de datos y, después, enlazando los controles del formulario al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="cbaac-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="cbaac-107">Toda interacción posterior con los datos, incluida la navegación, la ordenación, el filtrado y la actualización, se lleva a cabo mediante llamadas al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="cbaac-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="cbaac-108">Segundo, el componente <xref:System.Windows.Forms.BindingSource> puede actuar como un origen de datos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="cbaac-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="cbaac-109">Al agregar un tipo al componente <xref:System.Windows.Forms.BindingSource> con el método <xref:System.Windows.Forms.BindingSource.Add%2A> se crea una lista de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="cbaac-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cbaac-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cbaac-110">In This Section</span></span>  
 [<span data-ttu-id="cbaac-111">Información general sobre el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="cbaac-111">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)  
 <span data-ttu-id="cbaac-112">Presenta los conceptos generales del componente <xref:System.Windows.Forms.BindingSource>, que permite enlazar un origen de datos a un control.</span><span class="sxs-lookup"><span data-stu-id="cbaac-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="cbaac-113">Cómo: Enlazar controles de formularios Windows Forms a valores de la base de datos DBNull</span><span class="sxs-lookup"><span data-stu-id="cbaac-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="cbaac-114">Muestra cómo controlar un valor <xref:System.DBNull> desde el origen de datos mediante el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="cbaac-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="cbaac-115">Cómo: Ordenar y filtrar datos ADO.NET con el Windows Forms BindingSource (componente)</span><span class="sxs-lookup"><span data-stu-id="cbaac-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="cbaac-116">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para aplicar ordenaciones y filtros a los datos mostrados.</span><span class="sxs-lookup"><span data-stu-id="cbaac-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="cbaac-117">Cómo: Enlazar a un servicio Web mediante el componente BindingSource de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="cbaac-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="cbaac-118">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para enlazar a un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="cbaac-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="cbaac-119">Cómo: Controlar errores y excepciones que se producen con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="cbaac-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="cbaac-120">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para controlar correctamente los errores que ocurren en una operación de enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="cbaac-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="cbaac-121">Cómo: Enlazar un Control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="cbaac-121">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="cbaac-122">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar a un tipo.</span><span class="sxs-lookup"><span data-stu-id="cbaac-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="cbaac-123">Cómo: Enlazar un Control de Windows Forms a un objeto Factory</span><span class="sxs-lookup"><span data-stu-id="cbaac-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="cbaac-124">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar a un objeto o método de generador.</span><span class="sxs-lookup"><span data-stu-id="cbaac-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="cbaac-125">Cómo: Personalizar elemento con el componente BindingSource de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbaac-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="cbaac-126">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para crear nuevos elementos y agregarlos a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cbaac-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="cbaac-127">Cómo: Provocar notificaciones de cambios mediante el método BindingSource ResetItem</span><span class="sxs-lookup"><span data-stu-id="cbaac-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="cbaac-128">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para generar eventos de notificación de cambios para orígenes de datos que no admiten la notificación de cambios.</span><span class="sxs-lookup"><span data-stu-id="cbaac-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="cbaac-129">Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="cbaac-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="cbaac-130">Muestra cómo usar un tipo que hereda de la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> con un control <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="cbaac-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="cbaac-131">Cómo: Reflejar las actualizaciones del origen de datos en un Control de Windows Forms con BindingSource</span><span class="sxs-lookup"><span data-stu-id="cbaac-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="cbaac-132">Muestra cómo responder a los cambios en el origen de datos mediante el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="cbaac-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="cbaac-133">Cómo: Compartir datos enlazados entre formularios mediante el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="cbaac-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="cbaac-134">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> enlazar varios formularios al mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cbaac-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cbaac-135">Referencia</span><span class="sxs-lookup"><span data-stu-id="cbaac-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="cbaac-136">Proporciona documentación de referencia para el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="cbaac-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="cbaac-137">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="cbaac-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cbaac-138">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="cbaac-138">Related Sections</span></span>  
 [<span data-ttu-id="cbaac-139">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbaac-139">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="cbaac-140">Contiene vínculos a temas que describen la arquitectura de enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="cbaac-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="cbaac-141">Vea también [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="cbaac-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
