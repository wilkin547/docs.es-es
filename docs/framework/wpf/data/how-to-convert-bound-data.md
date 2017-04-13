---
title: "C&#243;mo: Convertir datos enlazados | Microsoft Docs"
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
  - "enlazar datos, convertir datos enlazados"
  - "convertir, datos enlazados"
  - "enlace de datos, convertir datos enlazados"
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Convertir datos enlazados
En este ejemplo se muestra cómo aplicar la conversión a datos que se utilizan en enlaces.  
  
 Para convertir datos durante el enlace, debe crear una clase que implemente la interfaz <xref:System.Windows.Data.IValueConverter>, que incluye los métodos <xref:System.Windows.Data.IValueConverter.Convert%2A> y <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra la implementación de un convertidor de fecha que convierte el valor de fecha pasado de manera que sólo muestre el año, el mes y el día.  Al implementar la interfaz <xref:System.Windows.Data.IValueConverter>, es recomendable decorar la implementación con un atributo <xref:System.Windows.Data.ValueConversionAttribute> para indicar a las herramientas de programación los tipos de datos que participan en la conversión, como en el ejemplo siguiente:  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Una vez creado un convertidor, puede agregarlo como recurso en el archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  En el ejemplo siguiente, *src* se asigna al espacio de nombres en el que se define *DateConverter*.  
  
 [!code-xml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Por último, puede utilizar el convertidor en el enlace mediante la sintaxis siguiente.  En el ejemplo siguiente, el contenido de texto de <xref:System.Windows.Controls.TextBlock> se enlaza a *StartDate*, que es una propiedad de un origen de datos externo.  
  
 [!code-xml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Los recursos de estilo a los que se hace referencia en el ejemplo anterior se definen en una sección de recurso que no se muestra en este tema.  
  
## Vea también  
 [Implementar la validación de enlaces](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)