---
title: Rendimiento de las tareas comunes con etiquetas inteligentes en los controles
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 826313d0a89410f62c034a5fba4dee32e90a1750
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744261"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="5f2f2-102">Tutorial: realizar tareas comunes con etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="5f2f2-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="5f2f2-103">A medida que crea formularios y controles para la aplicación de Windows Forms, hay muchas tareas que realizará repetidamente.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="5f2f2-104">Estas son algunas de las tareas que se realizan con frecuencia:</span><span class="sxs-lookup"><span data-stu-id="5f2f2-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="5f2f2-105">Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="5f2f2-106">Acoplar un control a su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="5f2f2-107">Cambiar la orientación de un control de <xref:System.Windows.Forms.SplitContainer>.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="5f2f2-108">Para agilizar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que le permiten realizar tareas comunes como estas en un solo gesto en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="5f2f2-109">Estas tareas se denominan *verbos de etiqueta inteligente*.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="5f2f2-110">Las etiquetas inteligentes permanecen adjuntas a una instancia de control para su duración en el diseñador y siempre están disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="5f2f2-111">Creación del proyecto</span><span class="sxs-lookup"><span data-stu-id="5f2f2-111">Create the project</span></span>

<span data-ttu-id="5f2f2-112">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="5f2f2-113">En Visual Studio, cree un proyecto de aplicación basada en Windows llamado **SmartTagsExample**.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="5f2f2-114">Seleccione el formulario en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="5f2f2-115">Usar etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="5f2f2-115">Use smart tags</span></span>

<span data-ttu-id="5f2f2-116">Las etiquetas inteligentes siempre están disponibles en tiempo de diseño en los controles que las ofrecen.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="5f2f2-117">Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="5f2f2-118">Tenga en cuenta el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif)) que aparece a la derecha de la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="5f2f2-119">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="5f2f2-120">En el menú contextual que aparece junto al glifo, seleccione el elemento de **pestaña agregar** .</span><span class="sxs-lookup"><span data-stu-id="5f2f2-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="5f2f2-121">Observe que se agrega una nueva página de pestañas a la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="5f2f2-122">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="5f2f2-123">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="5f2f2-124">En el menú contextual que aparece junto al glifo, seleccione el elemento **Agregar columna** .</span><span class="sxs-lookup"><span data-stu-id="5f2f2-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="5f2f2-125">Observe que se agrega una nueva columna al control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="5f2f2-126">Arrastre un control <xref:System.Windows.Forms.SplitContainer> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="5f2f2-127">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="5f2f2-128">En el menú contextual que aparece junto al glifo, seleccione el elemento de **orientación divisor horizontal** .</span><span class="sxs-lookup"><span data-stu-id="5f2f2-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="5f2f2-129">Observe que la barra divisora del control <xref:System.Windows.Forms.SplitContainer> ahora está orientada horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f2f2-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f2f2-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
