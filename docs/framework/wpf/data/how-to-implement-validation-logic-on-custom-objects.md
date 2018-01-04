---
title: "Cómo: Implementar lógica de validación en objetos personalizados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5044339e1d06bddad05151b2db99d5f96d068e77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>Cómo: Implementar lógica de validación en objetos personalizados
Este ejemplo muestra cómo implementar la lógica de validación en un objeto personalizado y, a continuación, enlazar a él.  
  
## <a name="example"></a>Ejemplo  
 Puede proporcionar lógica de validación en la capa de empresa si el objeto de origen implementa <xref:System.ComponentModel.IDataErrorInfo>, como en el ejemplo siguiente:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 En el ejemplo siguiente, la propiedad text del cuadro de texto se enlaza a la `Age` propiedad de la `Person` objeto, que se ha puesto a disposición para el enlace a través de una declaración de recursos que se proporciona el `x:Key``data`. El <xref:System.Windows.Controls.DataErrorValidationRule> comprueba los errores de validación provocados por la <xref:System.ComponentModel.IDataErrorInfo> implementación.  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 O bien, en lugar de utilizar el <xref:System.Windows.Controls.DataErrorValidationRule>, puede establecer la <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> propiedad `true`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [Implementar la validación de enlaces](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
