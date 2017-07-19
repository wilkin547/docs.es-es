---
title: "C&#243;mo: Generar un valor basado en una lista de elementos enlazados | Microsoft Docs"
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
  - "enlace de datos, MultiBinding"
  - "MultiBinding"
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Generar un valor basado en una lista de elementos enlazados
<xref:System.Windows.Data.MultiBinding> permite enlazar una propiedad del [destino de enlace](GTMT) a una lista de propiedades de origen y, a continuación, aplicar la lógica para generar un valor con las entradas indicadas.  En este ejemplo de complemento se muestra cómo utilizar <xref:System.Windows.Data.MultiBinding>.  
  
## Ejemplo  
 En el ejemplo siguiente, `NameListData` hace referencia a una colección de objetos `PersonName`, que son objetos que contienen dos propiedades, `firstName` y `lastName`.  En el ejemplo siguiente se genera un objeto <xref:System.Windows.Controls.TextBlock> que muestra el nombre y el apellido de una persona, con el apellido en primer lugar.  
  
 [!code-xml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Para entender cómo se genera el formato que muestra primero el apellido, estudiaremos la implementación de `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` implementa la interfaz <xref:System.Windows.Data.IMultiValueConverter>.  `NameConverter` toma los valores de los enlaces individuales y los almacena en la matriz de objetos de valores.  El orden en el que los elementos <xref:System.Windows.Data.Binding> aparecen bajo el elemento <xref:System.Windows.Data.MultiBinding> es el orden en el que esos valores están almacenados en la matriz.  El argumento de parámetro del método de <xref:System.Windows.Data.MultiBinding.Converter%2A>, que aplica una modificación al parámetro para determinar cómo dar formato al nombre, hace referencia al valor del atributo <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A>.  
  
## Vea también  
 [Convertir datos enlazados](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)