---
title: Procedimiento Crear un objeto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
ms.openlocfilehash: edc301cb896dc8e704a0e17e8e22366d82cc0c17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687198"
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="02e16-102">Procedimiento Crear un objeto de datos</span><span class="sxs-lookup"><span data-stu-id="02e16-102">How to: Create a Data Object</span></span>
<span data-ttu-id="02e16-103">Los ejemplos siguientes muestran distintas maneras de crear un objeto de datos mediante los constructores proporcionadas por el <xref:System.Windows.DataObject> clase.</span><span class="sxs-lookup"><span data-stu-id="02e16-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02e16-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02e16-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="02e16-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="02e16-105">Description</span></span>  
 <span data-ttu-id="02e16-106">Ejemplo de código siguiente crea un nuevo objeto de datos y utiliza uno de los constructores sobrecargados (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) para inicializar el objeto de datos con una cadena.</span><span class="sxs-lookup"><span data-stu-id="02e16-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="02e16-107">En este caso, un formato de datos adecuado se determina automáticamente según el tipo de datos almacenados, y se permite la conversión automática de los datos almacenados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="02e16-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="02e16-108">Código</span><span class="sxs-lookup"><span data-stu-id="02e16-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="02e16-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="02e16-109">Description</span></span>  
 <span data-ttu-id="02e16-110">Ejemplo de código siguiente es una versión comprimida del código mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="02e16-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="02e16-111">Código</span><span class="sxs-lookup"><span data-stu-id="02e16-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="02e16-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02e16-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="02e16-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="02e16-113">Description</span></span>  
 <span data-ttu-id="02e16-114">Ejemplo de código siguiente crea un nuevo objeto de datos y utiliza uno de los constructores sobrecargados (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) para inicializar el objeto de datos con una cadena y un formato de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="02e16-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="02e16-115">En este caso se especifica el formato de datos mediante una cadena; la <xref:System.Windows.DataFormats> clase proporciona un conjunto de cadenas de tipo predefinidas.</span><span class="sxs-lookup"><span data-stu-id="02e16-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="02e16-116">Se permite la conversión automática de los datos almacenados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="02e16-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="02e16-117">Código</span><span class="sxs-lookup"><span data-stu-id="02e16-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="02e16-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="02e16-118">Description</span></span>  
 <span data-ttu-id="02e16-119">Ejemplo de código siguiente es una versión comprimida del código mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="02e16-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="02e16-120">Código</span><span class="sxs-lookup"><span data-stu-id="02e16-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="02e16-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02e16-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="02e16-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="02e16-122">Description</span></span>  
 <span data-ttu-id="02e16-123">Ejemplo de código siguiente crea un nuevo objeto de datos y utiliza uno de los constructores sobrecargados (<xref:System.Windows.DataObject.%23ctor%2A>) para inicializar el objeto de datos con una cadena y un formato de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="02e16-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="02e16-124">En este caso se especifica el formato de datos por un <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="02e16-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="02e16-125">Se permite la conversión automática de los datos almacenados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="02e16-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="02e16-126">Código</span><span class="sxs-lookup"><span data-stu-id="02e16-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="02e16-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="02e16-127">Description</span></span>  
 <span data-ttu-id="02e16-128">Ejemplo de código siguiente es una versión comprimida del código mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="02e16-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="02e16-129">Código</span><span class="sxs-lookup"><span data-stu-id="02e16-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="02e16-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02e16-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="02e16-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="02e16-131">Description</span></span>  
 <span data-ttu-id="02e16-132">Ejemplo de código siguiente crea un nuevo objeto de datos y utiliza uno de los constructores sobrecargados (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) para inicializar el objeto de datos con una cadena y un formato de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="02e16-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="02e16-133">En este caso se especifica el formato de datos mediante una cadena; la <xref:System.Windows.DataFormats> clase proporciona un conjunto de cadenas de tipo predefinidas.</span><span class="sxs-lookup"><span data-stu-id="02e16-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="02e16-134">Esta sobrecarga del constructor determinado permite al llamador especificar si se permite la conversión automática.</span><span class="sxs-lookup"><span data-stu-id="02e16-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="02e16-135">Código</span><span class="sxs-lookup"><span data-stu-id="02e16-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="02e16-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="02e16-136">Description</span></span>  
 <span data-ttu-id="02e16-137">Ejemplo de código siguiente es una versión comprimida del código mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="02e16-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="02e16-138">Código</span><span class="sxs-lookup"><span data-stu-id="02e16-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="02e16-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="02e16-139">See also</span></span>
- <xref:System.Windows.IDataObject>
