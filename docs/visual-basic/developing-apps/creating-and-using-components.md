---
title: Crear y utilizar componentes en Visual Basic
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 03929dd0dbb81a9efee5b69ede78ff0b4ab4d380
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="creating-and-using-components-in-visual-basic"></a><span data-ttu-id="940f5-102">Crear y utilizar componentes en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="940f5-102">Creating and Using Components in Visual Basic</span></span>
<span data-ttu-id="940f5-103">Un *componente* es una clase que implementa la interfaz <xref:System.ComponentModel.IComponent?displayProperty=fullName> o que deriva directa o indirectamente de una clase que implementa <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="940f5-103">A *component* is a class that implements the <xref:System.ComponentModel.IComponent?displayProperty=fullName> interface or that derives directly or indirectly from a class that implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="940f5-104">Un componente de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] es un objeto que se puede reutilizar, puede interactuar con otros objetos y proporciona control sobre recursos externos y sobre la compatibilidad en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="940f5-104">A [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] component is an object that is reusable, can interact with other objects, and provides control over external resources and design-time support.</span></span>  
  
 <span data-ttu-id="940f5-105">Una característica importante de los componentes es que se pueden diseñar, lo que significa que se puede usar una clase que es un componente en el entorno de desarrollo integrado de [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="940f5-105">An important feature of components is that they are designable, which means that a class that is a component can be used in the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Integrated Development Environment.</span></span> <span data-ttu-id="940f5-106">Los componentes se pueden agregar al cuadro de herramientas, se pueden arrastrar y soltar en un formulario y se pueden manipular en una superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="940f5-106">A component can be added to the Toolbox, dragged and dropped onto a form, and manipulated on a design surface.</span></span> <span data-ttu-id="940f5-107">Observe que la compatibilidad en tiempo de diseño de los componentes está integrada en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]; un programador de componentes no tiene que efectuar ninguna tarea adicional para aprovechar las funcionalidades base del tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="940f5-107">Notice that base design-time support for components is built into the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]; a component developer does not have to do any additional work to take advantage of the base design-time functionality.</span></span>  
  
 <span data-ttu-id="940f5-108">Un *control* es similar a un componente, ya que ambos se pueden diseñar,</span><span class="sxs-lookup"><span data-stu-id="940f5-108">A *control* is similar to a component, as both are designable.</span></span> <span data-ttu-id="940f5-109">con la diferencia de que un control proporciona una interfaz de usuario, mientras que un componente no.</span><span class="sxs-lookup"><span data-stu-id="940f5-109">However, a control provides a user interface, while a component does not.</span></span> <span data-ttu-id="940f5-110">Un control debe derivar de una de las clases de control base: <xref:System.Windows.Forms.Control> o <xref:System.Web.UI.Control>.</span><span class="sxs-lookup"><span data-stu-id="940f5-110">A control must derive from one of the base control classes: <xref:System.Windows.Forms.Control> or <xref:System.Web.UI.Control>.</span></span>  
  
## <a name="when-to-create-a-component"></a><span data-ttu-id="940f5-111">Cuándo se debe crear un componente</span><span class="sxs-lookup"><span data-stu-id="940f5-111">When to Create a Component</span></span>  
 <span data-ttu-id="940f5-112">Si la clase se va a usar en una superficie de diseño (como en Windows Forms o en el Diseñador de Web Forms) pero no tiene ninguna interfaz de usuario, debe ser un componente y debe implementar <xref:System.ComponentModel.IComponent>, o bien debe derivarse de una clase que implemente directa o indirectamente <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="940f5-112">If your class will be used on a design surface (such as the Windows Forms or Web Forms Designer) but has no user interface, it should be a component and implement <xref:System.ComponentModel.IComponent>, or derive from a class that directly or indirectly implements <xref:System.ComponentModel.IComponent>.</span></span>  
  
 <span data-ttu-id="940f5-113">Las clases <xref:System.ComponentModel.Component> y <xref:System.ComponentModel.MarshalByValueComponent> son implementaciones base de la interfaz <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="940f5-113">The <xref:System.ComponentModel.Component> and <xref:System.ComponentModel.MarshalByValueComponent> classes are base implementations of the <xref:System.ComponentModel.IComponent> interface.</span></span> <span data-ttu-id="940f5-114">La principal diferencia entre estas clases es que la clase <xref:System.ComponentModel.Component> se calcula por referencia, mientras que <xref:System.ComponentModel.IComponent> se calcula por valor.</span><span class="sxs-lookup"><span data-stu-id="940f5-114">The main difference between these classes is that the <xref:System.ComponentModel.Component> class is marshaled by reference, while <xref:System.ComponentModel.IComponent> is marshaled by value.</span></span> <span data-ttu-id="940f5-115">En la lista siguiente se proporcionan directrices generales para los implementadores.</span><span class="sxs-lookup"><span data-stu-id="940f5-115">The following list provides broad guidelines for implementers.</span></span>  
  
