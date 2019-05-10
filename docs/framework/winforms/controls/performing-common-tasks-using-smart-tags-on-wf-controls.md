---
title: 'Tutorial: Realizar tareas comunes con etiquetas inteligentes en controles de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 1cc854d735ba88a301d6e2f6a83fe5c8bf881380
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211419"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="bc7ce-102">Tutorial: Realizar tareas comunes con etiquetas inteligentes en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc7ce-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>

<span data-ttu-id="bc7ce-103">Como construir formularios y controles para la aplicación de Windows Forms, hay muchas tareas que llevará a cabo varias veces.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="bc7ce-104">Estas son algunas de las tareas realizadas normalmente que encontrará:</span><span class="sxs-lookup"><span data-stu-id="bc7ce-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="bc7ce-105">Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="bc7ce-106">Acoplar un control a su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="bc7ce-107">Cambiar la orientación de un <xref:System.Windows.Forms.SplitContainer> control.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="bc7ce-108">Para acelerar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que le permiten realizar tareas comunes como éstas en un solo gesto en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="bc7ce-109">Estas tareas se denominan *verbos de etiquetas inteligentes*.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="bc7ce-110">Las etiquetas inteligentes permanecen adjuntas a una instancia del control de su duración en el diseñador y siempre están disponibles.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

<span data-ttu-id="bc7ce-111">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="bc7ce-111">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="bc7ce-112">Crear un proyecto de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc7ce-112">Creating a Windows Forms project</span></span>

- <span data-ttu-id="bc7ce-113">Uso de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="bc7ce-113">Using smart tags</span></span>

- <span data-ttu-id="bc7ce-114">Habilitación y deshabilitación de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="bc7ce-114">Enabling and Disabling Smart Tags</span></span>

<span data-ttu-id="bc7ce-115">Cuando termine, comprenderá el rol de estas importantes características de diseño.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="bc7ce-116">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="bc7ce-116">Create the project</span></span>

<span data-ttu-id="bc7ce-117">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-117">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="bc7ce-118">En Visual Studio, cree un proyecto de aplicación basada en Windows llamado "SmartTagsExample" (**archivo** > **New** > **proyecto**  >  **Visual C#**  o **Visual Basic** > **escritorio clásico de** > **Windows Forms Aplicación**).</span><span class="sxs-lookup"><span data-stu-id="bc7ce-118">In Visual Studio, create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="bc7ce-119">Seleccione el formulario en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-119">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="bc7ce-120">Utilizar etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="bc7ce-120">Use smart tags</span></span>

<span data-ttu-id="bc7ce-121">Las etiquetas inteligentes están siempre disponibles en tiempo de diseño de los controles que les ofrece.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-121">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="bc7ce-122">Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** hasta su formulario.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-122">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="bc7ce-123">Tenga en cuenta el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) que aparece en la en paralelo de la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-123">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="bc7ce-124">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-124">Click the smart-tag glyph.</span></span> <span data-ttu-id="bc7ce-125">En el menú contextual que aparece al lado del glifo, seleccione el **Agregar pestaña** elemento.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-125">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="bc7ce-126">Observe que una nueva página de ficha se agrega a la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-126">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="bc7ce-127">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-127">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="bc7ce-128">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-128">Click the smart-tag glyph.</span></span> <span data-ttu-id="bc7ce-129">En el menú contextual que aparece al lado del glifo, seleccione el **Agregar columna** elemento.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-129">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="bc7ce-130">Observe que se agrega una nueva columna a la <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-130">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="bc7ce-131">Arrastre un control <xref:System.Windows.Forms.SplitContainer> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-131">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="bc7ce-132">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-132">Click the smart-tag glyph.</span></span> <span data-ttu-id="bc7ce-133">En el menú contextual que aparece al lado del glifo, seleccione el **orientación del divisor Horizontal** elemento.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-133">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="bc7ce-134">Observe que el <xref:System.Windows.Forms.SplitContainer> barra divisora del control ahora está orientado horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="bc7ce-134">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc7ce-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc7ce-135">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="bc7ce-136">[Tutorial: Incorporación de etiquetas inteligentes a un componente de Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="bc7ce-136">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
