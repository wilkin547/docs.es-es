---
title: 'Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7a29b7224a3f4b692fdfb3afaf58d9744bafcc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="3db8b-102">Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3db8b-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="3db8b-103">Medida que genera los formularios y controles para la aplicación de formularios Windows Forms, hay muchas tareas que se realiza con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="3db8b-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="3db8b-104">Estas son algunas de las tareas realizadas normalmente que encontrará:</span><span class="sxs-lookup"><span data-stu-id="3db8b-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="3db8b-105">Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="3db8b-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="3db8b-106">Acoplar un control a su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="3db8b-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="3db8b-107">Cambiar la orientación de un <xref:System.Windows.Forms.SplitContainer> control.</span><span class="sxs-lookup"><span data-stu-id="3db8b-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="3db8b-108">Para acelerar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que le permiten realizar tareas comunes, como en una sola operación en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="3db8b-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="3db8b-109">Estas tareas se denominan *verbos de etiqueta inteligente*.</span><span class="sxs-lookup"><span data-stu-id="3db8b-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="3db8b-110">Las etiquetas inteligentes permanecen conectadas a una instancia de control durante su duración en el diseñador y siempre están disponibles.</span><span class="sxs-lookup"><span data-stu-id="3db8b-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="3db8b-111">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="3db8b-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="3db8b-112">Crear un proyecto de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3db8b-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="3db8b-113">Uso de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="3db8b-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="3db8b-114">Habilitar y deshabilitar las etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="3db8b-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="3db8b-115">Cuando termine, comprenderá el rol de estas importantes características de diseño.</span><span class="sxs-lookup"><span data-stu-id="3db8b-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3db8b-116">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="3db8b-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3db8b-117">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="3db8b-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3db8b-118">Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="3db8b-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="3db8b-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="3db8b-119">Creating the Project</span></span>  
 <span data-ttu-id="3db8b-120">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="3db8b-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="3db8b-121">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="3db8b-121">To create the project</span></span>  
  
1.  <span data-ttu-id="3db8b-122">Cree un proyecto de aplicación basada en Windows llamado "SmartTagsExample".</span><span class="sxs-lookup"><span data-stu-id="3db8b-122">Create a Windows-based application project called "SmartTagsExample".</span></span> <span data-ttu-id="3db8b-123">Para ver detalles, consulte [Cómo: Crear un nuevo proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="3db8b-123">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="3db8b-124">Seleccione el formulario en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="3db8b-124">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="3db8b-125">Uso de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="3db8b-125">Using Smart Tags</span></span>  
 <span data-ttu-id="3db8b-126">Las etiquetas inteligentes están siempre disponibles en tiempo de diseño de los controles que les ofrece.</span><span class="sxs-lookup"><span data-stu-id="3db8b-126">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="3db8b-127">Utilizar etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="3db8b-127">To use smart tags</span></span>  
  
1.  <span data-ttu-id="3db8b-128">Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="3db8b-128">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="3db8b-129">Tenga en cuenta el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) que aparece en paralelo de la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="3db8b-129">Note the smart-tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="3db8b-130">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="3db8b-130">Click the smart-tag glyph.</span></span> <span data-ttu-id="3db8b-131">En el menú contextual que aparece al lado del glifo, seleccione el **Agregar pestaña** elemento.</span><span class="sxs-lookup"><span data-stu-id="3db8b-131">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="3db8b-132">Observe que se agrega una nueva página de fichas a la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="3db8b-132">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="3db8b-133">Arrastre un <xref:System.Windows.Forms.TableLayoutPanel> controlar desde la **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="3db8b-133">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="3db8b-134">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="3db8b-134">Click the smart-tag glyph.</span></span> <span data-ttu-id="3db8b-135">En el menú contextual que aparece al lado del glifo, seleccione el **Agregar columna** elemento.</span><span class="sxs-lookup"><span data-stu-id="3db8b-135">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="3db8b-136">Observe que se agrega una nueva columna a la <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="3db8b-136">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="3db8b-137">Arrastre un <xref:System.Windows.Forms.SplitContainer> controlar desde la **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="3db8b-137">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="3db8b-138">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="3db8b-138">Click the smart-tag glyph.</span></span> <span data-ttu-id="3db8b-139">En el menú contextual que aparece al lado del glifo, seleccione el **orientación del divisor Horizontal** elemento.</span><span class="sxs-lookup"><span data-stu-id="3db8b-139">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="3db8b-140">Observe que el <xref:System.Windows.Forms.SplitContainer> barra divisora del control ahora está orientado horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="3db8b-140">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db8b-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="3db8b-141">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [<span data-ttu-id="3db8b-142">Tutorial: Agregar etiquetas inteligentes a un componente de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3db8b-142">Walkthrough: Adding Smart Tags to a Windows Forms Component</span></span>](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
