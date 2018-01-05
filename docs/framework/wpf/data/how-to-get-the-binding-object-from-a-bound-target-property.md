---
title: "Cómo: Obtener el objeto de enlace a partir de una propiedad de destino enlazada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f5369bc770a31aa99f1fb11bfec790eb8fe091d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Cómo: Obtener el objeto de enlace a partir de una propiedad de destino enlazada
En este ejemplo se muestra cómo obtener el objeto de enlace desde una propiedad de destino enlazada a datos.  
  
## <a name="example"></a>Ejemplo  
 Puede hacer lo siguiente para obtener la <xref:System.Windows.Data.Binding> objeto:  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  Debe especificar la propiedad de dependencia para el enlace que desee porque es posible que más de una propiedad del objeto de destino esté usando el enlace de datos.  
  
 Como alternativa, puede obtener el <xref:System.Windows.Data.BindingExpression> y, a continuación, obtener el valor de la <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> propiedad.  
  
 Para obtener el ejemplo completo, vea [Enlace de ejemplo de validación](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
>  Si el enlace es un <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>. Si es un <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>. Si no está seguro de si la propiedad de destino se enlaza mediante una <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding>, o un <xref:System.Windows.Data.PriorityBinding>, puede usar <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Crear un enlace mediante código](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
