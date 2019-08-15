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
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Procedimiento para abarcar filas y columnas en un control TableLayoutPanel
Los controles de <xref:System.Windows.Forms.TableLayoutPanel> un control pueden abarcar filas y columnas adyacentes.

## <a name="to-span-columns-and-rows"></a>Para abarcar columnas y filas

1. Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.

2. Arrastre un <xref:System.Windows.Forms.Button> control del **cuadro de herramientas** a la celda superior <xref:System.Windows.Forms.TableLayoutPanel> izquierda del control.

3. Establezca la <xref:System.Windows.Forms.Button> propiedad **ColumnSpan** del control en **2**. Tenga en cuenta <xref:System.Windows.Forms.Button> que el control abarca la primera y la segunda columna.

4. Establezca la <xref:System.Windows.Forms.Button> propiedad **RowSpan** del control en **2**. Tenga en cuenta <xref:System.Windows.Forms.Button> que el control abarca la primera y la segunda fila.

5. Establezca la <xref:System.Windows.Forms.Button> propiedad **ColumnSpan** del control en **1**. Tenga en cuenta <xref:System.Windows.Forms.Button> que el control se mueve a la primera columna y abarca la primera y la segunda fila.

## <a name="see-also"></a>Vea también

- [Control TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