-   <span data-ttu-id="940f5-116">Si el componente se tiene que calcular por referencia, se debe derivar de <xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="940f5-116">If your component needs to be marshaled by reference, derive from <xref:System.ComponentModel.Component>.</span></span>  
  
-   <span data-ttu-id="940f5-117">Si el componente se tiene que calcular por valor, se debe derivar de <xref:System.ComponentModel.MarshalByValueComponent>.</span><span class="sxs-lookup"><span data-stu-id="940f5-117">If your component needs to be marshaled by value, derive from <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
-   <span data-ttu-id="940f5-118">Si el componente no se puede derivar de una de las implementaciones base debido a la herencia única, implemente <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="940f5-118">If your component cannot derive from one of the base implementations due to single inheritance, implement <xref:System.ComponentModel.IComponent>.</span></span>  
  
 <span data-ttu-id="940f5-119">Para obtener más información sobre la compatibilidad en tiempo de diseño, vea [Atributos en tiempo de diseño para componentes](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3) y [Ampliar compatibilidad en tiempo de diseño](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).</span><span class="sxs-lookup"><span data-stu-id="940f5-119">For more information about design-time support, see [Design-Time Attributes for Components](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3) and [Extending Design-Time Support](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).</span></span>  
  
## <a name="component-classes"></a><span data-ttu-id="940f5-120">Clases de componentes</span><span class="sxs-lookup"><span data-stu-id="940f5-120">Component Classes</span></span>  
 <span data-ttu-id="940f5-121">El espacio de nombres <xref:System.ComponentModel> proporciona clases que se usan para implementar el comportamiento de los componentes y controles en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="940f5-121">The <xref:System.ComponentModel> namespace provides classes that are used to implement the run-time and design-time behavior of components and controls.</span></span> <span data-ttu-id="940f5-122">Este espacio de nombres incluye las clases bases y las interfaces para implementar atributos y convertidores de tipos, enlazarlos con orígenes de datos y generar licencias para los componentes.</span><span class="sxs-lookup"><span data-stu-id="940f5-122">This namespace includes the base classes and interfaces for implementing attributes and type converters, binding to data sources, and licensing components.</span></span>  
  
 <span data-ttu-id="940f5-123">Las clases de componentes básicas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="940f5-123">The core component classes are:</span></span>  
  
-   <span data-ttu-id="940f5-124"><xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="940f5-124"><xref:System.ComponentModel.Component>.</span></span> <span data-ttu-id="940f5-125">Una implementación base para la interfaz <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="940f5-125">A base implementation for the <xref:System.ComponentModel.IComponent> interface.</span></span> <span data-ttu-id="940f5-126">Esta clase permite el uso compartido de objetos entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="940f5-126">This class enables object sharing between applications.</span></span>  
  
-   <span data-ttu-id="940f5-127"><xref:System.ComponentModel.MarshalByValueComponent>.</span><span class="sxs-lookup"><span data-stu-id="940f5-127"><xref:System.ComponentModel.MarshalByValueComponent>.</span></span> <span data-ttu-id="940f5-128">Una implementación base para la interfaz <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="940f5-128">A base implementation for the <xref:System.ComponentModel.IComponent> interface.</span></span>  
  
