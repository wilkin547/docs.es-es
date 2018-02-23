---
title: "Cómo: Controlar cuándo el texto de TextBox actualiza el origen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00fc64938e6a063ffbda77961f967e08c169ebd7
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2018
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a><span data-ttu-id="b8c35-102">Cómo: Controlar cuándo el texto de TextBox actualiza el origen</span><span class="sxs-lookup"><span data-stu-id="b8c35-102">How to: Control When the TextBox Text Updates the Source</span></span>
<span data-ttu-id="b8c35-103">Este tema describe cómo utilizar el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad para controlar el tiempo de las actualizaciones del origen de enlace.</span><span class="sxs-lookup"><span data-stu-id="b8c35-103">This topic describes how to use the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property to control the timing of binding source updates.</span></span> <span data-ttu-id="b8c35-104">El tema utiliza el <xref:System.Windows.Controls.TextBox> control como un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b8c35-104">The topic uses the <xref:System.Windows.Controls.TextBox> control as an example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8c35-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8c35-105">Example</span></span>  
 <span data-ttu-id="b8c35-106">El <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> propiedad tiene un valor predeterminado <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valo <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="b8c35-106">The <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property has a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span> <span data-ttu-id="b8c35-107">Esto significa que si una aplicación tiene un <xref:System.Windows.Controls.TextBox> con un enlace de datos <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> propiedad, el texto que escriba en el <xref:System.Windows.Controls.TextBox> no actualiza el origen hasta el <xref:System.Windows.Controls.TextBox> pierde el foco (por ejemplo, al hacer clic fuera del <xref:System.Windows.Controls.TextBox>).</span><span class="sxs-lookup"><span data-stu-id="b8c35-107">This means if an application has a <xref:System.Windows.Controls.TextBox> with a data-bound <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property, the text you type into the <xref:System.Windows.Controls.TextBox> does not update the source until the <xref:System.Windows.Controls.TextBox> loses focus (for instance, when you click away from the <xref:System.Windows.Controls.TextBox>).</span></span>  
  
 <span data-ttu-id="b8c35-108">Si desea que el origen de actualizarse a medida que se escribe, establezca el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> del enlace a <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="b8c35-108">If you want the source to be updated as you type, set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> of the binding to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="b8c35-109">En el ejemplo siguiente, las líneas de código resaltadas muestran que la `Text` propiedades de la <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.TextBlock> están enlazados a la misma propiedad de origen.</span><span class="sxs-lookup"><span data-stu-id="b8c35-109">In the following example, the highlighted lines of code show that the `Text` properties of both the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.TextBlock> are bound to the same source property.</span></span> <span data-ttu-id="b8c35-110">El <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad de la <xref:System.Windows.Controls.TextBox> enlace se establece en <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="b8c35-110">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property of the <xref:System.Windows.Controls.TextBox> binding is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 <span data-ttu-id="b8c35-111">Como resultado, el <xref:System.Windows.Controls.TextBlock> muestra el mismo texto (dado que el origen cambia) cuando el usuario escribe texto en el <xref:System.Windows.Controls.TextBox>, tal y como se muestra en la siguiente captura de pantalla del ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b8c35-111">As a result, the <xref:System.Windows.Controls.TextBlock> shows the same text (because the source changes) as the user enters text into the <xref:System.Windows.Controls.TextBox>, as illustrated by the following screenshot of the sample:</span></span>  
  
 <span data-ttu-id="b8c35-112">![Captura de pantalla de ejemplo del enlace de datos simple](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span><span class="sxs-lookup"><span data-stu-id="b8c35-112">![Simple data binding sample screen shot](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span></span>  
  
 <span data-ttu-id="b8c35-113">Si tiene un cuadro de diálogo o un formulario puede modificar el usuario y desee diferir las actualizaciones del origen hasta que el usuario ha terminado de editar los campos y hace clic en "Aceptar", puede establecer la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor de sus enlaces a <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8c35-113">If you have a dialog or a user-editable form and you want to defer source updates until the user is finished editing the fields and clicks "OK", you can set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of your bindings to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, as in the following example:</span></span>  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="b8c35-114">Al establecer el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, solo se cambia el valor de origen cuando la aplicación llama el <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b8c35-114">When you set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, the source value only changes when the application calls the <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> method.</span></span> <span data-ttu-id="b8c35-115">En el ejemplo siguiente se muestra cómo llamar a <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> para `itemNameTextBox`:</span><span class="sxs-lookup"><span data-stu-id="b8c35-115">The following example shows how to call <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> for `itemNameTextBox`:</span></span>  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="b8c35-116">Puede usar la misma técnica para las propiedades de otros controles, pero tenga en cuenta que la mayoría de las demás propiedades tiene un valor predeterminado <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valo <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="b8c35-116">You can use the same technique for properties of other controls, but keep in mind that most other properties have a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="b8c35-117">Para obtener más información, consulte la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="b8c35-117">For more information, see the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8c35-118">El <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad trabaja con las actualizaciones del origen y, por tanto, solo es pertinente para <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces.</span><span class="sxs-lookup"><span data-stu-id="b8c35-118">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property deals with source updates and therefore is only relevant for <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings.</span></span> <span data-ttu-id="b8c35-119">Para <xref:System.Windows.Data.BindingMode.TwoWay> y <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces funcione, las necesidades de objeto de origen para proporcionar notificaciones de cambio de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b8c35-119">For <xref:System.Windows.Data.BindingMode.TwoWay> and <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings to work, the source object needs to provide property change notifications.</span></span> <span data-ttu-id="b8c35-120">Puede consultar los ejemplos citados en este tema para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b8c35-120">You can refer to the samples cited in this topic for more information.</span></span> <span data-ttu-id="b8c35-121">Además, puede consultar [Implementar la notificación de cambio de propiedad](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="b8c35-121">In addition, you can look at [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8c35-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8c35-122">See Also</span></span>  
 [<span data-ttu-id="b8c35-123">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="b8c35-123">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
