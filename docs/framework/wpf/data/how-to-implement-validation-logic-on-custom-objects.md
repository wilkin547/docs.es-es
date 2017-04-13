---
title: "C&#243;mo: Implementar l&#243;gica de validaci&#243;n en objetos personalizados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "comprobar en busca de errores de validación [WPF]"
  - "objetos personalizados [WPF], implementar lógica de validación en"
  - "implementar lógica de validación en objetos personalizados [WPF]"
  - "errores de validación [WPF], comprobar"
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Implementar l&#243;gica de validaci&#243;n en objetos personalizados
En este ejemplo se muestra cómo implementar la lógica de validación en un objeto personalizado y, a continuación, enlazar a este objeto.  
  
## Ejemplo  
 Puede proporcionar lógica de validación en la capa de negocios si el objeto de origen implementa <xref:System.ComponentModel.IDataErrorInfo>, como en el ejemplo siguiente:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 En el ejemplo siguiente, la propiedad de texto del cuadro de texto enlaza a la propiedad `Age` del objeto `Person`, que está disponible para el enlace mediante una declaración de recurso a la que se asigna el atributo `x:Key` `data`.  <xref:System.Windows.Controls.DataErrorValidationRule> comprueba los errores de validación provocados por la implementación de <xref:System.ComponentModel.IDataErrorInfo>.  
  
 [!code-xml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 Como alternativa, en lugar de usar <xref:System.Windows.Controls.DataErrorValidationRule>, puede establecer la propiedad <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> en `true`.  
  
## Vea también  
 <xref:System.Windows.Controls.ExceptionValidationRule>   
 [Implementar la validación de enlaces](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)