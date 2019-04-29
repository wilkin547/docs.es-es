---
title: Procedimiento Determinar si un formato de datos está presente en un objeto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
ms.openlocfilehash: 4cec733490e2a9dc5d54b3b253ac38a5090ac885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776251"
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="04ee0-102">Procedimiento Determinar si un formato de datos está presente en un objeto de datos</span><span class="sxs-lookup"><span data-stu-id="04ee0-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="04ee0-103">Los ejemplos siguientes muestran cómo usar las distintas <xref:System.Windows.DataObject.GetDataPresent%2A> sobrecargas del método para consultar si un formato concreto está presente en un objeto de datos.</span><span class="sxs-lookup"><span data-stu-id="04ee0-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04ee0-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04ee0-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="04ee0-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="04ee0-105">Description</span></span>  
 <span data-ttu-id="04ee0-106">El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> sobrecarga para consultar la presencia de un formato concreto mediante la cadena de descriptor.</span><span class="sxs-lookup"><span data-stu-id="04ee0-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="04ee0-107">Código</span><span class="sxs-lookup"><span data-stu-id="04ee0-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="04ee0-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04ee0-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="04ee0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="04ee0-109">Description</span></span>  
 <span data-ttu-id="04ee0-110">El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> sobrecarga para consultar la presencia de un formato concreto por tipo.</span><span class="sxs-lookup"><span data-stu-id="04ee0-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="04ee0-111">Código</span><span class="sxs-lookup"><span data-stu-id="04ee0-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="04ee0-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04ee0-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="04ee0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="04ee0-113">Description</span></span>  
 <span data-ttu-id="04ee0-114">El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> sobrecarga para consultar los datos mediante la cadena de descriptor y especificar cómo tratar los formatos de datos.</span><span class="sxs-lookup"><span data-stu-id="04ee0-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="04ee0-115">Código</span><span class="sxs-lookup"><span data-stu-id="04ee0-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="04ee0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="04ee0-116">See also</span></span>

- <xref:System.Windows.IDataObject>
