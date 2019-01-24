---
title: Procedimiento Imprimir un formulario de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 5e672f40797a90111daefed0be74c941d4cc37b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628141"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="841da-102">Procedimiento Imprimir un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="841da-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="841da-103">Como parte del proceso de desarrollo, normalmente deseará imprimir una copia del formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="841da-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="841da-104">El ejemplo de código siguiente muestra cómo imprimir una copia del formulario actual mediante el <xref:System.Drawing.Graphics.CopyFromScreen%2A> método.</span><span class="sxs-lookup"><span data-stu-id="841da-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="841da-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="841da-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="841da-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="841da-106">Compiling the Code</span></span>  
 <span data-ttu-id="841da-107">Este es un ejemplo de código completo que contiene un `Main` método.</span><span class="sxs-lookup"><span data-stu-id="841da-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="841da-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="841da-108">Robust Programming</span></span>  
 <span data-ttu-id="841da-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="841da-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="841da-110">No tiene permiso para tener acceso a la impresora.</span><span class="sxs-lookup"><span data-stu-id="841da-110">You do not have permission to access the printer.</span></span>  
  
-   <span data-ttu-id="841da-111">No hay ninguna impresora instalada.</span><span class="sxs-lookup"><span data-stu-id="841da-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="841da-112">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="841da-112">.NET Framework Security</span></span>  
 <span data-ttu-id="841da-113">Para ejecutar este ejemplo de código, debe tener permiso para tener acceso a la impresora que utilice con el equipo.</span><span class="sxs-lookup"><span data-stu-id="841da-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841da-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="841da-114">See also</span></span>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="841da-115">Cómo: Representar imágenes con GDI +</span><span class="sxs-lookup"><span data-stu-id="841da-115">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
- [<span data-ttu-id="841da-116">Cómo: Imprimir gráficos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="841da-116">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
