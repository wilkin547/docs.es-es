---
title: "Cómo: Utilizar un objeto ThicknessConverter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ce70dcd749f31d77061b4669d83d2e0b83726c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="5b39b-102">Cómo: Utilizar un objeto ThicknessConverter</span><span class="sxs-lookup"><span data-stu-id="5b39b-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="5b39b-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b39b-103">Example</span></span>  
 <span data-ttu-id="5b39b-104">Este ejemplo muestra cómo crear una instancia de <xref:System.Windows.ThicknessConverter> y usarlo para cambiar el grosor de un borde.</span><span class="sxs-lookup"><span data-stu-id="5b39b-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="5b39b-105">En el ejemplo se define un método personalizado denominado `changeThickness`; en primer lugar, este método convierte el contenido de un <xref:System.Windows.Controls.ListBoxItem>, tal como se define en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo a una instancia de <xref:System.Windows.Thickness>y más adelante convierte el contenido en un <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5b39b-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="5b39b-106">Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a una <xref:System.Windows.ThicknessConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Windows.Thickness>.</span><span class="sxs-lookup"><span data-stu-id="5b39b-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="5b39b-107">Este valor, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.Border.BorderThickness%2A> propiedad de la <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="5b39b-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="5b39b-108">En este ejemplo no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="5b39b-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5b39b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b39b-109">See Also</span></span>  
 <xref:System.Windows.Thickness>  
 <xref:System.Windows.ThicknessConverter>  
 <xref:System.Windows.Controls.Border>  
 [<span data-ttu-id="5b39b-110">Cómo: cambiar la propiedad Margin</span><span class="sxs-lookup"><span data-stu-id="5b39b-110">How to: Change the Margin Property</span></span>](http://msdn.microsoft.com/en-us/8a313efd-5f99-4097-b4c1-8fa49d8379a2)  
 [<span data-ttu-id="5b39b-111">Cómo: convertir un elemento ListBoxItem en un nuevo tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5b39b-111">How to: Convert a ListBoxItem to a new Data Type</span></span>](http://msdn.microsoft.com/en-us/7a080b88-184e-4b27-bb61-d42bafba9727)  
 [<span data-ttu-id="5b39b-112">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="5b39b-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
