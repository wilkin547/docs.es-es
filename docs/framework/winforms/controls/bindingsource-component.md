---
title: Componente BindingSource
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 006cafafdf8e3c3f4da77394d6155fa52e113b58
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="bindingsource-component"></a><span data-ttu-id="7cf6d-102">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="7cf6d-102">BindingSource Component</span></span>
<span data-ttu-id="7cf6d-103">Encapsula un origen de datos para el enlace a controles.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="7cf6d-104">El componente <xref:System.Windows.Forms.BindingSource> sirve para dos propósitos.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="7cf6d-105">Primero, proporciona una capa de direccionamiento indirecto cuando los controles de un formulario se enlazan a datos.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="7cf6d-106">Esto se logra enlazando el componente <xref:System.Windows.Forms.BindingSource> a su origen de datos y, después, enlazando los controles del formulario al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="7cf6d-107">Toda interacción posterior con los datos, incluida la navegación, la ordenación, el filtrado y la actualización, se lleva a cabo mediante llamadas al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="7cf6d-108">Segundo, el componente <xref:System.Windows.Forms.BindingSource> puede actuar como un origen de datos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="7cf6d-109">Al agregar un tipo al componente <xref:System.Windows.Forms.BindingSource> con el método <xref:System.Windows.Forms.BindingSource.Add%2A> se crea una lista de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7cf6d-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7cf6d-110">In This Section</span></span>  
 [<span data-ttu-id="7cf6d-111">Información general sobre el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="7cf6d-111">BindingSource Component Overview</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)  
 <span data-ttu-id="7cf6d-112">Presenta los conceptos generales del componente <xref:System.Windows.Forms.BindingSource>, que permite enlazar un origen de datos a un control.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="7cf6d-113">Cómo: Enlazar controles de Windows Forms a valores de base de datos DBNull</span><span class="sxs-lookup"><span data-stu-id="7cf6d-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="7cf6d-114">Muestra cómo controlar un valor <xref:System.DBNull> desde el origen de datos mediante el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="7cf6d-115">Cómo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7cf6d-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="7cf6d-116">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para aplicar ordenaciones y filtros a los datos mostrados.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="7cf6d-117">Cómo: Enlazar a un servicio Web mediante el componente BindingSource de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7cf6d-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="7cf6d-118">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para enlazar a un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="7cf6d-119">Cómo: Controlar errores y excepciones que se producen con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="7cf6d-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="7cf6d-120">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> para controlar correctamente los errores que ocurren en una operación de enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="7cf6d-121">Cómo: Enlazar un control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="7cf6d-121">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="7cf6d-122">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar a un tipo.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="7cf6d-123">Cómo: Enlazar un control de Windows Forms a un objeto Factory</span><span class="sxs-lookup"><span data-stu-id="7cf6d-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="7cf6d-124">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para enlazar a un objeto o método de generador.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="7cf6d-125">Cómo: Personalizar la forma de agregar elementos con el control BindingSource de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7cf6d-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="7cf6d-126">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para crear nuevos elementos y agregarlos a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="7cf6d-127">Cómo: Provocar notificaciones de cambios mediante el método ResetItem de BindingSource</span><span class="sxs-lookup"><span data-stu-id="7cf6d-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="7cf6d-128">Muestra cómo usar un componente <xref:System.Windows.Forms.BindingSource> para generar eventos de notificación de cambios para orígenes de datos que no admiten la notificación de cambios.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="7cf6d-129">Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="7cf6d-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](../../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="7cf6d-130">Muestra cómo usar un tipo que hereda de la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> con un control <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="7cf6d-131">Cómo: Reflejar las actualizaciones de los orígenes de datos en un control de Windows Forms con BindingSource</span><span class="sxs-lookup"><span data-stu-id="7cf6d-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="7cf6d-132">Muestra cómo responder a los cambios en el origen de datos mediante el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="7cf6d-133">Cómo: Compartir datos enlazados entre formularios mediante el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="7cf6d-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="7cf6d-134">Muestra cómo usar el componente <xref:System.Windows.Forms.BindingSource> enlazar varios formularios al mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7cf6d-135">Referencia</span><span class="sxs-lookup"><span data-stu-id="7cf6d-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="7cf6d-136">Proporciona documentación de referencia para el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="7cf6d-137">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7cf6d-138">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7cf6d-138">Related Sections</span></span>  
 [<span data-ttu-id="7cf6d-139">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7cf6d-139">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 <span data-ttu-id="7cf6d-140">Contiene vínculos a temas que describen la arquitectura de enlace de datos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7cf6d-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="7cf6d-141">Vea también [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="7cf6d-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
