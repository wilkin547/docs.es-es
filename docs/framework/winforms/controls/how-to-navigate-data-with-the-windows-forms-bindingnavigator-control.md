---
title: Navegar por los datos con el control BindingNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingNavigator control [Windows Forms], navigating data
- data [Windows Forms], navigating
- data navigation
- examples [Windows Forms], BindingNavigator control
ms.assetid: 0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb
ms.openlocfilehash: 10508cb447e70cc387f9d98effa3bc4b5ccbbaa9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735999"
---
# <a name="how-to-navigate-data-with-the-windows-forms-bindingnavigator-control"></a>Cómo: Explorar datos con el control BindingNavigator de Windows Forms
La incorporación del control <xref:System.Windows.Forms.BindingNavigator> de Windows Forms permite a los desarrolladores proporcionar a los usuarios finales una sencilla interfaz de usuario de navegación y manipulación de datos en los formularios que creen.  
  
 El control <xref:System.Windows.Forms.BindingNavigator> es un control <xref:System.Windows.Forms.ToolStrip> con botones preconfigurados para navegar al registro primero, último, anterior y siguiente en un conjunto de datos, así como botones para agregar y eliminar registros. Agregar botones al control <xref:System.Windows.Forms.BindingNavigator> es fácil porque es un control <xref:System.Windows.Forms.ToolStrip>. Para obtener ejemplos, vea [Cómo: agregar los botones cargar, guardar y cancelar al control BindingNavigator de Windows Forms](load-save-and-cancel-bindingnavigator.md).  
  
 Por cada botón del control <xref:System.Windows.Forms.BindingNavigator> hay un miembro correspondiente del componente <xref:System.Windows.Forms.BindingSource> que permite la misma funcionalidad mediante programación. Por ejemplo, el botón <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> corresponde al método <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> del componente <xref:System.Windows.Forms.BindingSource>, el botón <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> corresponde al método <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A>, y así sucesivamente. Como resultado, habilitar el control <xref:System.Windows.Forms.BindingNavigator> para navegar por los registros de datos es tan sencillo como establecer la propiedad <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> en el componente <xref:System.Windows.Forms.BindingSource> correspondiente en el formulario.  
  
### <a name="to-set-up-the-bindingnavigator-control"></a>Para configurar el control BindingNavigator  
  
1. Agregue un componente <xref:System.Windows.Forms.BindingSource> llamado `bindingSource1` y dos controles <xref:System.Windows.Forms.TextBox> llamados `textBox1` y `textBox2`.  
  
2. Enlace `bindingSource1` a los datos y los controles de cuadro de texto a `bindingSource1`. Para ello, pegue el siguiente código en el formulario y llame a `LoadData` desde el constructor del formulario o al método de control de eventos <xref:System.Windows.Forms.Form.Load>.  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#2)]  
  
3. Agregue un control <xref:System.Windows.Forms.BindingNavigator> llamado `bindingNavigator1` al formulario.  
  
4. Establezca la propiedad <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> de `bindingNavigator1` en `bindingSource1`. Puede hacerlo con el diseñador o en el código.  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente es el ejemplo completo de los pasos enumerados anteriormente.  
  
 [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Data, System.Drawing, System.Windows.Forms y System.Xml.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.BindingNavigator>
- [BindingNavigator (control)](bindingnavigator-control-windows-forms.md)
- [Control ToolStrip](toolstrip-control-windows-forms.md)
