---
title: "C&#243;mo: Crear un enlace sencillo | Microsoft Docs"
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
  - "enlazar datos, crear"
  - "enlace de datos, crear enlaces simples"
  - "enlace simple, crear"
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Crear un enlace sencillo
En este ejemplo se muestra cómo crear un <xref:System.Windows.Data.Binding> sencillo.  
  
## Ejemplo  
 En este ejemplo, tenemos un objeto `Person` con una propiedad de cadena denominada `PersonName`.  El objeto `Person` se define en el espacio de nombres denominado `SDKSample`.  
  
 En el ejemplo siguiente se crea una instancia del objeto `Person` con un valor de propiedad `PersonName` de `Joe`.  Esto se hace en la sección `Resources` y se le asigna `x:Key`.  
  
 [!code-xml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 Para enlazar la propiedad `PersonName`, se hace lo siguiente:  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Como resultado, <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)