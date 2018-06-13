---
title: 'Cómo: Crear Windows Forms de entrada de datos de tamaño variable'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: a7768b3c6be10373e742cbeea0028d1aee0b261d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531796"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>Cómo: Crear Windows Forms de entrada de datos de tamaño variable
Un buen diseño responde bien a los cambios en las dimensiones de su formulario principal. Puede usar el control <xref:System.Windows.Forms.TableLayoutPanel> para organizar el diseño del formulario de manera que el tamaño y la posición de los controles cambien de una manera coherente cuando cambien las dimensiones del formulario. El control <xref:System.Windows.Forms.TableLayoutPanel> también es útil cuando los cambios en el contenido de los controles producen cambios en el diseño. El proceso descrito en este procedimiento puede realizarse en el entorno de Visual Studio.  Vea también [Tutorial: Crear Windows Forms de entrada de datos de tamaño variable](http://msdn.microsoft.com/library/991eahec\(v=vs.110\)).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar un control <xref:System.Windows.Forms.TableLayoutPanel> para crear un diseño que responda bien cuando el usuario cambie el tamaño del formulario. También se muestra un diseño que responde bien a la localización.  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Crear un diseño de formularios Windows Forms que sea apropiado para la localización](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [Microsoft Windows User Experience, Official Guidelines for User Interface Developers and diseñadores. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)
