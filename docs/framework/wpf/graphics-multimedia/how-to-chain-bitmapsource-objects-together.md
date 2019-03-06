---
title: Procedimiento Encadenar objetos BitmapSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BitmapSource objects [WPF], chaining
- graphics [WPF], chaining BitmapSource objects
- chaining BitmapSource objects [WPF]
ms.assetid: 32d88853-395b-4855-9685-51a482a3b421
ms.openlocfilehash: 403a2a8683e65fd71df89befd59744ac3fe6200c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377526"
---
# <a name="how-to-chain-bitmapsource-objects-together"></a><span data-ttu-id="e88b6-102">Filtrar Encadenar objetos BitmapSource</span><span class="sxs-lookup"><span data-stu-id="e88b6-102">How to: Chain BitmapSource Objects Together</span></span>
<span data-ttu-id="e88b6-103">En este ejemplo se muestra cómo aplicar diversos efectos a un origen de imagen encadenando varios <xref:System.Windows.Media.Imaging.BitmapSource> objetos derivados entre sí.</span><span class="sxs-lookup"><span data-stu-id="e88b6-103">This example shows how you can apply a variety of effects to an image source by chaining multiple <xref:System.Windows.Media.Imaging.BitmapSource> derived objects together.</span></span>  
  
 <span data-ttu-id="e88b6-104">En el ejemplo siguiente se utiliza el encadenamiento para voltear y cambiar el formato de píxel del origen de una imagen.</span><span class="sxs-lookup"><span data-stu-id="e88b6-104">The following example uses chaining to flip and change the pixel format of the source of an image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e88b6-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e88b6-105">Example</span></span>  
 [!code-xaml[ImagingSnippetGallery_snip#ChainedBitmapSourcesXamlExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_snip/CS/ChainedBitmapSourcesExample.xaml#chainedbitmapsourcesxamlexamplewholepage)]  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/ChainedBitmapSourcesExample.cs#chainedbitmapsourcescodeexamplewholepage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/ChainedBitmapSourcesExample.vb#chainedbitmapsourcescodeexamplewholepage)]
