---
title: Procedimiento Asociar un objeto ContextMenuStrip con un Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: 4b61da8dc9f36e0a80807547e2049ef512c94747
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718343"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a>Filtrar Asociar un objeto ContextMenuStrip con un Control
Después de crear los controles y menús contextuales, utilice los procedimientos siguientes para mostrar un menú contextual determinado cuando el usuario hace clic con el botón secundario del mouse en el control. Estos procedimientos asocian un <xref:System.Windows.Forms.ContextMenuStrip> a un Windows Forms y a un control <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a>Para asociar un objeto ContextMenuStrip a Windows Forms  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> al nombre del <xref:System.Windows.Forms.ContextMenuStrip> asociado.  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a>Para asociar un objeto ContextMenuStrip a un control ToolStrip  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> del control en el nombre del <xref:System.Windows.Forms.ContextMenuStrip> asociado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente, se crea un Windows Forms y un control <xref:System.Windows.Forms.ToolStrip>, y se asocia un control <xref:System.Windows.Forms.ContextMenuStrip> diferente a cada uno de ellos.  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [Cómo: Agregar elementos de menú a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md)
- [ContextMenuStrip (Control)](contextmenustrip-control.md)
