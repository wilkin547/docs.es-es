---
title: Desarrollo de controles en tiempo de diseño
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: dac049ea6a51037daa0e23dc93476e4410b2df06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745983"
---
# <a name="develop-windows-forms-controls-at-design-time"></a><span data-ttu-id="01abf-102">Desarrollar controles Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="01abf-102">Develop Windows Forms controls at design time</span></span>

<span data-ttu-id="01abf-103">Para los autores de controles, .NET Framework proporciona una gran cantidad de tecnologías de creación de controles.</span><span class="sxs-lookup"><span data-stu-id="01abf-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="01abf-104">Los creadores ya no están limitados al diseño de controles compuestos que actúan como una colección de controles preexistentes.</span><span class="sxs-lookup"><span data-stu-id="01abf-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="01abf-105">A través de la herencia, puede crear sus propios controles a partir de controles compuestos preexistentes o de controles de Windows Forms preexistentes.</span><span class="sxs-lookup"><span data-stu-id="01abf-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="01abf-106">También puede diseñar sus propios controles que implementen el dibujo personalizado.</span><span class="sxs-lookup"><span data-stu-id="01abf-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="01abf-107">Estas opciones permiten una gran flexibilidad en el diseño y la funcionalidad de la interfaz visual.</span><span class="sxs-lookup"><span data-stu-id="01abf-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="01abf-108">Para aprovechar estas características, debe estar familiarizado con conceptos de programación basada en objetos.</span><span class="sxs-lookup"><span data-stu-id="01abf-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="01abf-109">No es necesario tener un conocimiento exhaustivo de la herencia, pero puede que le resulte útil hacer referencia a los [conceptos básicos de la herencia (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="01abf-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>

<span data-ttu-id="01abf-110">Si quiere crear controles personalizados para usarlos en formularios Web Forms, consulte [Desarrollar controles de servidor ASP.NET personalizados](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="01abf-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="01abf-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="01abf-111">In this section</span></span>

<span data-ttu-id="01abf-112">[Tutorial: crear un control compuesto](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-112">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="01abf-113">Muestra cómo crear un control compuesto simple en C#.</span><span class="sxs-lookup"><span data-stu-id="01abf-113">Shows how to create a simple composite control in C#.</span></span>

<span data-ttu-id="01abf-114">[Tutorial: heredar de un Control Windows Forms](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-114">[Walkthrough: Inheriting from a Windows Forms Control](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="01abf-115">Muestra cómo crear un control de Windows Forms simple utilizando la herencia en C#.</span><span class="sxs-lookup"><span data-stu-id="01abf-115">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>

<span data-ttu-id="01abf-116">[Tutorial: realizar tareas comunes utilizando etiquetas inteligentes en controles de Windows Forms](performing-common-tasks-using-smart-tags-on-wf-controls.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-116">[Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](performing-common-tasks-using-smart-tags-on-wf-controls.md)</span></span>\
<span data-ttu-id="01abf-117">Muestra cómo usar la característica de etiquetas inteligentes en controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="01abf-117">Shows how to use the smart tag feature on Windows Forms controls.</span></span>

<span data-ttu-id="01abf-118">[Tutorial: serializar colecciones de tipos estándar con la\ DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-118">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)\</span></span>
<span data-ttu-id="01abf-119">Muestra cómo usar el atributo <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> para serializar una colección.</span><span class="sxs-lookup"><span data-stu-id="01abf-119">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>

<span data-ttu-id="01abf-120">[Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-120">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="01abf-121">Muestra cómo depurar el comportamiento en tiempo de diseño de un control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="01abf-121">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>

<span data-ttu-id="01abf-122">[Tutorial: crear un control de Windows Forms que aprovecha las características en tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-122">[Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md)</span></span>\
<span data-ttu-id="01abf-123">Muestra cómo integrar estrechamente un control compuesto en el entorno de diseño.</span><span class="sxs-lookup"><span data-stu-id="01abf-123">Shows how to tightly integrate a composite control into the design environment.</span></span>

<span data-ttu-id="01abf-124">[Cómo: Crear controles para Windows Forms](how-to-author-controls-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-124">[How to: Author Controls for Windows Forms](how-to-author-controls-for-windows-forms.md)</span></span>\
<span data-ttu-id="01abf-125">Proporciona información general sobre consideraciones para implementar un control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="01abf-125">Provides an overview of considerations for implementing a Windows Forms control.</span></span>

<span data-ttu-id="01abf-126">[Cómo: Crear controles compuestos](how-to-author-composite-controls.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-126">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>\
<span data-ttu-id="01abf-127">Muestra cómo crear un control al heredar de un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="01abf-127">Shows how to create a control by inheriting from a composite control.</span></span>

<span data-ttu-id="01abf-128">[Cómo: Heredar de una clase UserControl](how-to-inherit-from-the-usercontrol-class.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-128">[How to: Inherit from the UserControl Class](how-to-inherit-from-the-usercontrol-class.md)</span></span>\
<span data-ttu-id="01abf-129">Proporciona información general sobre el procedimiento para crear un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="01abf-129">Provides an overview of the procedure for creating a composite control.</span></span>

<span data-ttu-id="01abf-130">[Cómo: Heredar de controles de Windows Forms existentes](how-to-inherit-from-existing-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-130">[How to: Inherit from Existing Windows Forms Controls](how-to-inherit-from-existing-windows-forms-controls.md)</span></span>\
<span data-ttu-id="01abf-131">Muestra cómo crear un control extendido heredando de la clase de control <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="01abf-131">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>

<span data-ttu-id="01abf-132">[Cómo: Heredar de una clase de control](how-to-inherit-from-the-control-class.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-132">[How to: Inherit from the Control Class](how-to-inherit-from-the-control-class.md)</span></span>\
<span data-ttu-id="01abf-133">Proporciona información general sobre la creación de un control extendido.</span><span class="sxs-lookup"><span data-stu-id="01abf-133">Provides an overview of creating an extended control.</span></span>

<span data-ttu-id="01abf-134">[Cómo: alinear un control con los bordes de los formularios en tiempo de diseño](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-134">[How to: Align a Control to the Edges of Forms at Design Time](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span></span>\
<span data-ttu-id="01abf-135">Muestra cómo usar la propiedad <xref:System.Windows.Forms.Control.Dock%2A> para alinear el control con el borde del formulario que ocupa.</span><span class="sxs-lookup"><span data-stu-id="01abf-135">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="01abf-136">[Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-136">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>\
<span data-ttu-id="01abf-137">Muestra el procedimiento para instalar el control de modo que aparezca en el cuadro de diálogo **Customize Toolbox** (Personalizar cuadro de herramientas).</span><span class="sxs-lookup"><span data-stu-id="01abf-137">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>

<span data-ttu-id="01abf-138">[Cómo: proporcionar un mapa de bits del cuadro de herramientas para un Control](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-138">[How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span></span>\
<span data-ttu-id="01abf-139">Muestra cómo utilizar el <xref:System.Drawing.ToolboxBitmapAttribute> para mostrar un icono junto al control personalizado en el cuadro de **herramientas**.</span><span class="sxs-lookup"><span data-stu-id="01abf-139">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="01abf-140">[Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-140">[How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span></span>\
<span data-ttu-id="01abf-141">Muestra cómo utilizar **UserControl Test Container** para probar el comportamiento de un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="01abf-141">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>

<span data-ttu-id="01abf-142">[Errores en tiempo de diseño en el Diseñador de Windows Forms](design-time-errors-in-the-windows-forms-designer.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-142">[Design-Time Errors in the Windows Forms Designer](design-time-errors-in-the-windows-forms-designer.md)</span></span>\
<span data-ttu-id="01abf-143">Explica el significado y el uso de la lista de errores de tiempo de diseño que aparece en Microsoft Visual Studio cuando no se puede cargar el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="01abf-143">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>

<span data-ttu-id="01abf-144">[Solución de problemas relacionados con la creación de controles y componentes](troubleshooting-control-and-component-authoring.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-144">[Troubleshooting Control and Component Authoring](troubleshooting-control-and-component-authoring.md)</span></span>\
<span data-ttu-id="01abf-145">Muestra cómo diagnosticar y corregir los problemas comunes que pueden producirse al crear un componente o control personalizados.</span><span class="sxs-lookup"><span data-stu-id="01abf-145">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>

## <a name="reference"></a><span data-ttu-id="01abf-146">Referencia</span><span class="sxs-lookup"><span data-stu-id="01abf-146">Reference</span></span>

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a><span data-ttu-id="01abf-147">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="01abf-147">Related sections</span></span>

<span data-ttu-id="01abf-148">[Desarrollar controles personalizados de formularios Windows Forms con .NET Framework](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-148">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="01abf-149">Describe cómo crear sus propios controles personalizados con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01abf-149">Discusses how to create your own custom controls with the .NET Framework.</span></span>

<span data-ttu-id="01abf-150">[Independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-150">[Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md)</span></span>\
<span data-ttu-id="01abf-151">Presenta Common Language Runtime, que está diseñado para simplificar la creación y el uso de componentes.</span><span class="sxs-lookup"><span data-stu-id="01abf-151">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="01abf-152">Un aspecto importante de esta simplificación es la interoperabilidad mejorada entre los componentes escritos con diferentes lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="01abf-152">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="01abf-153">Common Language Specification (CLS) hace posible crear herramientas y componentes que funcionen con varios lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="01abf-153">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>

<span data-ttu-id="01abf-154">[Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span><span class="sxs-lookup"><span data-stu-id="01abf-154">[Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span></span>\
<span data-ttu-id="01abf-155">Describe cómo habilitar que el componente o el control se muestren en el cuadro de diálogo **Customize Toolbox** (Personalizar cuadro de herramientas).</span><span class="sxs-lookup"><span data-stu-id="01abf-155">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
