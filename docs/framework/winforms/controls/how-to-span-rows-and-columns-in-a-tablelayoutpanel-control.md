---
title: Procedimiento para abarcar filas y columnas en un control TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039700"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="98e28-102">Procedimiento para abarcar filas y columnas en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="98e28-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="98e28-103">Los controles de <xref:System.Windows.Forms.TableLayoutPanel> un control pueden abarcar filas y columnas adyacentes.</span><span class="sxs-lookup"><span data-stu-id="98e28-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>

## <a name="to-span-columns-and-rows"></a><span data-ttu-id="98e28-104">Para abarcar columnas y filas</span><span class="sxs-lookup"><span data-stu-id="98e28-104">To span columns and rows</span></span>

1. <span data-ttu-id="98e28-105">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="98e28-105">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="98e28-106">Arrastre un <xref:System.Windows.Forms.Button> control del **cuadro de herramientas** a la celda superior <xref:System.Windows.Forms.TableLayoutPanel> izquierda del control.</span><span class="sxs-lookup"><span data-stu-id="98e28-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="98e28-107">Establezca la <xref:System.Windows.Forms.Button> propiedad **ColumnSpan** del control en **2**.</span><span class="sxs-lookup"><span data-stu-id="98e28-107">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="98e28-108">Tenga en cuenta <xref:System.Windows.Forms.Button> que el control abarca la primera y la segunda columna.</span><span class="sxs-lookup"><span data-stu-id="98e28-108">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>

4. <span data-ttu-id="98e28-109">Establezca la <xref:System.Windows.Forms.Button> propiedad **RowSpan** del control en **2**.</span><span class="sxs-lookup"><span data-stu-id="98e28-109">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="98e28-110">Tenga en cuenta <xref:System.Windows.Forms.Button> que el control abarca la primera y la segunda fila.</span><span class="sxs-lookup"><span data-stu-id="98e28-110">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>

5. <span data-ttu-id="98e28-111">Establezca la <xref:System.Windows.Forms.Button> propiedad **ColumnSpan** del control en **1**.</span><span class="sxs-lookup"><span data-stu-id="98e28-111">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="98e28-112">Tenga en cuenta <xref:System.Windows.Forms.Button> que el control se mueve a la primera columna y abarca la primera y la segunda fila.</span><span class="sxs-lookup"><span data-stu-id="98e28-112">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>

## <a name="see-also"></a><span data-ttu-id="98e28-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="98e28-113">See also</span></span>

- [<span data-ttu-id="98e28-114">Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="98e28-114">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
