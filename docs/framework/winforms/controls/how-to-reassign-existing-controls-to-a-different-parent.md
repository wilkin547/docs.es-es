---
title: 'Cómo: Reasignar controles existentes en un elemento primario diferente'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1767fcff1742f4ad630b4b996c709b7ded53a129
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459202"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Cómo: reasignar controles existentes a un elemento primario diferente

Puede asignar controles que existen en el formulario a un nuevo control contenedor.

1. En Visual Studio, arrastre tres controles <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** hasta el formulario. Colóquelos cerca entre sí, pero sin alinearlos.

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
- [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
