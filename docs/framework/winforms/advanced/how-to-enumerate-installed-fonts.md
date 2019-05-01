---
title: Procedimiento para enumerar las fuentes instaladas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 92f27399cce9e03a4679c8a34fbdafcf28c32252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004104"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="7f1cf-102">Procedimiento para enumerar las fuentes instaladas</span><span class="sxs-lookup"><span data-stu-id="7f1cf-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="7f1cf-103">El <xref:System.Drawing.Text.InstalledFontCollection> clase hereda de la <xref:System.Drawing.Text.FontCollection> clase base abstracta.</span><span class="sxs-lookup"><span data-stu-id="7f1cf-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="7f1cf-104">Puede usar un <xref:System.Drawing.Text.InstalledFontCollection> objeto para enumerar las fuentes instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7f1cf-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="7f1cf-105">El <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad de un <xref:System.Drawing.Text.InstalledFontCollection> objeto es una matriz de <xref:System.Drawing.FontFamily> objetos.</span><span class="sxs-lookup"><span data-stu-id="7f1cf-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f1cf-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f1cf-106">Example</span></span>  
 <span data-ttu-id="7f1cf-107">El ejemplo siguiente enumeran los nombres de todas las familias de fuentes instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7f1cf-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="7f1cf-108">El código recupera el <xref:System.Drawing.FontFamily.Name%2A> propiedad de cada uno <xref:System.Drawing.FontFamily> objeto en la matriz devuelta por la <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7f1cf-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="7f1cf-109">Como se recuperan los nombres de familia, se concatenan para lista separada por comas de formulario.</span><span class="sxs-lookup"><span data-stu-id="7f1cf-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="7f1cf-110">El <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase dibuja la lista separada por comas en un rectángulo.</span><span class="sxs-lookup"><span data-stu-id="7f1cf-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="7f1cf-111">Si ejecuta el código de ejemplo, el resultado será similar al que se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f1cf-111">If you run the example code, the output will be similar to that shown in the following illustration:</span></span>  
  
 ![Captura de pantalla que muestra las familias de fuentes instaladas.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7f1cf-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="7f1cf-113">Compiling the Code</span></span>  
 <span data-ttu-id="7f1cf-114">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="7f1cf-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="7f1cf-115">Además, debe importar el <xref:System.Drawing.Text> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7f1cf-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f1cf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f1cf-116">See also</span></span>

- [<span data-ttu-id="7f1cf-117">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="7f1cf-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
