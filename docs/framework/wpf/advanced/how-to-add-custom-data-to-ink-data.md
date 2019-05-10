---
title: Procedimiento Agregar datos personalizados a datos de entrada de lápiz
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 7c59a205df5358daec101339cc6a308c8e38a9d6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64640866"
---
# <a name="how-to-add-custom-data-to-ink-data"></a>Procedimiento Agregar datos personalizados a datos de entrada de lápiz
Puede agregar datos personalizados a la entrada de lápiz que se guardarán cuando se guarda la entrada de lápiz como formato serializado de tinta (ISF).  Puede guardar los datos personalizados a la <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, o el <xref:System.Windows.Ink.Stroke>.  Posibilidad de guardar los datos personalizados en los tres objetos le permite decidir el mejor lugar para guardar los datos.  Las tres clases usan métodos similares para almacenar y acceder a los datos personalizados.  
  
 Solo los tipos siguientes se pueden guardar como datos personalizados:  
  
- <xref:System.Boolean>  
  
- <xref:System.Boolean>[]  
  
- <xref:System.Byte>  
  
- <xref:System.Byte>[]  
  
- <xref:System.Char>  
  
- <xref:System.Char>[]  
  
- <xref:System.DateTime>  
  
- <xref:System.DateTime>[]  
  
- <xref:System.Decimal>  
  
- <xref:System.Decimal>[]  
  
- <xref:System.Double>  
  
- <xref:System.Double>[]  
  
- <xref:System.Int16>  
  
- <xref:System.Int16>[]  
  
- <xref:System.Int32>  
  
- <xref:System.Int32>[]  
  
- <xref:System.Int64>  
  
- <xref:System.Int64>[]  
  
- <xref:System.Single>  
  
- <xref:System.Single>[]  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <xref:System.UInt16>[]  
  
- <xref:System.UInt32>  
  
- <xref:System.UInt32>[]  
  
- <xref:System.UInt64>  
  
- <xref:System.UInt64>[]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo agregar y recuperar los datos personalizados de un <xref:System.Windows.Ink.StrokeCollection>.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 En el ejemplo siguiente se crea una aplicación que muestra un <xref:System.Windows.Controls.InkCanvas> y dos botones.  El botón, `switchAuthor`, permite que dos lápices que va a utilizar dos autores diferentes.  El botón `changePenColors` cambia el color de cada trazo en el <xref:System.Windows.Controls.InkCanvas> según el autor.  La aplicación define dos <xref:System.Windows.Ink.DrawingAttributes> objetos y agrega una propiedad personalizada a cada uno de ellos que indica que el autor ha dibujado el <xref:System.Windows.Ink.Stroke>.  Cuando el usuario hace clic en `changePenColors`, la aplicación cambia la apariencia del trazo según el valor de la propiedad personalizada.  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
