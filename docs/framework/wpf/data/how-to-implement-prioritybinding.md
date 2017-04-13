---
title: "C&#243;mo: Implementar PriorityBinding | Microsoft Docs"
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
  - "clases, PriorityBinding"
  - "enlace de datos, PriorityBinding (clase)"
  - "PriorityBinding (clase)"
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Implementar PriorityBinding
<xref:System.Windows.Data.PriorityBinding> en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funciona especificando una lista de enlaces.  La lista de enlaces se ordena por orden de prioridad descendente.  Si el enlace de máxima prioridad devuelve correctamente un valor cuando se procesa, entonces nunca es necesario procesar los demás enlaces de la lista.  Puede suceder que el enlace de máxima prioridad tarde mucho tiempo en evaluarse; si esto ocurre, se utilizará el enlace con el siguiente nivel de prioridad que devuelva correctamente un valor hasta que un enlace con una prioridad superior devuelva correctamente un valor.  
  
## Ejemplo  
 Para mostrar cómo funciona <xref:System.Windows.Data.PriorityBinding>, se ha creado el objeto `AsyncDataSource` con las tres propiedades siguientes: `FastDP`, `SlowerDP` y `SlowestDP`.  
  
 El descriptor de acceso get de `FastDP` devuelve el valor del miembro de datos `_fastDP`.  
  
 El descriptor de acceso get de `SlowerDP` espera durante 3 segundos antes de devolver el valor del miembro de datos `_slowerDP`.  
  
 El descriptor de acceso get de `SlowestDP` espera durante 5 segundos antes de devolver el valor del miembro de datos `_slowestDP`.  
  
> [!NOTE]
>  El único fin de este ejemplo es usarlo para realizar una demostración.  Las instrucciones de [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] no recomiendan la definición de propiedades con órdenes de magnitud más lentos que los de un conjunto de campos.  Para obtener más información, consulte [NIB: Choosing Between Properties and Methods](http://msdn.microsoft.com/es-es/55825e8f-7e2e-448a-9505-7217cc91b1af).  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 La propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> se enlaza al `AsyncDS` anterior utilizando <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Cuando el motor de enlace procesa los objetos <xref:System.Windows.Data.Binding>, comienza por el primer objeto <xref:System.Windows.Data.Binding>, que está enlazado a la propiedad `SlowestDP`.  Cuando se procesa este objeto <xref:System.Windows.Data.Binding>, no devuelve correctamente un valor porque está inactivo durante 5 segundos, por lo que se procesa el elemento <xref:System.Windows.Data.Binding> siguiente.  El <xref:System.Windows.Data.Binding> siguiente no devuelve correctamente un valor porque está inactivo durante 3 segundos.  Entonces, el motor de enlace pasa al elemento <xref:System.Windows.Data.Binding> siguiente, que está enlazado a la propiedad `FastDP`.  Este objeto <xref:System.Windows.Data.Binding> devuelve el valor "Fast Value".  Ahora, <xref:System.Windows.Controls.TextBlock> muestra el valor "Fast Value".  
  
 Una vez transcurridos 3 segundos, la propiedad `SlowerDP` devuelve el valor "Slower Value".  Entonces, <xref:System.Windows.Controls.TextBlock> muestra el valor "Slower Value".  
  
 Una vez transcurridos 5 segundos, la propiedad `SlowestDP` devuelve el valor "Slowest Value".  Este enlace es el de máxima prioridad, porque figura en primer lugar en la lista.  Ahora, <xref:System.Windows.Controls.TextBlock> muestra el valor "Slowest Value".  
  
 Consulte <xref:System.Windows.Data.PriorityBinding> para obtener información sobre qué se considera un valor devuelto correctamente de un enlace.  
  
## Vea también  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=fullName>   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)