---
title: Procedimiento para provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged
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
ms.openlocfilehash: 7dc640f272226da650a63b1a3434822d21053b48
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968290"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a><span data-ttu-id="883a7-102">Procedimiento para provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="883a7-102">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="883a7-103">El componente <xref:System.Windows.Forms.BindingSource> detectará automáticamente los cambios en un origen de datos cuando el tipo de contenido en el origen de datos implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> y genera eventos <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> cuando se cambia un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="883a7-103">The <xref:System.Windows.Forms.BindingSource> component will automatically detect changes in a data source when the type contained in the data source implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface and raises <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> events when a property value is changed.</span></span> <span data-ttu-id="883a7-104">Esto resulta útil porque los controles enlazados a <xref:System.Windows.Forms.BindingSource> se actualizarán automáticamente cuando cambien los valores del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="883a7-104">This is useful because controls bound to the <xref:System.Windows.Forms.BindingSource> will then automatically update as the data source values change.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="883a7-105">Si su origen de datos implementa <xref:System.ComponentModel.INotifyPropertyChanged> y realiza operaciones asincrónicas, no debe realizar cambios en el origen de datos en un subproceso en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="883a7-105">If your data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and you are performing asynchronous operations, you should not make changes to the data source on a background thread.</span></span> <span data-ttu-id="883a7-106">En su lugar, debe leer los datos en un subproceso en segundo plano y fusionar mediante combinación los datos en una lista en el subproceso de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="883a7-106">Instead, you should read the data on a background thread and merge the data into a list on the UI thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="883a7-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="883a7-107">Example</span></span>  
 <span data-ttu-id="883a7-108">En el ejemplo de código siguiente se muestra una implementación simple de la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="883a7-108">The following code example demonstrates a simple implementation of the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="883a7-109">También se muestra cómo <xref:System.Windows.Forms.BindingSource> pasa automáticamente un cambio del origen de datos a un control enlazado cuando <xref:System.Windows.Forms.BindingSource> está enlazada a una lista del tipo <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="883a7-109">It also shows how the <xref:System.Windows.Forms.BindingSource> automatically passes a data source change to a bound control when the <xref:System.Windows.Forms.BindingSource> is bound to a list of the <xref:System.ComponentModel.INotifyPropertyChanged> type.</span></span>  
  
 <span data-ttu-id="883a7-110">Si usa el atributo `CallerMemberName`, las llamadas al método `NotifyPropertyChanged` no tienen que especificar el nombre de la propiedad como un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="883a7-110">If you use the `CallerMemberName` attribute, calls to the `NotifyPropertyChanged` method don't have to specify the property name as a string argument.</span></span> <span data-ttu-id="883a7-111">Para obtener más información, vea [información del llamador (C#)](../../../csharp/programming-guide/concepts/caller-information.md) o información del llamador [(Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="883a7-111">For more information, see [Caller Information (C#)](../../../csharp/programming-guide/concepts/caller-information.md) or [Caller Information (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="883a7-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="883a7-112">Compiling the Code</span></span>  
 <span data-ttu-id="883a7-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="883a7-113">This example requires:</span></span>  
  
- <span data-ttu-id="883a7-114">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="883a7-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="883a7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="883a7-115">See also</span></span>

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [<span data-ttu-id="883a7-116">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="883a7-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="883a7-117">Procedimientos: Generar notificaciones de cambios mediante el método ResetItem de BindingSource</span><span class="sxs-lookup"><span data-stu-id="883a7-117">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
