---
title: Atributos en controles de formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13aad22dca249147e3037bcef6da755c264021db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="attributes-in-windows-forms-controls"></a><span data-ttu-id="8d92a-102">Atributos en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d92a-102">Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="8d92a-103">.NET Framework proporciona una variedad de atributos que puede aplicar a los miembros de sus controles y componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="8d92a-103">The .NET Framework provides a variety of attributes you can apply to the members of your custom controls and components.</span></span> <span data-ttu-id="8d92a-104">Algunos de estos atributos afectan al comportamiento en tiempo de ejecución de una clase y otros afectan al comportamiento en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="8d92a-104">Some of these attributes affect the run-time behavior of a class, and others affect the design-time behavior.</span></span>  
  
## <a name="attributes-for-control-and-component-properties"></a><span data-ttu-id="8d92a-105">Atributos para las propiedades de controles y componentes</span><span class="sxs-lookup"><span data-stu-id="8d92a-105">Attributes for Control and Component Properties</span></span>  
 <span data-ttu-id="8d92a-106">En la tabla siguiente se muestran los atributos que se pueden aplicar a las propiedades o a otros miembros de los controles y componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="8d92a-106">The following table shows the attributes you can apply to properties or other members of your custom controls and components.</span></span> <span data-ttu-id="8d92a-107">Para obtener un ejemplo que utiliza muchos de estos atributos, vea [Cómo: Aplicar atributos en controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="8d92a-107">For an example that uses many of these attributes, see [How to: Apply Attributes in Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
|<span data-ttu-id="8d92a-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="8d92a-108">Attribute</span></span>|<span data-ttu-id="8d92a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d92a-109">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|<span data-ttu-id="8d92a-110">Especifica el valor para pasar a una propiedad que hace que esta obtenga su valor de otro origen.</span><span class="sxs-lookup"><span data-stu-id="8d92a-110">Specifies the value to pass to a property to cause the property to get its value from another source.</span></span> <span data-ttu-id="8d92a-111">Esto se conoce como *ambiente*.</span><span class="sxs-lookup"><span data-stu-id="8d92a-111">This is known as *ambience*.</span></span>|  
|<xref:System.ComponentModel.BrowsableAttribute>|<span data-ttu-id="8d92a-112">Especifica si una propiedad o un evento se debería mostrar en una ventana **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8d92a-112">Specifies whether a property or event should be displayed in a **Properties** window.</span></span>|  
|<xref:System.ComponentModel.CategoryAttribute>|<span data-ttu-id="8d92a-113">Especifica el nombre de la categoría en la que desea agrupar la propiedad o evento cuando se muestre en una <xref:System.Windows.Forms.PropertyGrid> establecer control <xref:System.Windows.Forms.PropertySort.Categorized> modo.</span><span class="sxs-lookup"><span data-stu-id="8d92a-113">Specifies the name of the category in which to group the property or event when displayed in a <xref:System.Windows.Forms.PropertyGrid> control set to <xref:System.Windows.Forms.PropertySort.Categorized> mode.</span></span>|  
|<xref:System.ComponentModel.DefaultValueAttribute>|<span data-ttu-id="8d92a-114">Especifica el valor predeterminado de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="8d92a-114">Specifies the default value for a property.</span></span>|  
|<xref:System.ComponentModel.DescriptionAttribute>|<span data-ttu-id="8d92a-115">Especifica una descripción para una propiedad o evento.</span><span class="sxs-lookup"><span data-stu-id="8d92a-115">Specifies a description for a property or event.</span></span>|  
|<xref:System.ComponentModel.DisplayNameAttribute>|<span data-ttu-id="8d92a-116">Especifica el nombre para mostrar de una propiedad, evento o método `public``void` que no toma ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="8d92a-116">Specifies the display name for a property, event, or `public``void` method that takes no arguments.</span></span>|  
|<xref:System.ComponentModel.EditorAttribute>|<span data-ttu-id="8d92a-117">Especifica el editor que se va a utilizar para cambiar una propiedad.</span><span class="sxs-lookup"><span data-stu-id="8d92a-117">Specifies the editor to use to change a property.</span></span>|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|<span data-ttu-id="8d92a-118">Especifica que una propiedad o un método son visibles en un editor.</span><span class="sxs-lookup"><span data-stu-id="8d92a-118">Specifies that a property or method is viewable in an editor.</span></span>|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|<span data-ttu-id="8d92a-119">Especifica la palabra clave de contexto para una clase o miembro.</span><span class="sxs-lookup"><span data-stu-id="8d92a-119">Specifies the context keyword for a class or member.</span></span>|  
|<xref:System.ComponentModel.LocalizableAttribute>|<span data-ttu-id="8d92a-120">Especifica si se debería localizar una propiedad.</span><span class="sxs-lookup"><span data-stu-id="8d92a-120">Specifies whether a property should be localized.</span></span>|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|<span data-ttu-id="8d92a-121">Indica los caracteres que ocultan la representación del texto de un objeto, como asteriscos.</span><span class="sxs-lookup"><span data-stu-id="8d92a-121">Indicates that an object's text representation is obscured by characters such as asterisks.</span></span>|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|<span data-ttu-id="8d92a-122">Especifica si la propiedad a la que se enlaza este atributo es de solo lectura o de lectura y escritura en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="8d92a-122">Specifies whether the property this attribute is bound to is read-only or read/write at design time.</span></span>|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|<span data-ttu-id="8d92a-123">Indica que la cuadrícula de la propiedad debería actualizarse cuando cambia el valor de propiedad asociado.</span><span class="sxs-lookup"><span data-stu-id="8d92a-123">Indicates that the property grid should refresh when the associated property value changes.</span></span>|  
|<xref:System.ComponentModel.TypeConverterAttribute>|<span data-ttu-id="8d92a-124">Especifica el tipo que se debe utilizar como convertidor para el objeto al que está enlazado este atributo.</span><span class="sxs-lookup"><span data-stu-id="8d92a-124">Specifies what type to use as a converter for the object this attribute is bound to.</span></span>|  
  
## <a name="attributes-for-data-binding-properties"></a><span data-ttu-id="8d92a-125">Atributos para las propiedades de enlaces de datos</span><span class="sxs-lookup"><span data-stu-id="8d92a-125">Attributes for Data Binding Properties</span></span>  
 <span data-ttu-id="8d92a-126">En la tabla siguiente se muestran los atributos que se pueden aplicar para especificar cómo los controles y componentes personalizados interactúan con enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="8d92a-126">The following table shows the attributes you can apply to specify how your custom controls and components interact with data binding.</span></span>  
  
|<span data-ttu-id="8d92a-127">Atributo</span><span class="sxs-lookup"><span data-stu-id="8d92a-127">Attribute</span></span>|<span data-ttu-id="8d92a-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d92a-128">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|<span data-ttu-id="8d92a-129">Especifica si una propiedad se utiliza normalmente para enlace.</span><span class="sxs-lookup"><span data-stu-id="8d92a-129">Specifies whether a property is typically used for binding.</span></span>|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|<span data-ttu-id="8d92a-130">Especifica las propiedades del origen de datos y del miembro de datos para un componente.</span><span class="sxs-lookup"><span data-stu-id="8d92a-130">Specifies the data source and data member properties for a component.</span></span>|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|<span data-ttu-id="8d92a-131">Especifica la propiedad de enlace predeterminada para un componente.</span><span class="sxs-lookup"><span data-stu-id="8d92a-131">Specifies the default binding property for a component.</span></span>|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|<span data-ttu-id="8d92a-132">Especifica las propiedades del origen de datos y del miembro de datos para un componente.</span><span class="sxs-lookup"><span data-stu-id="8d92a-132">Specifies the data source and data member properties for a component.</span></span>|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|<span data-ttu-id="8d92a-133">Habilita la redirección del atributo.</span><span class="sxs-lookup"><span data-stu-id="8d92a-133">Enables attribute redirection.</span></span>|  
  
## <a name="attributes-for-classes"></a><span data-ttu-id="8d92a-134">Atributos para las clases</span><span class="sxs-lookup"><span data-stu-id="8d92a-134">Attributes for Classes</span></span>  
 <span data-ttu-id="8d92a-135">En la tabla siguiente se muestran los atributos que se pueden aplicar para especificar en tiempo de diseño el comportamiento de los controles y componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="8d92a-135">The following table shows the attributes you can apply to specify the behavior of your custom controls and components at design time.</span></span>  
  
|<span data-ttu-id="8d92a-136">Atributo</span><span class="sxs-lookup"><span data-stu-id="8d92a-136">Attribute</span></span>|<span data-ttu-id="8d92a-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d92a-137">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|<span data-ttu-id="8d92a-138">Especifica el evento predeterminado para un componente.</span><span class="sxs-lookup"><span data-stu-id="8d92a-138">Specifies the default event for a component.</span></span>|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|<span data-ttu-id="8d92a-139">Especifica la propiedad predeterminada para un componente.</span><span class="sxs-lookup"><span data-stu-id="8d92a-139">Specifies the default property for a component.</span></span>|  
|<xref:System.ComponentModel.DesignerAttribute>|<span data-ttu-id="8d92a-140">Especifica la clase utilizada para implementar, en tiempo de diseño, los servicios para un componente.</span><span class="sxs-lookup"><span data-stu-id="8d92a-140">Specifies the class used to implement design-time services for a component.</span></span>|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|<span data-ttu-id="8d92a-141">Especifica que el diseñador de una clase pertenece a una categoría determinada.</span><span class="sxs-lookup"><span data-stu-id="8d92a-141">Specifies that the designer for a class belongs to a certain category.</span></span>|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|<span data-ttu-id="8d92a-142">Representa un atributo de un elemento del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="8d92a-142">Represents an attribute of a toolbox item.</span></span>|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|<span data-ttu-id="8d92a-143">Especifica la cadena del filtro y el tipo de filtro que se va a utilizar para un elemento del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="8d92a-143">Specifies the filter string and filter type to use for a Toolbox item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d92a-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d92a-144">See Also</span></span>  
 <xref:System.Attribute>  
 [<span data-ttu-id="8d92a-145">Aplicar atributos en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d92a-145">How to: Apply Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="8d92a-146">Ampliar compatibilidad en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="8d92a-146">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [<span data-ttu-id="8d92a-147">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8d92a-147">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
