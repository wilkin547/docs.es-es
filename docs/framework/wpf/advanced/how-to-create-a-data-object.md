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
ms.openlocfilehash: f7bdfbf3dba0c700513348195c1d031d4c2c8b65
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370597"
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="e7c53-102">Filtrar Crear un objeto de datos</span><span class="sxs-lookup"><span data-stu-id="e7c53-102">How to: Create a Data Object</span></span>
<span data-ttu-id="e7c53-103">Los ejemplos siguientes muestran distintas maneras de crear un objeto de datos mediante los constructores proporcionadas por el <xref:System.Windows.DataObject> clase.</span><span class="sxs-lookup"><span data-stu-id="e7c53-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7c53-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7c53-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e7c53-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7c53-105">Description</span></span>  
 <span data-ttu-id="e7c53-106">Ejemplo de código siguiente crea un nuevo objeto de datos y utiliza uno de los constructores sobrecargados (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) para inicializar el objeto de datos con una cadena.</span><span class="sxs-lookup"><span data-stu-id="e7c53-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="e7c53-107">En este caso, un formato de datos adecuado se determina automáticamente según el tipo de datos almacenados, y se permite la conversión automática de los datos almacenados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e7c53-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7c53-108">Código</span><span class="sxs-lookup"><span data-stu-id="e7c53-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="e7c53-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7c53-109">Description</span></span>  
 <span data-ttu-id="e7c53-110">Ejemplo de código siguiente es una versión comprimida del código mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e7c53-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7c53-111">Código</span><span class="sxs-lookup"><span data-stu-id="e7c53-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="e7c53-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7c53-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e7c53-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7c53-113">Description</span></span>  
 <span data-ttu-id="e7c53-114">Ejemplo de código siguiente crea un nuevo objeto de datos y utiliza uno de los constructores sobrecargados (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) para inicializar el objeto de datos con una cadena y un formato de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="e7c53-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="e7c53-115">En este caso se especifica el formato de datos mediante una cadena; la <xref:System.Windows.DataFormats> clase proporciona un conjunto de cadenas de tipo predefinidas.</span><span class="sxs-lookup"><span data-stu-id="e7c53-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="e7c53-116">Se permite la conversión automática de los datos almacenados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e7c53-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7c53-117">Código</span><span class="sxs-lookup"><span data-stu-id="e7c53-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="e7c53-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7c53-118">Description</span></span>  
 <span data-ttu-id="e7c53-119">Ejemplo de código siguiente es una versión comprimida del código mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e7c53-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7c53-120">Código</span><span class="sxs-lookup"><span data-stu-id="e7c53-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="e7c53-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7c53-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e7c53-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7c53-122">Description</span></span>  
 <span data-ttu-id="e7c53-123">Ejemplo de código siguiente crea un nuevo objeto de datos y utiliza uno de los constructores sobrecargados (<xref:System.Windows.DataObject.%23ctor%2A>) para inicializar el objeto de datos con una cadena y un formato de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="e7c53-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="e7c53-124">En este caso se especifica el formato de datos por un <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="e7c53-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="e7c53-125">Se permite la conversión automática de los datos almacenados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e7c53-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7c53-126">Código</span><span class="sxs-lookup"><span data-stu-id="e7c53-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="e7c53-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7c53-127">Description</span></span>  
 <span data-ttu-id="e7c53-128">Ejemplo de código siguiente es una versión comprimida del código mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e7c53-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7c53-129">Código</span><span class="sxs-lookup"><span data-stu-id="e7c53-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="e7c53-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7c53-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e7c53-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7c53-131">Description</span></span>  
 <span data-ttu-id="e7c53-132">Ejemplo de código siguiente crea un nuevo objeto de datos y utiliza uno de los constructores sobrecargados (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) para inicializar el objeto de datos con una cadena y un formato de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="e7c53-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="e7c53-133">En este caso se especifica el formato de datos mediante una cadena; la <xref:System.Windows.DataFormats> clase proporciona un conjunto de cadenas de tipo predefinidas.</span><span class="sxs-lookup"><span data-stu-id="e7c53-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="e7c53-134">Esta sobrecarga del constructor determinado permite al llamador especificar si se permite la conversión automática.</span><span class="sxs-lookup"><span data-stu-id="e7c53-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7c53-135">Código</span><span class="sxs-lookup"><span data-stu-id="e7c53-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="e7c53-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7c53-136">Description</span></span>  
 <span data-ttu-id="e7c53-137">Ejemplo de código siguiente es una versión comprimida del código mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e7c53-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7c53-138">Código</span><span class="sxs-lookup"><span data-stu-id="e7c53-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="e7c53-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7c53-139">See also</span></span>
- <xref:System.Windows.IDataObject>
