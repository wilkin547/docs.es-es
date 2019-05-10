---
title: Procedimiento para crear un formulario Windows Forms de entrada de datos de tamaño variable
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
ms.openlocfilehash: 724dfa79358548530eab49683f1cb2db55f889c8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625978"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>Procedimiento para crear un formulario Windows Forms de entrada de datos de tamaño variable
Un buen diseño responde bien a los cambios en las dimensiones de su formulario principal. Puede usar el control <xref:System.Windows.Forms.TableLayoutPanel> para organizar el diseño del formulario de manera que el tamaño y la posición de los controles cambien de una manera coherente cuando cambien las dimensiones del formulario. El control <xref:System.Windows.Forms.TableLayoutPanel> también es útil cuando los cambios en el contenido de los controles producen cambios en el diseño. El proceso descrito en este procedimiento puede realizarse en el entorno de Visual Studio.  Consulte también [Tutorial: Creación de un formulario de Windows puede cambiar el tamaño de entrada de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar un control <xref:System.Windows.Forms.TableLayoutPanel> para crear un diseño que responda bien cuando el usuario cambie el tamaño del formulario. También se muestra un diseño que responde bien a la localización.  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Cómo: Crear un diseño de formularios de Windows que sea apropiado para la localización](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [Experiencia de usuario de Microsoft Windows, Official Guidelines for diseñadores y desarrolladores de interfaz de usuario. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
