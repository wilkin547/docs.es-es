---
title: Gráficos y dibujos en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 08f87436ade62bb54295b012a1c24dc177ea9667
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938182"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="43cd2-102">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="43cd2-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="43cd2-103">Common Language Runtime usa una implementación avanzada de la interfaz de dispositivo gráfico de Windows ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) llamada [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43cd2-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) called [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="43cd2-104">Con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede crear gráficos, dibujar texto y manipular imágenes gráficas como objetos.</span><span class="sxs-lookup"><span data-stu-id="43cd2-104">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can create graphics, draw text, and manipulate graphical images as objects.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="43cd2-105">está diseñada para proporcionar rendimiento y facilidad de uso.</span><span class="sxs-lookup"><span data-stu-id="43cd2-105">is designed to offer performance and ease of use.</span></span> <span data-ttu-id="43cd2-106">Puede usar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para representar imágenes gráficas en Windows Forms y en controles.</span><span class="sxs-lookup"><span data-stu-id="43cd2-106">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="43cd2-107">Aunque no puede usar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] directamente en formularios Web Forms, puede mostrar imágenes gráficas mediante el control Image de servidor web.</span><span class="sxs-lookup"><span data-stu-id="43cd2-107">Although you cannot use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="43cd2-108">En esta sección, encontrará temas que presentan los conceptos básicos de la programación de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43cd2-108">In this section, you will find topics that introduce the fundamentals of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] programming.</span></span> <span data-ttu-id="43cd2-109">Aunque no pretende ser una referencia exhaustiva, esta sección incluye información sobre los objetos <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> y <xref:System.Drawing.Color>, y explica cómo realizar tareas tales como dibujar formas, dibujar texto o mostrar imágenes.</span><span class="sxs-lookup"><span data-stu-id="43cd2-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="43cd2-110">Para obtener más información, consulte [referencia de GDI +](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="43cd2-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="43cd2-111">Si quiere incorporarse y empezar a trabajar inmediatamente, vea [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="43cd2-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="43cd2-112">Encontrará temas sobre cómo usar código para dibujar líneas, formas, texto y mucho más en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="43cd2-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43cd2-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="43cd2-113">In This Section</span></span>  
 <span data-ttu-id="43cd2-114">[Graphics Overview](graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])</span><span class="sxs-lookup"><span data-stu-id="43cd2-114">[Graphics Overview](graphics-overview-windows-forms.md)</span></span>  
 <span data-ttu-id="43cd2-115">Proporciona una introducción a las clases administradas relacionadas con gráficos.</span><span class="sxs-lookup"><span data-stu-id="43cd2-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 <span data-ttu-id="43cd2-116">[About GDI+ Managed Code](about-gdi-managed-code.md) (Acerca del código administrado de GDI+)</span><span class="sxs-lookup"><span data-stu-id="43cd2-116">[About GDI+ Managed Code](about-gdi-managed-code.md)</span></span>  
 <span data-ttu-id="43cd2-117">Proporciona información acerca de las clases administradas de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43cd2-117">Provides information about the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span>  
  
 <span data-ttu-id="43cd2-118">[Using Managed Graphics Classes](using-managed-graphics-classes.md) (Usar clases gráficas administradas)</span><span class="sxs-lookup"><span data-stu-id="43cd2-118">[Using Managed Graphics Classes](using-managed-graphics-classes.md)</span></span>  
 <span data-ttu-id="43cd2-119">Muestra cómo completar diferentes tareas usando las clases administradas de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43cd2-119">Demonstrates how to complete a variety of tasks using the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="43cd2-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="43cd2-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="43cd2-121">Proporciona acceso a la funcionalidad básica de gráficos de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43cd2-121">Provides access to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="43cd2-122">Proporciona funcionalidad avanzada de gráficos vectoriales y bidimensionales.</span><span class="sxs-lookup"><span data-stu-id="43cd2-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="43cd2-123">Proporciona la funcionalidad avanzada de imágenes de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43cd2-123">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="43cd2-124">Proporciona la funcionalidad avanzada de tipografía de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43cd2-124">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] typography functionality.</span></span> <span data-ttu-id="43cd2-125">Las clases de este espacio de nombres se pueden usar para crear y utilizar colecciones de fuentes.</span><span class="sxs-lookup"><span data-stu-id="43cd2-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="43cd2-126">Proporciona la funcionalidad de impresión.</span><span class="sxs-lookup"><span data-stu-id="43cd2-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="43cd2-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="43cd2-127">Related Sections</span></span>  
 <span data-ttu-id="43cd2-128">[Custom Control Painting and Rendering](../controls/custom-control-painting-and-rendering.md) (Pintura y representación personalizadas de controles)</span><span class="sxs-lookup"><span data-stu-id="43cd2-128">[Custom Control Painting and Rendering](../controls/custom-control-painting-and-rendering.md)</span></span>  
 <span data-ttu-id="43cd2-129">Detalla cómo proporcionar código para dibujar controles.</span><span class="sxs-lookup"><span data-stu-id="43cd2-129">Details how to provide code for painting controls.</span></span>
