---
title: Realizar tareas comunes con acciones de diseñador en controles
ms.date: 02/13/2019
helpviewer_keywords:
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 342741b9ce032b1b8ec50a6c689d9109d12f5b3b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634898"
---
# <a name="walkthrough-perform-common-tasks-using-designer-actions"></a><span data-ttu-id="96ca2-102">Tutorial: realizar tareas comunes con las acciones del diseñador</span><span class="sxs-lookup"><span data-stu-id="96ca2-102">Walkthrough: Perform common tasks using designer actions</span></span>

<span data-ttu-id="96ca2-103">A medida que crea formularios y controles para la aplicación de Windows Forms, hay muchas tareas que realizará repetidamente.</span><span class="sxs-lookup"><span data-stu-id="96ca2-103">As you construct forms and controls for your Windows Forms application, there are many tasks you'll perform repeatedly.</span></span> <span data-ttu-id="96ca2-104">En la lista siguiente se muestran algunas de las tareas que se realizan con frecuencia:</span><span class="sxs-lookup"><span data-stu-id="96ca2-104">The following list shows some of the commonly performed tasks you'll come across:</span></span>

- <span data-ttu-id="96ca2-105">Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="96ca2-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>
- <span data-ttu-id="96ca2-106">Acoplar un control a su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="96ca2-106">Docking a control to its parent.</span></span>
- <span data-ttu-id="96ca2-107">Cambiar la orientación de un control de <xref:System.Windows.Forms.SplitContainer>.</span><span class="sxs-lookup"><span data-stu-id="96ca2-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="96ca2-108">Para agilizar el desarrollo, muchos controles ofrecen acciones de diseñador, que son menús contextuales que le permiten realizar tareas comunes como estas en un solo gesto en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="96ca2-108">To speed development, many controls offer designer actions, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="96ca2-109">Estas tareas se denominan *verbos de acciones del diseñador*.</span><span class="sxs-lookup"><span data-stu-id="96ca2-109">These tasks are called *designer actions verbs*.</span></span>

<span data-ttu-id="96ca2-110">Las acciones del diseñador permanecen adjuntas a una instancia del control para su duración en el diseñador y siempre están disponibles.</span><span class="sxs-lookup"><span data-stu-id="96ca2-110">Designer actions remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="96ca2-111">Creación del proyecto</span><span class="sxs-lookup"><span data-stu-id="96ca2-111">Create the project</span></span>

<span data-ttu-id="96ca2-112">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="96ca2-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="96ca2-113">En Visual Studio, cree un proyecto de aplicación basada en Windows llamado **DesignerActionsExample**.</span><span class="sxs-lookup"><span data-stu-id="96ca2-113">In Visual Studio, create a Windows-based application project called **DesignerActionsExample**.</span></span>

2. <span data-ttu-id="96ca2-114">Seleccione el formulario en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="96ca2-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-designer-actions"></a><span data-ttu-id="96ca2-115">Usar acciones del diseñador</span><span class="sxs-lookup"><span data-stu-id="96ca2-115">Use designer actions</span></span>

<span data-ttu-id="96ca2-116">Las acciones del diseñador siempre están disponibles en tiempo de diseño en los controles que las ofrecen.</span><span class="sxs-lookup"><span data-stu-id="96ca2-116">Designer actions are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="96ca2-117">Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="96ca2-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="96ca2-118">Observe el glifo de acciones del diseñador (![flecha negra pequeña](./media/designer-actions-glyph.gif)) que aparece a la derecha de la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="96ca2-118">Note the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="96ca2-119">Haga clic en el glifo de acciones del diseñador.</span><span class="sxs-lookup"><span data-stu-id="96ca2-119">Click the designer actions glyph.</span></span> <span data-ttu-id="96ca2-120">En el menú contextual que aparece junto al glifo, seleccione el elemento de **pestaña agregar** .</span><span class="sxs-lookup"><span data-stu-id="96ca2-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="96ca2-121">Observe que se agrega una nueva página de pestañas a la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="96ca2-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="96ca2-122">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="96ca2-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="96ca2-123">Haga clic en el glifo de acciones del diseñador.</span><span class="sxs-lookup"><span data-stu-id="96ca2-123">Click the designer actions glyph.</span></span> <span data-ttu-id="96ca2-124">En el menú contextual que aparece junto al glifo, seleccione el elemento **Agregar columna** .</span><span class="sxs-lookup"><span data-stu-id="96ca2-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="96ca2-125">Observe que se agrega una nueva columna al control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="96ca2-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="96ca2-126">Arrastre un control <xref:System.Windows.Forms.SplitContainer> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="96ca2-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="96ca2-127">Haga clic en el glifo de acciones del diseñador.</span><span class="sxs-lookup"><span data-stu-id="96ca2-127">Click the designer actions glyph.</span></span> <span data-ttu-id="96ca2-128">En el menú contextual que aparece junto al glifo, seleccione el elemento de **orientación divisor horizontal** .</span><span class="sxs-lookup"><span data-stu-id="96ca2-128">In the shortcut menu that appears next to the glyph, select the **Horizontal Splitter Orientation** item.</span></span> <span data-ttu-id="96ca2-129">Observe que la barra divisora del control <xref:System.Windows.Forms.SplitContainer> ahora está orientada horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="96ca2-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="96ca2-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96ca2-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
