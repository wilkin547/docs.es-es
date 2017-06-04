---
title: "C&#243;mo: Implementar la validaci&#243;n de enlaces | Microsoft Docs"
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
  - "enlace, validación de"
  - "enlace de datos, validación de enlace"
  - "validación de enlace"
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Implementar la validaci&#243;n de enlaces
En este ejemplo se muestra cómo utilizar una propiedad <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> y un desencadenador de estilo para informar visualmente al usuario cuando escribe un valor no válido, de acuerdo con una regla de validación personalizada.  
  
## Ejemplo  
 El contenido de texto del control <xref:System.Windows.Controls.TextBox> en el ejemplo siguiente se enlaza a la propiedad `Age` \(de tipo int\) de un objeto de [origen de enlace](GTMT) denominado `ods`.  El enlace está configurado para utilizar una regla de validación denominada `AgeRangeRule`, de tal forma que si el usuario especifica caracteres no numéricos o un valor menor que 21 o mayor que 130, aparezca un signo de admiración rojo al lado del cuadro de texto y se muestre una información sobre herramientas con el mensaje de error cuando el usuario mueva el mouse sobre el cuadro de texto.  
  
 [!code-xml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 En el ejemplo siguiente se muestra la implementación de `AgeRangeRule`, que hereda de <xref:System.Windows.Controls.ValidationRule> e invalida el método <xref:System.Windows.Controls.ValidationRule.Validate%2A>.  Se llama al método Int32.Parse\(\) para el valor, a fin de asegurarse de que no contiene ningún carácter no válido.  El método <xref:System.Windows.Controls.ValidationRule.Validate%2A> devuelve <xref:System.Windows.Controls.ValidationResult>, que indica si el valor es válido; esto se determina en función de si se detecta una excepción durante el análisis y de si el valor de edad se encuentra fuera de los límites mínimo y máximo.  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 En el ejemplo siguiente se muestra el objeto <xref:System.Windows.Controls.ControlTemplate>`validationTemplate` personalizado que crea un signo de admiración rojo para notificar al usuario la existencia de un error de validación.  Se utilizan plantillas de control para volver a definir el aspecto de un control.  
  
 [!code-xml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 Como se muestra en el ejemplo siguiente, el objeto <xref:System.Windows.Controls.ToolTip> que muestra el mensaje de error se crea utilizando el estilo denominado `textBoxInError`.  Si el valor de <xref:System.Windows.Controls.Validation.HasError%2A> es `true`, el desencadenador establece la información sobre herramientas del control <xref:System.Windows.Controls.TextBox> actual en su primer error de validación.  La propiedad <xref:System.Windows.Data.Binding.RelativeSource%2A> se establece en <xref:System.Windows.Data.RelativeSourceMode>, en referencia al elemento actual.  
  
 [!code-xml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 Para obtener el ejemplo completo, vea [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
 Tenga en cuenta que si no proporciona una propiedad <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> personalizada, aparece la plantilla de error predeterminada para proporcionar información visual al usuario cuando se produce un error de validación.  Vea "Validación de datos" en [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md) para obtener más información.  Asimismo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una regla de validación integrada que detecta las excepciones iniciadas durante la actualización de la propiedad de origen de enlace.  Para obtener más información, vea <xref:System.Windows.Controls.ExceptionValidationRule>.  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)