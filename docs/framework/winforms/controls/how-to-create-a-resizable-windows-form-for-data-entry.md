---
title: Filtrar para crear un formulario Windows Forms de entrada de datos de tamaño variable
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
ms.openlocfilehash: ebccad248927d8a201bd5758e5ddf2d5414455f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189688"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>Filtrar para crear un formulario Windows Forms de entrada de datos de tamaño variable
Un buen diseño responde bien a los cambios en las dimensiones de su formulario principal. Puede usar el control <xref:System.Windows.Forms.TableLayoutPanel> para organizar el diseño del formulario de manera que el tamaño y la posición de los controles cambien de una manera coherente cuando cambien las dimensiones del formulario. El control <xref:System.Windows.Forms.TableLayoutPanel> también es útil cuando los cambios en el contenido de los controles producen cambios en el diseño. El proceso descrito en este procedimiento puede realizarse en el entorno de Visual Studio.  Consulte también [Tutorial: Creación de un formulario de Windows puede cambiar el tamaño de entrada de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar un control <xref:System.Windows.Forms.TableLayoutPanel> para crear un diseño que responda bien cuando el usuario cambie el tamaño del formulario. También se muestra un diseño que responde bien a la localización.  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Filtrar para delimitar y acoplar controles secundarios en un control TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Filtrar para crear un diseño de formularios Windows Forms que sea apropiado para la localización](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
