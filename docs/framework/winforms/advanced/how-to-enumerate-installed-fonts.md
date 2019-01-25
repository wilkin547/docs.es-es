---
title: Procedimiento Enumerar las fuentes instaladas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 0124d2bdd8b9c60dc2bf2508348044d76a2c7eb4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602239"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="6304a-102">Procedimiento Enumerar las fuentes instaladas</span><span class="sxs-lookup"><span data-stu-id="6304a-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="6304a-103">El <xref:System.Drawing.Text.InstalledFontCollection> clase hereda de la <xref:System.Drawing.Text.FontCollection> clase base abstracta.</span><span class="sxs-lookup"><span data-stu-id="6304a-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="6304a-104">Puede usar un <xref:System.Drawing.Text.InstalledFontCollection> objeto para enumerar las fuentes instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="6304a-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="6304a-105">El <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad de un <xref:System.Drawing.Text.InstalledFontCollection> objeto es una matriz de <xref:System.Drawing.FontFamily> objetos.</span><span class="sxs-lookup"><span data-stu-id="6304a-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6304a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6304a-106">Example</span></span>  
 <span data-ttu-id="6304a-107">El ejemplo siguiente enumeran los nombres de todas las familias de fuentes instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="6304a-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="6304a-108">El código recupera el <xref:System.Drawing.FontFamily.Name%2A> propiedad de cada uno <xref:System.Drawing.FontFamily> objeto en la matriz devuelta por la <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="6304a-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="6304a-109">Como se recuperan los nombres de familia, se concatenan para lista separada por comas de formulario.</span><span class="sxs-lookup"><span data-stu-id="6304a-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="6304a-110">El <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase dibuja la lista separada por comas en un rectángulo.</span><span class="sxs-lookup"><span data-stu-id="6304a-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="6304a-111">Si ejecuta el código de ejemplo, el resultado será similar al que se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="6304a-111">If you run the example code, the output will be similar to that shown in the following illustration.</span></span>  
  
 <span data-ttu-id="6304a-112">![Las fuentes instaladas](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span><span class="sxs-lookup"><span data-stu-id="6304a-112">![Installed Fonts](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6304a-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="6304a-113">Compiling the Code</span></span>  
 <span data-ttu-id="6304a-114">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="6304a-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="6304a-115">Además, debe importar el <xref:System.Drawing.Text> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6304a-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6304a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6304a-116">See also</span></span>
- [<span data-ttu-id="6304a-117">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="6304a-117">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
