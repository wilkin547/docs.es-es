---
title: Personalizar la apariencia de las filas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: 099b2104e7a4887aa846c4d65273db2dd4f60559
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744039"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d8711-102">Cómo: Personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d8711-102">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d8711-103">Puede controlar la apariencia de las filas de <xref:System.Windows.Forms.DataGridView> controlando el evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>, o ambos.</span><span class="sxs-lookup"><span data-stu-id="d8711-103">You can control the appearance of <xref:System.Windows.Forms.DataGridView> rows by handling one or both of the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> and <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> events.</span></span> <span data-ttu-id="d8711-104">Estos eventos están diseñados para que pueda representar solo lo que se desea mientras permite que el control <xref:System.Windows.Forms.DataGridView> represente el resto.</span><span class="sxs-lookup"><span data-stu-id="d8711-104">These events are designed so that you can paint only what you want to while letting the <xref:System.Windows.Forms.DataGridView> control paint the rest.</span></span> <span data-ttu-id="d8711-105">Por ejemplo, si quiere representar un fondo personalizado, puede controlar el evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> y dejar que las celdas individuales representen su propio contenido de primer plano.</span><span class="sxs-lookup"><span data-stu-id="d8711-105">For example, if you want to paint a custom background, you can handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event and let the individual cells paint their own foreground content.</span></span> <span data-ttu-id="d8711-106">También tiene la opción de dejar que las celdas se representen a sí mismas y agregar contenido de primer plano personalizado en un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d8711-106">Alternately, you can let the cells paint themselves and add custom foreground content in a handler for the <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="d8711-107">Además, puede deshabilitar la representación de las celdas y representar todo usted mismo en un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d8711-107">You can also disable cell painting and paint everything yourself in a <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event handler.</span></span>  
  
 <span data-ttu-id="d8711-108">En el ejemplo de código siguiente, se implementan controladores de ambos eventos para ofrecer un fondo de selección de degradado y algún contenido de primer plano personalizado que abarca varias columnas.</span><span class="sxs-lookup"><span data-stu-id="d8711-108">The following code example implements handlers for both events in order to provide a gradient selection background and some custom foreground content that spans multiple columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8711-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8711-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d8711-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d8711-110">Compiling the Code</span></span>  
 <span data-ttu-id="d8711-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="d8711-111">This example requires:</span></span>  
  
- <span data-ttu-id="d8711-112">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d8711-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8711-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8711-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [<span data-ttu-id="d8711-114">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d8711-114">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d8711-115">Arquitectura del control DataGridView</span><span class="sxs-lookup"><span data-stu-id="d8711-115">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