-   <span data-ttu-id="940f5-129"><xref:System.ComponentModel.Container>.</span><span class="sxs-lookup"><span data-stu-id="940f5-129"><xref:System.ComponentModel.Container>.</span></span> <span data-ttu-id="940f5-130">La implementación base de la interfaz <xref:System.ComponentModel.IContainer>.</span><span class="sxs-lookup"><span data-stu-id="940f5-130">The base implementation for the <xref:System.ComponentModel.IContainer> interface.</span></span> <span data-ttu-id="940f5-131">Esta clase encapsula cero o más componentes.</span><span class="sxs-lookup"><span data-stu-id="940f5-131">This class encapsulates zero or more components.</span></span>  
  
 <span data-ttu-id="940f5-132">Algunas de las clases usadas para la generación de licencias de componentes son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="940f5-132">Some of the classes used for component licensing are:</span></span>  
  
-   <span data-ttu-id="940f5-133"><xref:System.ComponentModel.License>.</span><span class="sxs-lookup"><span data-stu-id="940f5-133"><xref:System.ComponentModel.License>.</span></span> <span data-ttu-id="940f5-134">Clase base abstracta para todas las licencias.</span><span class="sxs-lookup"><span data-stu-id="940f5-134">The abstract base class for all licenses.</span></span> <span data-ttu-id="940f5-135">Las licencias se conceden a una instancia específica de un componente.</span><span class="sxs-lookup"><span data-stu-id="940f5-135">A license is granted to a specific instance of a component.</span></span>  
  
-   <span data-ttu-id="940f5-136"><xref:System.ComponentModel.LicenseManager>.</span><span class="sxs-lookup"><span data-stu-id="940f5-136"><xref:System.ComponentModel.LicenseManager>.</span></span> <span data-ttu-id="940f5-137">Proporciona propiedades y métodos para agregar una licencia a un componente y administrar un <xref:System.ComponentModel.LicenseProvider>.</span><span class="sxs-lookup"><span data-stu-id="940f5-137">Provides properties and methods to add a license to a component and to manage a <xref:System.ComponentModel.LicenseProvider>.</span></span>  
  
-   <span data-ttu-id="940f5-138"><xref:System.ComponentModel.LicenseProvider>.</span><span class="sxs-lookup"><span data-stu-id="940f5-138"><xref:System.ComponentModel.LicenseProvider>.</span></span> <span data-ttu-id="940f5-139">Clase base abstracta para implementar un proveedor de licencias.</span><span class="sxs-lookup"><span data-stu-id="940f5-139">The abstract base class for implementing a license provider.</span></span>  
  
-   <span data-ttu-id="940f5-140"><xref:System.ComponentModel.LicenseProviderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="940f5-140"><xref:System.ComponentModel.LicenseProviderAttribute>.</span></span> <span data-ttu-id="940f5-141">Especifica la clase <xref:System.ComponentModel.LicenseProvider> que se va a usar con una clase.</span><span class="sxs-lookup"><span data-stu-id="940f5-141">Specifies the <xref:System.ComponentModel.LicenseProvider> class to use with a class.</span></span>  
  
 <span data-ttu-id="940f5-142">Clases usadas habitualmente para describir y conservar componentes.</span><span class="sxs-lookup"><span data-stu-id="940f5-142">Classes commonly used for describing and persisting components.</span></span>  
  
-   <span data-ttu-id="940f5-143"><xref:System.ComponentModel.TypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="940f5-143"><xref:System.ComponentModel.TypeDescriptor>.</span></span> <span data-ttu-id="940f5-144">Proporciona información sobre las características de un componente, como sus atributos, propiedades y eventos.</span><span class="sxs-lookup"><span data-stu-id="940f5-144">Provides information about the characteristics for a component, such as its attributes, properties, and events.</span></span>  
  
-   <span data-ttu-id="940f5-145"><xref:System.ComponentModel.EventDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="940f5-145"><xref:System.ComponentModel.EventDescriptor>.</span></span> <span data-ttu-id="940f5-146">Proporciona información sobre un evento.</span><span class="sxs-lookup"><span data-stu-id="940f5-146">Provides information about an event.</span></span>  
  
