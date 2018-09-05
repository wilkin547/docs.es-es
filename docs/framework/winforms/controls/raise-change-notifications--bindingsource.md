---
title: 'Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: 039875473fe3bd1702ad43465edae2c73ffcadca
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43672198"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged
El componente <xref:System.Windows.Forms.BindingSource> detectará automáticamente los cambios en un origen de datos cuando el tipo de contenido en el origen de datos implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> y genera eventos <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> cuando se cambia un valor de propiedad. Esto resulta útil porque los controles enlazados a <xref:System.Windows.Forms.BindingSource> se actualizarán automáticamente cuando cambien los valores del origen de datos.  
  
> [!NOTE]
>  Si su origen de datos implementa <xref:System.ComponentModel.INotifyPropertyChanged> y realiza operaciones asincrónicas, no debe realizar cambios en el origen de datos en un subproceso en segundo plano. En su lugar, debe leer los datos en un subproceso en segundo plano y fusionar mediante combinación los datos en una lista en el subproceso de la interfaz de usuario.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra una implementación simple de la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>. También se muestra cómo <xref:System.Windows.Forms.BindingSource> pasa automáticamente un cambio del origen de datos a un control enlazado cuando <xref:System.Windows.Forms.BindingSource> está enlazada a una lista del tipo <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Si usa el atributo `CallerMemberName`, las llamadas al método `NotifyPropertyChanged` no tienen que especificar el nombre de la propiedad como un argumento de cadena. Para obtener más información, consulte [información del llamador](https://msdn.microsoft.com/library/9cb2b8c0-c4f6-44b8-9c90-38948455b373).  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Consulte también [HYPERLINK "http://msdn.microsoft.com/library/Bb129228(v=vs.110)" Cómo: compilar y ejecutar un Windows Forms código completo en el ejemplo se utiliza Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ComponentModel.INotifyPropertyChanged>  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Cómo: Provocar notificaciones de cambios mediante el método ResetItem de BindingSource](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
