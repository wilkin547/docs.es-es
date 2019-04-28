---
title: Procedimiento Crear un botón que tenga una imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: 5be928ac75ad727feabcde07ac0c6dc76ed130e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910954"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="8cbcf-102">Procedimiento Crear un botón que tenga una imagen</span><span class="sxs-lookup"><span data-stu-id="8cbcf-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="8cbcf-103">En este ejemplo se muestra cómo incluir una imagen en un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="8cbcf-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cbcf-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8cbcf-104">Example</span></span>  
 <span data-ttu-id="8cbcf-105">En el ejemplo siguiente se crean dos <xref:System.Windows.Controls.Button> controles.</span><span class="sxs-lookup"><span data-stu-id="8cbcf-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="8cbcf-106">Una <xref:System.Windows.Controls.Button> contiene texto y el otro contiene una imagen.</span><span class="sxs-lookup"><span data-stu-id="8cbcf-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="8cbcf-107">La imagen está en una carpeta denominada datos, que es una subcarpeta de la carpeta del proyecto del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8cbcf-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="8cbcf-108">Cuando un usuario hace clic en el <xref:System.Windows.Controls.Button> que tiene la imagen, el fondo y el texto de la otra <xref:System.Windows.Controls.Button> cambiar.</span><span class="sxs-lookup"><span data-stu-id="8cbcf-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="8cbcf-109">Este ejemplo se crea <xref:System.Windows.Controls.Button> controla mediante el uso de marcado, pero usa el código para escribir el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="8cbcf-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="8cbcf-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cbcf-110">See also</span></span>

- [<span data-ttu-id="8cbcf-111">Controles</span><span class="sxs-lookup"><span data-stu-id="8cbcf-111">Controls</span></span>](index.md)
- [<span data-ttu-id="8cbcf-112">Biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="8cbcf-112">Control Library</span></span>](control-library.md)
