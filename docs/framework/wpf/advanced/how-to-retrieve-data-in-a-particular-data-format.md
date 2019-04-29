---
title: Procedimiento Recuperar datos en un formato concreto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: b3ec1b8fa873fd449956912e9e77e98b0362cb0e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768425"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="7db95-102">Procedimiento Recuperar datos en un formato concreto</span><span class="sxs-lookup"><span data-stu-id="7db95-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="7db95-103">Los ejemplos siguientes muestran cómo recuperar datos de un objeto de datos en un formato especificado.</span><span class="sxs-lookup"><span data-stu-id="7db95-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7db95-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7db95-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7db95-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="7db95-105">Description</span></span>  
 <span data-ttu-id="7db95-106">El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> sobrecarga compruebe primero si dar formato a datos especificado está disponible (de forma nativa o mediante la conversión automática); si el formato especificado está disponible, el ejemplo recupera los datos mediante el <xref:System.Windows.DataObject.GetData%28System.String%29> método.</span><span class="sxs-lookup"><span data-stu-id="7db95-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7db95-107">Código</span><span class="sxs-lookup"><span data-stu-id="7db95-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="7db95-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7db95-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7db95-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7db95-109">Description</span></span>  
 <span data-ttu-id="7db95-110">El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> sobrecarga compruebe primero si un formato de datos especificado está disponible de forma nativa (se filtran los formatos de datos); si el formato especificado está disponible, el ejemplo recupera los datos mediante el uso de la <xref:System.Windows.DataObject.GetData%28System.String%29>método.</span><span class="sxs-lookup"><span data-stu-id="7db95-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7db95-111">Código</span><span class="sxs-lookup"><span data-stu-id="7db95-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="7db95-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7db95-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="7db95-113">Información general sobre la función de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="7db95-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
