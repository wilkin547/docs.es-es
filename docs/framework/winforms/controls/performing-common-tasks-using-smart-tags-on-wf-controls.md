---
title: 'Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07fb43a711ae8b1e2e375b17b136c07f35b1cf39
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459577"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="72f45-102">Tutorial: realizar tareas comunes con etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="72f45-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="72f45-103">A medida que crea formularios y controles para la aplicación de Windows Forms, hay muchas tareas que realizará repetidamente.</span><span class="sxs-lookup"><span data-stu-id="72f45-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="72f45-104">Estas son algunas de las tareas que se realizan con frecuencia:</span><span class="sxs-lookup"><span data-stu-id="72f45-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="72f45-105">Agregar o quitar una pestaña en un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="72f45-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="72f45-106">Acoplar un control a su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="72f45-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="72f45-107">Cambiar la orientación de un control de <xref:System.Windows.Forms.SplitContainer>.</span><span class="sxs-lookup"><span data-stu-id="72f45-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="72f45-108">Para agilizar el desarrollo, muchos controles ofrecen etiquetas inteligentes, que son menús contextuales que le permiten realizar tareas comunes como estas en un solo gesto en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="72f45-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="72f45-109">Estas tareas se denominan *verbos de etiqueta inteligente*.</span><span class="sxs-lookup"><span data-stu-id="72f45-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="72f45-110">Las etiquetas inteligentes permanecen adjuntas a una instancia de control para su duración en el diseñador y siempre están disponibles.</span><span class="sxs-lookup"><span data-stu-id="72f45-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="72f45-111">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="72f45-111">Create the project</span></span>

<span data-ttu-id="72f45-112">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="72f45-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="72f45-113">En Visual Studio, cree un proyecto de aplicación basada en Windows llamado **SmartTagsExample**.</span><span class="sxs-lookup"><span data-stu-id="72f45-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="72f45-114">Seleccione el formulario en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="72f45-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="72f45-115">Usar etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="72f45-115">Use smart tags</span></span>

<span data-ttu-id="72f45-116">Las etiquetas inteligentes siempre están disponibles en tiempo de diseño en los controles que las ofrecen.</span><span class="sxs-lookup"><span data-stu-id="72f45-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="72f45-117">Arrastre un <xref:System.Windows.Forms.TabControl> desde el **cuadro de herramientas** hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="72f45-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="72f45-118">Tenga en cuenta el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif)) que aparece a la derecha de la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="72f45-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="72f45-119">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="72f45-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="72f45-120">En el menú contextual que aparece junto al glifo, seleccione el elemento de **pestaña agregar** .</span><span class="sxs-lookup"><span data-stu-id="72f45-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="72f45-121">Observe que se agrega una nueva página de pestañas a la <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="72f45-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="72f45-122">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="72f45-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="72f45-123">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="72f45-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="72f45-124">En el menú contextual que aparece junto al glifo, seleccione el elemento **Agregar columna** .</span><span class="sxs-lookup"><span data-stu-id="72f45-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="72f45-125">Observe que se agrega una nueva columna al control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="72f45-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="72f45-126">Arrastre un control <xref:System.Windows.Forms.SplitContainer> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="72f45-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="72f45-127">Haga clic en el glifo de etiqueta inteligente.</span><span class="sxs-lookup"><span data-stu-id="72f45-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="72f45-128">En el menú contextual que aparece junto al glifo, seleccione el elemento de **orientación divisor horizontal** .</span><span class="sxs-lookup"><span data-stu-id="72f45-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="72f45-129">Observe que la barra divisora del control <xref:System.Windows.Forms.SplitContainer> ahora está orientada horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="72f45-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="72f45-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="72f45-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
