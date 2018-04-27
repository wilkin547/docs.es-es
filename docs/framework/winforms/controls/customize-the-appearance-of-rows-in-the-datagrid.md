---
title: 'Cómo: Personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 579d63da8a411e47c649695c0a09d4cf519b4410
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a>Cómo: Personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms
Puede controlar la apariencia de las filas de <xref:System.Windows.Forms.DataGridView> controlando el evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>, o ambos. Estos eventos están diseñados para que pueda representar solo lo que se desea mientras permite que el control <xref:System.Windows.Forms.DataGridView> represente el resto. Por ejemplo, si quiere representar un fondo personalizado, puede controlar el evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> y dejar que las celdas individuales representen su propio contenido de primer plano. También tiene la opción de dejar que las celdas se representen a sí mismas y agregar contenido de primer plano personalizado en un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>. Además, puede deshabilitar la representación de las celdas y representar todo usted mismo en un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>.  
  
 En el ejemplo de código siguiente, se implementan controladores de ambos eventos para ofrecer un fondo de selección de degradado y algún contenido de primer plano personalizado que abarca varias columnas.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>  
 [Personalizar el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [Arquitectura del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)
