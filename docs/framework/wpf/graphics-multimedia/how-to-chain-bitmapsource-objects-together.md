---
title: 'Cómo: Encadenar objetos BitmapSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BitmapSource objects [WPF], chaining
- graphics [WPF], chaining BitmapSource objects
- chaining BitmapSource objects [WPF]
ms.assetid: 32d88853-395b-4855-9685-51a482a3b421
ms.openlocfilehash: 5c70b6ec132234959404203fb62567ddb0acf762
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558870"
---
# <a name="how-to-chain-bitmapsource-objects-together"></a><span data-ttu-id="e8971-102">Cómo: Encadenar objetos BitmapSource</span><span class="sxs-lookup"><span data-stu-id="e8971-102">How to: Chain BitmapSource Objects Together</span></span>
<span data-ttu-id="e8971-103">Este ejemplo muestra cómo se puede aplicar una variedad de efectos a un origen de imagen con el encadenamiento de varios <xref:System.Windows.Media.Imaging.BitmapSource> objetos derivados juntos.</span><span class="sxs-lookup"><span data-stu-id="e8971-103">This example shows how you can apply a variety of effects to an image source by chaining multiple <xref:System.Windows.Media.Imaging.BitmapSource> derived objects together.</span></span>  
  
 <span data-ttu-id="e8971-104">En el ejemplo siguiente se utiliza el encadenamiento para voltear y cambiar el formato de píxel del origen de una imagen.</span><span class="sxs-lookup"><span data-stu-id="e8971-104">The following example uses chaining to flip and change the pixel format of the source of an image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8971-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8971-105">Example</span></span>  
 [!code-xaml[ImagingSnippetGallery_snip#ChainedBitmapSourcesXamlExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_snip/CS/ChainedBitmapSourcesExample.xaml#chainedbitmapsourcesxamlexamplewholepage)]  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/ChainedBitmapSourcesExample.cs#chainedbitmapsourcescodeexamplewholepage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/ChainedBitmapSourcesExample.vb#chainedbitmapsourcescodeexamplewholepage)]
