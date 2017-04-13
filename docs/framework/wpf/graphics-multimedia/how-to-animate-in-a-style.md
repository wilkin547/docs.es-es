---
title: "C&#243;mo: Animar en un estilo | Microsoft Docs"
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
  - "animación, propiedades, dentro de estilos"
  - "estilos, animar propiedades dentro de"
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Animar en un estilo
En este ejemplo se muestra cómo animar propiedades en un estilo.  Al animar dentro de un estilo, únicamente se puede establecer como destino directo el elemento marco cuyo estilo se define.  Para establecer el destino en un objeto freezable, debe "establecer una relación" desde una propiedad del elemento al que se aplica el estilo.  
  
 En el ejemplo siguiente, se definen varias animaciones dentro de un estilo y se aplican a un control <xref:System.Windows.Controls.Button>.  Cuando el usuario mueve el mouse sobre el botón, se desvanece de opaco a parcialmente translúcido y viceversa, repetidamente.  Cuando el usuario retira el mouse y del botón, se vuelve completamente opaco.  Cuando se hace clic en el botón, su color de fondo cambia de la naranja al blanco y de nuevo al naranja.  Dado que el objeto <xref:System.Windows.Media.SolidColorBrush> puede utilizado para pintar el botón no se puede establecer directamente como destino, se tiene acceso a él estableciendo una relación desde la propiedad <xref:System.Windows.Controls.Control.Background%2A> del botón.  
  
## Ejemplo  
 [!code-xml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 Tenga en cuenta que al animar dentro de un estilo, es posible establecer como destinos objetos que no existen.  Por ejemplo, suponga que el estilo utiliza un objeto <xref:System.Windows.Media.SolidColorBrush> para establecer la propiedad del fondo de un botón, pero que en algún punto se invalida el estilo y se establece el fondo del botón en un objeto <xref:System.Windows.Media.LinearGradientBrush>.  Si intenta animar <xref:System.Windows.Media.SolidColorBrush>, no se iniciará ninguna excepción; simplemente se producirá un error en la animación, que no se comunicará.  
  
 Para obtener más información sobre la sintaxis de establecimiento de destinos en guiones gráficos, vea [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  Para obtener más información acerca de la animación, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Para obtener más información acerca de los estilos, vea [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).