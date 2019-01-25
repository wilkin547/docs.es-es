---
title: Procedimiento Provocar notificaciones de cambios mediante el método BindingSource ResetItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: 50d2203638363831d236a6add7c6f4ba4fbebf4b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644829"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a>Procedimiento Provocar notificaciones de cambios mediante el método BindingSource ResetItem
Algunos orígenes de datos para sus controles no provocan notificaciones de cambios cuando se cambian, agregan o eliminan elementos. Con el componente <xref:System.Windows.Forms.BindingSource>, puede enlazar a tales orígenes de datos y provocar una notificación de cambios desde el código.  
  
## <a name="example"></a>Ejemplo  
 Este formulario muestra cómo utilizar un componente <xref:System.Windows.Forms.BindingSource> para enlazar una lista a un control <xref:System.Windows.Forms.DataGridView>. La lista no provoca notificaciones de cambios, por lo que se llama al método <xref:System.Windows.Forms.BindingSource.ResetItem%2A> en <xref:System.Windows.Forms.BindingSource> cuando se cambia un elemento en la lista. .  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [Cómo: Enlazar un Control de Windows Forms a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
