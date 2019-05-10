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
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="19de7-102">Procedimiento Agregar datos personalizados a datos de entrada de lápiz</span><span class="sxs-lookup"><span data-stu-id="19de7-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="19de7-103">Puede agregar datos personalizados a la entrada de lápiz que se guardarán cuando se guarda la entrada de lápiz como formato serializado de tinta (ISF).</span><span class="sxs-lookup"><span data-stu-id="19de7-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="19de7-104">Puede guardar los datos personalizados a la <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, o el <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="19de7-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="19de7-105">Posibilidad de guardar los datos personalizados en los tres objetos le permite decidir el mejor lugar para guardar los datos.</span><span class="sxs-lookup"><span data-stu-id="19de7-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="19de7-106">Las tres clases usan métodos similares para almacenar y acceder a los datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="19de7-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="19de7-107">Solo los tipos siguientes se pueden guardar como datos personalizados:</span><span class="sxs-lookup"><span data-stu-id="19de7-107">Only the following types can be saved as custom data:</span></span>  
  
- <xref:System.Boolean>  
  
- <span data-ttu-id="19de7-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-108"><xref:System.Boolean>[]</span></span>  
  
- <xref:System.Byte>  
  
- <span data-ttu-id="19de7-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-109"><xref:System.Byte>[]</span></span>  
  
- <xref:System.Char>  
  
- <span data-ttu-id="19de7-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-110"><xref:System.Char>[]</span></span>  
  
- <xref:System.DateTime>  
  
- <span data-ttu-id="19de7-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-111"><xref:System.DateTime>[]</span></span>  
  
- <xref:System.Decimal>  
  
- <span data-ttu-id="19de7-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-112"><xref:System.Decimal>[]</span></span>  
  
- <xref:System.Double>  
  
- <span data-ttu-id="19de7-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-113"><xref:System.Double>[]</span></span>  
  
- <xref:System.Int16>  
  
- <span data-ttu-id="19de7-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-114"><xref:System.Int16>[]</span></span>  
  
- <xref:System.Int32>  
  
- <span data-ttu-id="19de7-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-115"><xref:System.Int32>[]</span></span>  
  
- <xref:System.Int64>  
  
- <span data-ttu-id="19de7-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-116"><xref:System.Int64>[]</span></span>  
  
- <xref:System.Single>  
  
- <span data-ttu-id="19de7-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-117"><xref:System.Single>[]</span></span>  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <span data-ttu-id="19de7-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-118"><xref:System.UInt16>[]</span></span>  
  
- <xref:System.UInt32>  
  
- <span data-ttu-id="19de7-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-119"><xref:System.UInt32>[]</span></span>  
  
- <xref:System.UInt64>  
  
- <span data-ttu-id="19de7-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="19de7-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="19de7-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19de7-121">Example</span></span>  
 <span data-ttu-id="19de7-122">En el ejemplo siguiente se muestra cómo agregar y recuperar los datos personalizados de un <xref:System.Windows.Ink.StrokeCollection>.</span><span class="sxs-lookup"><span data-stu-id="19de7-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="19de7-123">En el ejemplo siguiente se crea una aplicación que muestra un <xref:System.Windows.Controls.InkCanvas> y dos botones.</span><span class="sxs-lookup"><span data-stu-id="19de7-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="19de7-124">El botón, `switchAuthor`, permite que dos lápices que va a utilizar dos autores diferentes.</span><span class="sxs-lookup"><span data-stu-id="19de7-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="19de7-125">El botón `changePenColors` cambia el color de cada trazo en el <xref:System.Windows.Controls.InkCanvas> según el autor.</span><span class="sxs-lookup"><span data-stu-id="19de7-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="19de7-126">La aplicación define dos <xref:System.Windows.Ink.DrawingAttributes> objetos y agrega una propiedad personalizada a cada uno de ellos que indica que el autor ha dibujado el <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="19de7-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="19de7-127">Cuando el usuario hace clic en `changePenColors`, la aplicación cambia la apariencia del trazo según el valor de la propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="19de7-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
