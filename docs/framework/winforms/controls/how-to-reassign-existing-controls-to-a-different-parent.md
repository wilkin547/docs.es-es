---
title: Procedimiento para reasignar los controles existentes en un elemento primario diferente
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 84e662e0bd2689115abe128c6442e4462eed3e18
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987037"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Procedimiento Reasignar los controles existentes a un elemento primario diferente

Puede asignar controles que existen en el formulario a un nuevo control contenedor.

1. En Visual Studio, arrastre tres <xref:System.Windows.Forms.Button> controles desde el **cuadro de herramientas** hasta el formulario. Colóquelos cerca entre sí, pero sin alinearlos.

2. En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> . (No arrastre el icono hasta el formulario).

3. Mueva el puntero del mouse cerca de los tres controles <xref:System.Windows.Forms.Button> .

   Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> agregado.

4. Haga clic y mantenga presionado el botón del mouse.

5. Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.FlowLayoutPanel> .

6. Dibuje el contorno alrededor de los tres controles <xref:System.Windows.Forms.Button> .

7. Suelte el botón del mouse.

   Observe que los tres controles <xref:System.Windows.Forms.Button> se insertan en el control <xref:System.Windows.Forms.FlowLayoutPanel> .

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Organizar controles en Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
