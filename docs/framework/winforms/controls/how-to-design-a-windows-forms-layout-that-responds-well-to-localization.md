---
title: 'Cómo: Crear un diseño de formularios Windows Forms que sea apropiado para la localización'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: c72cae58e8486f1187fd27d200522a43dca328ca
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43390749"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>Cómo: Crear un diseño de formularios Windows Forms que sea apropiado para la localización
La creación de formularios ya listos para ser localizados acelera en gran medida el desarrollo para los mercados internacionales. Puede utilizar el control <xref:System.Windows.Forms.TableLayoutPanel> para implementar diseños que respondan correctamente cuando los controles cambien de tamaño debido a los cambios en los valores de la propiedad <xref:System.Windows.Forms.Control.Text%2A>.  
  
## <a name="example"></a>Ejemplo  
 Este formulario muestra cómo crear un diseño que se ajusta proporcionalmente cuando traduce los valores de cadena mostrados a otros idiomas. Este proceso de traducción se denomina *localización*. Para más información, consulte [Localización](../../../../docs/standard/globalization-localization/localization.md).  
  
 Visual Studio es altamente compatible con esta tarea.  Vea también Tutorial: [Crear un diseño que ajuste las proporciones para la localización](https://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [Cómo: Alinear y expandir un control en un control TableLayoutPanel](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](https://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))  
  
3.  [Cómo: Abarcar filas y columnas en un control TableLayoutPanel](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4.  [Cómo: Editar columnas y filas en un control TableLayoutPanel](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5.  [Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de Windows Forms](https://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))  
  
6.  [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
7.  [Tutorial: Diseñar controles de Windows Forms con relleno, márgenes y la propiedad AutoSize](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))  
  
8.  [Cómo: Admitir la localización en Windows Forms mediante AutoSize y el control TableLayoutPanel](https://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))  
  
9. [Tutorial: Crear Windows Forms de entrada de datos de tamaño variable](https://msdn.microsoft.com/library/991eahec\(v=vs.110\))  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [Localización](../../../../docs/standard/globalization-localization/localization.md)
