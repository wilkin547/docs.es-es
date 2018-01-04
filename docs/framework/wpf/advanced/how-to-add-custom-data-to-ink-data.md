---
title: "Cómo: Agregar datos personalizados a datos de entrada manuscrita"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ca44d6a2c42219f7aec76f8007010c24c610138
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-custom-data-to-ink-data"></a>Cómo: Agregar datos personalizados a datos de entrada manuscrita
Puede agregar datos personalizados a tinta que se guardará cuando la tinta se guarda como formato serializado de tinta (ISF).  Puede guardar los datos personalizados a la <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, o <xref:System.Windows.Ink.Stroke>.  Posibilidad de guardar los datos personalizados en tres objetos permite decidir el mejor lugar para guardar los datos.  Las tres clases usan métodos similares para almacenar y tener acceso a datos personalizados.  
  
 Solo los tipos siguientes se pueden guardar como datos personalizados:  
  
-   <xref:System.Boolean>  
  
-   <xref:System.Boolean>[]  
  
-   <xref:System.Byte>  
  
-   <xref:System.Byte>[]  
  
-   <xref:System.Char>  
  
-   <xref:System.Char>[]  
  
-   <xref:System.DateTime>  
  
-   <xref:System.DateTime>[]  
  
-   <xref:System.Decimal>  
  
-   <xref:System.Decimal>[]  
  
-   <xref:System.Double>  
  
-   <xref:System.Double>[]  
  
-   <xref:System.Int16>  
  
-   <xref:System.Int16>[]  
  
-   <xref:System.Int32>  
  
-   <xref:System.Int32>[]  
  
-   <xref:System.Int64>  
  
-   <xref:System.Int64>[]  
  
-   <xref:System.Single>  
  
-   <xref:System.Single>[]  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <xref:System.UInt16>[]  
  
-   <xref:System.UInt32>  
  
-   <xref:System.UInt32>[]  
  
-   <xref:System.UInt64>  
  
-   <xref:System.UInt64>[]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo agregar y recuperar los datos personalizados de un <xref:System.Windows.Ink.StrokeCollection>.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 En el ejemplo siguiente se crea una aplicación que muestra un <xref:System.Windows.Controls.InkCanvas> y dos botones.  El botón, `switchAuthor`, permite que dos lápices que va a usar dos autores diferentes.  El botón `changePenColors` cambia el color de cada trazo en el <xref:System.Windows.Controls.InkCanvas> según el autor.  La aplicación define dos <xref:System.Windows.Ink.DrawingAttributes> objetos y agrega una propiedad personalizada a cada uno de ellos que indica qué autor dibujó el <xref:System.Windows.Ink.Stroke>.  Cuando el usuario hace clic en `changePenColors`, la aplicación cambia el aspecto del trazo según el valor de la propiedad personalizada.  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
