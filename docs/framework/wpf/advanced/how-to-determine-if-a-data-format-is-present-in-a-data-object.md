---
title: "Cómo: Determinar si un formato de datos está presente en un objeto de datos"
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
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9e5eaad64e18ff955340a8e91bfe8bd0e09dd8d7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="bf356-102">Cómo: Determinar si un formato de datos está presente en un objeto de datos</span><span class="sxs-lookup"><span data-stu-id="bf356-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="bf356-103">Los ejemplos siguientes muestran cómo usar las distintas <xref:System.Windows.DataObject.GetDataPresent%2A> sobrecargas de método para consultar si un formato de datos determinado se encuentra presente en un objeto de datos.</span><span class="sxs-lookup"><span data-stu-id="bf356-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf356-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf356-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bf356-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf356-105">Description</span></span>  
 <span data-ttu-id="bf356-106">El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> sobrecarga para consultar la presencia de un formato de datos concreto por cadena del descriptor.</span><span class="sxs-lookup"><span data-stu-id="bf356-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bf356-107">Código</span><span class="sxs-lookup"><span data-stu-id="bf356-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="bf356-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf356-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bf356-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf356-109">Description</span></span>  
 <span data-ttu-id="bf356-110">El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> sobrecarga para consultar la presencia de un formato de datos concreto por tipo.</span><span class="sxs-lookup"><span data-stu-id="bf356-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bf356-111">Código</span><span class="sxs-lookup"><span data-stu-id="bf356-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="bf356-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf356-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bf356-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf356-113">Description</span></span>  
 <span data-ttu-id="bf356-114">El código de ejemplo siguiente usa el <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> sobrecargar para consultar los datos por cadena del descriptor y especificar cómo tratar los formatos de datos automática.</span><span class="sxs-lookup"><span data-stu-id="bf356-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bf356-115">Código</span><span class="sxs-lookup"><span data-stu-id="bf356-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="bf356-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf356-116">See Also</span></span>  
 <xref:System.Windows.IDataObject>
