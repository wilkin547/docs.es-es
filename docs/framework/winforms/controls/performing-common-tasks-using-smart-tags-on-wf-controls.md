---
title: 'Tutorial: Realizar tareas comunes con etiquetas inteligentes en controles de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 34c14c0afd9632b06947fd72e46ddbda070cfb0f
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015765"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="6af65-102">Tutorial: Realizar tareas comunes con etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="6af65-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="6af65-103">A medida que crea formularios y controles para la aplicación de Windows Forms, hay muchas tareas que realizará repetidamente.</span><span class="sxs-lookup"><span data-stu-id="6af65-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="6af65-104">Estas son algunas de las tareas que se realizan con frecuencia:</span><span class="sxs-lookup"><span data-stu-id="6af65-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="6af65-105">Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="6af65-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="6af65-106">Acoplar un control a su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="6af65-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="6af65-107">Cambiar la orientación de un <xref:System.Windows.Forms.SplitContainer> control.</span><span class="sxs-lookup"><span data-stu-id="6af65-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="6af65-108">Para agilizar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que le permiten realizar tareas comunes como estas en un solo gesto en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="6af65-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="6af65-109">Estas tareas se denominan *verbos de etiqueta inteligente*.</span><span class="sxs-lookup"><span data-stu-id="6af65-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="6af65-110">Las etiquetas inteligentes permanecen adjuntas a una instancia de control para su duración en el diseñador y siempre están disponibles.</span><span class="sxs-lookup"><span data-stu-id="6af65-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="6af65-111">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="6af65-111">Create the project</span></span>

<span data-ttu-id="6af65-112">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="6af65-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="6af65-113">En Visual Studio, cree un proyecto de aplicación basada en Windows llamado **SmartTagsExample**.</span><span class="sxs-lookup"><span data-stu-id="6af65-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="6af65-114">Seleccione el formulario en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="6af65-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="6af65-115">Usar etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="6af65-115">Use smart tags</span></span>

<span data-ttu-id="6af65-116">Las etiquetas inteligentes siempre están disponibles en tiempo de diseño en los controles que las ofrecen.</span><span class="sxs-lookup"><span data-stu-id="6af65-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="6af65-117">Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="6af65-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="6af65-118">Observe el glifo de etiqueta inteligente (![glifo](./media/vs-winformsmttagglyph.gif)de etiqueta inteligente) que aparece <xref:System.Windows.Forms.TabControl>en el lado de.</span><span class="sxs-lookup"><span data-stu-id="6af65-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="6af65-119">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="6af65-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="6af65-120">En el menú contextual que aparece junto al glifo, seleccione el elemento de **pestaña agregar** .</span><span class="sxs-lookup"><span data-stu-id="6af65-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="6af65-121">Observe que se agrega una nueva página de pestañas <xref:System.Windows.Forms.TabControl>a.</span><span class="sxs-lookup"><span data-stu-id="6af65-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="6af65-122">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="6af65-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="6af65-123">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="6af65-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="6af65-124">En el menú contextual que aparece junto al glifo, seleccione el elemento **Agregar columna** .</span><span class="sxs-lookup"><span data-stu-id="6af65-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="6af65-125">Observe que se agrega una nueva columna al <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="6af65-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="6af65-126">Arrastre un control <xref:System.Windows.Forms.SplitContainer> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="6af65-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="6af65-127">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="6af65-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="6af65-128">En el menú contextual que aparece junto al glifo, seleccione el elemento de **orientación divisor horizontal** .</span><span class="sxs-lookup"><span data-stu-id="6af65-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="6af65-129">Observe que la <xref:System.Windows.Forms.SplitContainer> barra divisora del control ahora está orientada horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="6af65-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="6af65-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="6af65-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
