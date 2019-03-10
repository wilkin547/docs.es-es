---
title: 'Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 2805ebc66be5908c333e9a5db41076518ad77c1a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705862"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="01fe9-102">Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01fe9-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="01fe9-103">Como construir formularios y controles para la aplicación de Windows Forms, hay muchas tareas que llevará a cabo varias veces.</span><span class="sxs-lookup"><span data-stu-id="01fe9-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="01fe9-104">Estas son algunas de las tareas realizadas normalmente que encontrará:</span><span class="sxs-lookup"><span data-stu-id="01fe9-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="01fe9-105">Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="01fe9-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="01fe9-106">Acoplar un control a su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="01fe9-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="01fe9-107">Cambiar la orientación de un <xref:System.Windows.Forms.SplitContainer> control.</span><span class="sxs-lookup"><span data-stu-id="01fe9-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="01fe9-108">Para acelerar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que le permiten realizar tareas comunes como éstas en un solo gesto en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="01fe9-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="01fe9-109">Estas tareas se denominan *verbos de etiquetas inteligentes*.</span><span class="sxs-lookup"><span data-stu-id="01fe9-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="01fe9-110">Las etiquetas inteligentes permanecen adjuntas a una instancia del control de su duración en el diseñador y siempre están disponibles.</span><span class="sxs-lookup"><span data-stu-id="01fe9-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="01fe9-111">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="01fe9-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="01fe9-112">Crear un proyecto de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01fe9-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="01fe9-113">Uso de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="01fe9-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="01fe9-114">Habilitación y deshabilitación de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="01fe9-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="01fe9-115">Cuando termine, comprenderá el rol de estas importantes características de diseño.</span><span class="sxs-lookup"><span data-stu-id="01fe9-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01fe9-116">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="01fe9-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="01fe9-117">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="01fe9-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="01fe9-118">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="01fe9-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="01fe9-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="01fe9-119">Creating the Project</span></span>  
 <span data-ttu-id="01fe9-120">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="01fe9-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="01fe9-121">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="01fe9-121">To create the project</span></span>  
  
1.  <span data-ttu-id="01fe9-122">Cree un proyecto de aplicación basada en Windows llamado "SmartTagsExample" (**archivo** > **New** > **proyecto**  >   **Visual C#** o **Visual Basic** > **escritorio clásico de** > **aplicación de Windows Forms**).</span><span class="sxs-lookup"><span data-stu-id="01fe9-122">Create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="01fe9-123">Seleccione el formulario en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="01fe9-123">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="01fe9-124">Uso de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="01fe9-124">Using Smart Tags</span></span>  
 <span data-ttu-id="01fe9-125">Las etiquetas inteligentes están siempre disponibles en tiempo de diseño de los controles que les ofrece.</span><span class="sxs-lookup"><span data-stu-id="01fe9-125">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="01fe9-126">Utilizar etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="01fe9-126">To use smart tags</span></span>  
  
1.  <span data-ttu-id="01fe9-127">Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** hasta su formulario.</span><span class="sxs-lookup"><span data-stu-id="01fe9-127">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="01fe9-128">Tenga en cuenta el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) que aparece en la en paralelo de la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="01fe9-128">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="01fe9-129">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="01fe9-129">Click the smart-tag glyph.</span></span> <span data-ttu-id="01fe9-130">En el menú contextual que aparece al lado del glifo, seleccione el **Agregar pestaña** elemento.</span><span class="sxs-lookup"><span data-stu-id="01fe9-130">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="01fe9-131">Observe que una nueva página de ficha se agrega a la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="01fe9-131">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="01fe9-132">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="01fe9-132">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="01fe9-133">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="01fe9-133">Click the smart-tag glyph.</span></span> <span data-ttu-id="01fe9-134">En el menú contextual que aparece al lado del glifo, seleccione el **Agregar columna** elemento.</span><span class="sxs-lookup"><span data-stu-id="01fe9-134">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="01fe9-135">Observe que se agrega una nueva columna a la <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="01fe9-135">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="01fe9-136">Arrastre un control <xref:System.Windows.Forms.SplitContainer> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="01fe9-136">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="01fe9-137">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="01fe9-137">Click the smart-tag glyph.</span></span> <span data-ttu-id="01fe9-138">En el menú contextual que aparece al lado del glifo, seleccione el **orientación del divisor Horizontal** elemento.</span><span class="sxs-lookup"><span data-stu-id="01fe9-138">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="01fe9-139">Observe que el <xref:System.Windows.Forms.SplitContainer> barra divisora del control ahora está orientado horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="01fe9-139">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01fe9-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="01fe9-140">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="01fe9-141">[Tutorial: Incorporación de etiquetas inteligentes a un componente de Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="01fe9-141">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