-   <span data-ttu-id="940f5-147"><xref:System.ComponentModel.PropertyDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="940f5-147"><xref:System.ComponentModel.PropertyDescriptor>.</span></span> <span data-ttu-id="940f5-148">Proporciona información sobre una propiedad.</span><span class="sxs-lookup"><span data-stu-id="940f5-148">Provides information about a property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="940f5-149">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="940f5-149">Related Sections</span></span>  
 [<span data-ttu-id="940f5-150">Clase frente a componente y frente a control</span><span class="sxs-lookup"><span data-stu-id="940f5-150">Class vs. Component vs. Control</span></span>](http://msdn.microsoft.com/library/db8b842e-44d9-40cc-a0f8-70fd189632c3)  
 <span data-ttu-id="940f5-151">Define *componente* y *control* y describe las diferencias existentes entre estos y las clases.</span><span class="sxs-lookup"><span data-stu-id="940f5-151">Defines *component* and *control*, and discusses the differences between them and classes.</span></span>  
  
 [<span data-ttu-id="940f5-152">Creación de componentes</span><span class="sxs-lookup"><span data-stu-id="940f5-152">Component Authoring</span></span>](http://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 <span data-ttu-id="940f5-153">Guía de introducción a los componentes.</span><span class="sxs-lookup"><span data-stu-id="940f5-153">Roadmap for getting started with components.</span></span>  
  
 [<span data-ttu-id="940f5-154">Tutoriales sobre la creación de componentes</span><span class="sxs-lookup"><span data-stu-id="940f5-154">Component Authoring Walkthroughs</span></span>](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)  
 <span data-ttu-id="940f5-155">Vínculos a temas que proporcionan instrucciones paso a paso para la programación de componentes.</span><span class="sxs-lookup"><span data-stu-id="940f5-155">Links to topics that provide step-by-step instruction for component programming.</span></span>  
  
 [<span data-ttu-id="940f5-156">Clases de componentes</span><span class="sxs-lookup"><span data-stu-id="940f5-156">Component Classes</span></span>](http://msdn.microsoft.com/library/ce2e5647-e673-4c2b-8125-ffebbd9d71bc)  
 <span data-ttu-id="940f5-157">Se describe lo que convierte una clase en un componente, maneras de exponer la funcionalidad de los componentes, controlar el acceso a componentes y controlar cómo se crean instancias de los componentes.</span><span class="sxs-lookup"><span data-stu-id="940f5-157">Describes what makes a class a component, ways to expose component functionality, controlling access to components, and controlling how component instances are created.</span></span>  
  
 [<span data-ttu-id="940f5-158">Solución de problemas relacionados con la creación de controles y componentes</span><span class="sxs-lookup"><span data-stu-id="940f5-158">Troubleshooting Control and Component Authoring</span></span>](../../framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 <span data-ttu-id="940f5-159">Se explica cómo solucionar problemas comunes.</span><span class="sxs-lookup"><span data-stu-id="940f5-159">Explains how to fix common problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="940f5-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="940f5-160">See Also</span></span>  
 <span data-ttu-id="940f5-161">[Cómo: Obtener acceso a las funciones en tiempo de diseño de formularios Windows Forms](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09) </span><span class="sxs-lookup"><span data-stu-id="940f5-161">[How to: Access Design-Time Support in Windows Forms](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09) </span></span>  
 <span data-ttu-id="940f5-162">[Cómo: Extender la apariencia y el comportamiento de los controles en modo de diseño](http://msdn.microsoft.com/library/68f85054-2253-47f5-a4f2-3f1ac8c9f27b) </span><span class="sxs-lookup"><span data-stu-id="940f5-162">[How to: Extend the Appearance and Behavior of Controls in Design Mode](http://msdn.microsoft.com/library/68f85054-2253-47f5-a4f2-3f1ac8c9f27b) </span></span>  
 [<span data-ttu-id="940f5-163">Cómo: Llevar a cabo una inicialización personalizada de controles en modo de diseño</span><span class="sxs-lookup"><span data-stu-id="940f5-163">How to: Perform Custom Initialization for Controls in Design Mode</span></span>](http://msdn.microsoft.com/library/914eaa03-092f-4556-9160-b8a2a40641d9)

