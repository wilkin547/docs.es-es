---
title: Procedimiento para mover un elemento ToolStrip de un control ToolStripContainer a un formulario
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: c6519add6789485d41146633abb5e11f80913649
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039824"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Procedimiento para mover un elemento ToolStrip de un control ToolStripContainer a un formulario
Utilice el siguiente procedimiento para sacar un <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripContainer> de un en un formulario.

## <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Para quitar un control ToolStrip de un control ToolStripContainer en un formulario

1. Seleccione el control <xref:System.Windows.Forms.ToolStrip>.

2. Para cortar, presione Ctrl + X o haga clic con el botón <xref:System.Windows.Forms.ToolStrip> secundario en el y elija cortar en el menú contextual. <xref:System.Windows.Forms.ToolStrip>

3. Seleccione el formulario.

4. Pegue el <xref:System.Windows.Forms.ToolStrip> presionando Ctrl + V o elija **pegar** en el menú **edición** .

5. Establezca la <xref:System.Windows.Forms.ToolStrip.Dock%2A> propiedad <xref:System.Windows.Forms.ToolStrip> de en **Top**.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
