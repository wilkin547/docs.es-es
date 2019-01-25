---
title: Procedimiento Proporcionar elementos de menú estándar a un formulario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: befff7b2eceb37b49c4d1263f46bf93775d432c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564021"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a>Procedimiento Proporcionar elementos de menú estándar a un formulario
Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.  
  
 Hay una amplia compatibilidad para esta característica en Visual Studio.  
  
 Consulte también [Tutorial: Proporcionar elementos de menú estándar a un formulario](walkthrough-providing-standard-menu-items-to-a-form.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente, se muestra cómo usar un control <xref:System.Windows.Forms.MenuStrip> para crear un formulario con un menú estándar. Las selecciones de elementos de menú se muestran en un control <xref:System.Windows.Forms.StatusStrip>.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
