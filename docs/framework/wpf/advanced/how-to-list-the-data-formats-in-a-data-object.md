---
title: Procedimiento Mostrar los formatos de datos en un objeto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: f8230eac33a18a0d99cc757d54c2b901c1afe977
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077750"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="17632-102">Procedimiento Mostrar los formatos de datos en un objeto de datos</span><span class="sxs-lookup"><span data-stu-id="17632-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="17632-103">Los ejemplos siguientes muestran cómo usar el <xref:System.Windows.DataObject.GetFormats%2A> sobrecargas del método obtención una matriz de cadenas que denotan cada formato de datos que está disponible en un objeto de datos.</span><span class="sxs-lookup"><span data-stu-id="17632-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17632-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17632-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="17632-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="17632-105">Description</span></span>  
 <span data-ttu-id="17632-106">El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetFormats%2A> sobrecarga para obtener una matriz de cadenas que denotan todos los formatos de datos disponibles en un objeto de datos (nativo y convertir automáticamente).</span><span class="sxs-lookup"><span data-stu-id="17632-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="17632-107">Código</span><span class="sxs-lookup"><span data-stu-id="17632-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="17632-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17632-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="17632-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="17632-109">Description</span></span>  
 <span data-ttu-id="17632-110">El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetFormats%2A> sobrecarga para obtener una matriz de cadenas que denotan sólo los formatos de datos disponibles en un objeto de datos (se filtran los formatos de datos automática convertible).</span><span class="sxs-lookup"><span data-stu-id="17632-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="17632-111">Código</span><span class="sxs-lookup"><span data-stu-id="17632-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="17632-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="17632-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="17632-113">Información general sobre la función de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="17632-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
