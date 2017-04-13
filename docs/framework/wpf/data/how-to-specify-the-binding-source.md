---
title: "C&#243;mo: Especificar el origen de enlace | Microsoft Docs"
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
  - "enlazar datos, orígenes de enlace"
  - "orígenes de enlace"
  - "enlace de datos, origen de enlace"
ms.assetid: 55d47757-2648-4a52-987f-b767953f168c
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Especificar el origen de enlace
En el enlace de datos, el objeto de [origen de enlace](GTMT) hace referencia al objeto del que se obtienen los datos.  En este tema se describen las distintas maneras de especificar el [origen de enlace](GTMT).  
  
## Ejemplo  
 Para enlazar varias propiedades a un mismo origen, utilice la propiedad `DataContext`, que proporciona una manera cómoda de establecer un ámbito dentro del cual todas las propiedades enlazadas a datos heredan un origen común.  
  
 En el ejemplo siguiente, el contexto de datos se establece en el elemento raíz de la aplicación.  Esto permite que todos los elementos secundarios hereden ese contexto de datos.  Los datos para el enlace proceden de una clase de datos personalizada, `NetIncome`, a la que se hace referencia directamente mediante una asignación que recibe la clave de recurso de `incomeDataSource`.  
  
 [!code-xml[DirectionalBinding#DataContext1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext1)]  
[!code-xml[DirectionalBinding#DataContext2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext2)]  
  
 En el ejemplo siguiente, se muestra la definición de la clase `NetIncome`.  
  
 [!code-csharp[DirectionalBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/billsdata.cs#dataobject)]
 [!code-vb[DirectionalBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DirectionalBinding/VisualBasic/NetIncome.vb#dataobject)]  
  
> [!NOTE]
>  En el ejemplo anterior se crea una instancia del objeto en marcado y se utiliza como recurso.  Si desea enlazar a un objeto del que ya se ha creado una instancia en el código, deberá establecer la propiedad `DataContext` mediante programación.  Para obtener un ejemplo, vea [Hacer que los datos estén disponibles para el enlace en XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md).  
  
 Como alternativa, si desea especificar explícitamente el origen en los enlaces individuales, dispone de las opciones siguientes.  Éstas tienen prioridad sobre el contexto de datos heredado.  
  
|Propiedad.|Descripción|  
|----------------|-----------------|  
|<xref:System.Windows.Data.Binding.Source%2A>|Esta propiedad se utiliza para establecer el origen en una instancia de un objeto.  Si no necesita la funcionalidad de establecer un ámbito en el que varias propiedades hereden el mismo contexto de datos, puede utilizar la propiedad <xref:System.Windows.Data.Binding.Source%2A> en lugar de la propiedad `DataContext`.  Para obtener más información, consulte <xref:System.Windows.Data.Binding.Source%2A>.|  
|<xref:System.Windows.Data.Binding.RelativeSource%2A>|Resulta útil si desea especificar el origen con relación a la ubicación donde se encuentra el [destino de enlace](GTMT).  Algunos escenarios comunes donde puede utilizar esta propiedad son aquéllos en los que desea enlazar una propiedad del elemento a otra propiedad del mismo elemento o en los que se define un enlace en un estilo o una plantilla.  Para obtener más información, consulte <xref:System.Windows.Data.Binding.RelativeSource%2A>.|  
|<xref:System.Windows.Data.Binding.ElementName%2A>|Especifica una cadena que representa el elemento que se desea enlazar.  Resulta útil si desear enlazar la propiedad de otro elemento de la aplicación.  Por ejemplo, si desea utilizar un control <xref:System.Windows.Controls.Slider> para controlar el alto de otro control de la aplicación, o si desea enlazar la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> del control a la propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> del control <xref:System.Windows.Controls.ListBox>.  Para obtener más información, consulte <xref:System.Windows.Data.Binding.ElementName%2A>.|  
  
## Vea también  
 <xref:System.Windows.FrameworkElement.DataContext%2A?displayProperty=fullName>   
 <xref:System.Windows.FrameworkContentElement.DataContext%2A?displayProperty=fullName>   
 [Herencia de valores de propiedad](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre declaraciones de enlaces](../../../../docs/framework/wpf/data/binding-declarations-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)