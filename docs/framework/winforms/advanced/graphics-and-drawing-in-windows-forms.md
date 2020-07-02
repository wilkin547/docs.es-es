---
title: Gráficos y dibujo
description: Obtenga información sobre los objetos Graphics, Pen, Brush y color, y cómo realizar tareas como dibujar formas, dibujar texto o mostrar imágenes en Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 58d8cde6aa102225cf9e3c342efe37218c818307
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618407"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="aeb66-103">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aeb66-103">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="aeb66-104">En el Common Language Runtime se usa una implementación avanzada de Windows Interfaz de dispositivo gráfico (GDI) denominada GDI+.</span><span class="sxs-lookup"><span data-stu-id="aeb66-104">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="aeb66-105">Con GDI+ puede crear gráficos, dibujar texto y manipular imágenes gráficas como objetos.</span><span class="sxs-lookup"><span data-stu-id="aeb66-105">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="aeb66-106">GDI+ está diseñado para ofrecer rendimiento y facilidad de uso.</span><span class="sxs-lookup"><span data-stu-id="aeb66-106">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="aeb66-107">Puede usar GDI+ para representar imágenes gráficas en Windows Forms y controles.</span><span class="sxs-lookup"><span data-stu-id="aeb66-107">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="aeb66-108">Aunque no puede usar GDI+ directamente en formularios Web Forms, puede mostrar imágenes gráficas mediante el control imagen de servidor Web.</span><span class="sxs-lookup"><span data-stu-id="aeb66-108">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="aeb66-109">En esta sección, encontrará temas que presentan los aspectos básicos de la programación con GDI+.</span><span class="sxs-lookup"><span data-stu-id="aeb66-109">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="aeb66-110">Aunque no pretende ser una referencia exhaustiva, esta sección incluye información sobre los objetos <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> y <xref:System.Drawing.Color>, y explica cómo realizar tareas tales como dibujar formas, dibujar texto o mostrar imágenes.</span><span class="sxs-lookup"><span data-stu-id="aeb66-110">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="aeb66-111">Para obtener más información, vea [referencia de GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="aeb66-111">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="aeb66-112">Si quiere incorporarse y empezar a trabajar inmediatamente, vea [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="aeb66-112">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="aeb66-113">Encontrará temas sobre cómo usar código para dibujar líneas, formas, texto y mucho más en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="aeb66-113">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aeb66-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="aeb66-114">In This Section</span></span>  
 [<span data-ttu-id="aeb66-115">Información general sobre gráficos</span><span class="sxs-lookup"><span data-stu-id="aeb66-115">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="aeb66-116">Proporciona una introducción a las clases administradas relacionadas con gráficos.</span><span class="sxs-lookup"><span data-stu-id="aeb66-116">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="aeb66-117">Código administrado de GDI+</span><span class="sxs-lookup"><span data-stu-id="aeb66-117">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="aeb66-118">Proporciona información sobre las clases administradas de GDI+.</span><span class="sxs-lookup"><span data-stu-id="aeb66-118">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="aeb66-119">Utilizar clases gráficas administradas</span><span class="sxs-lookup"><span data-stu-id="aeb66-119">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="aeb66-120">Muestra cómo realizar una serie de tareas mediante las clases administradas de GDI+.</span><span class="sxs-lookup"><span data-stu-id="aeb66-120">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="aeb66-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="aeb66-121">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="aeb66-122">Proporciona acceso a la funcionalidad de gráficos básica de GDI+.</span><span class="sxs-lookup"><span data-stu-id="aeb66-122">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="aeb66-123">Proporciona funcionalidad avanzada de gráficos vectoriales y bidimensionales.</span><span class="sxs-lookup"><span data-stu-id="aeb66-123">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="aeb66-124">Proporciona funcionalidad avanzada de imágenes de GDI+.</span><span class="sxs-lookup"><span data-stu-id="aeb66-124">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="aeb66-125">Proporciona funcionalidad avanzada de tipografía de GDI+.</span><span class="sxs-lookup"><span data-stu-id="aeb66-125">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="aeb66-126">Las clases de este espacio de nombres se pueden usar para crear y utilizar colecciones de fuentes.</span><span class="sxs-lookup"><span data-stu-id="aeb66-126">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="aeb66-127">Proporciona la funcionalidad de impresión.</span><span class="sxs-lookup"><span data-stu-id="aeb66-127">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aeb66-128">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="aeb66-128">Related Sections</span></span>  
 [<span data-ttu-id="aeb66-129">Dibujo y representación personalizados de controles</span><span class="sxs-lookup"><span data-stu-id="aeb66-129">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="aeb66-130">Detalla cómo proporcionar código para dibujar controles.</span><span class="sxs-lookup"><span data-stu-id="aeb66-130">Details how to provide code for painting controls.</span></span>
