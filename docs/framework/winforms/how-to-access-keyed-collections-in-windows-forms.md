---
title: 'Cómo: obtener acceso a colecciones con clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: 717ba9cc8605da08701de1bd13d6bc6da1c9b758
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739615"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="78afa-102">Cómo: Obtener acceso a colecciones con claves en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="78afa-102">How to: Access Keyed Collections in Windows Forms</span></span>

- <span data-ttu-id="78afa-103">Puede tener acceso a elementos individuales de la colección por clave.</span><span class="sxs-lookup"><span data-stu-id="78afa-103">You can access individual collection items by key.</span></span> <span data-ttu-id="78afa-104">Esta funcionalidad se ha agregado a muchas clases de colección que suelen usar Windows Forms aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="78afa-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="78afa-105">En la lista siguiente se muestran algunas de las clases de colección que tienen colecciones con clave accesibles:</span><span class="sxs-lookup"><span data-stu-id="78afa-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="78afa-106">La clave asociada con un elemento de una colección es normalmente el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="78afa-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="78afa-107">Los procedimientos siguientes muestran cómo usar las clases de colección para realizar tareas comunes.</span><span class="sxs-lookup"><span data-stu-id="78afa-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="78afa-108">Para buscar y dar el foco a un control anidado en una colección de controles</span><span class="sxs-lookup"><span data-stu-id="78afa-108">To find and give focus to a nested control in a control collection</span></span>  
  
- <span data-ttu-id="78afa-109">Utilice los métodos <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> y <xref:System.Windows.Forms.Control.Focus%2A> para especificar el nombre del control que se va a buscar y proporcionar el foco.</span><span class="sxs-lookup"><span data-stu-id="78afa-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="78afa-110">Para tener acceso a una imagen en una colección de imágenes</span><span class="sxs-lookup"><span data-stu-id="78afa-110">To access an image in an image collection</span></span>  
  
- <span data-ttu-id="78afa-111">Use la propiedad <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> para especificar el nombre de la imagen a la que desea obtener acceso.</span><span class="sxs-lookup"><span data-stu-id="78afa-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="78afa-112">Para establecer una página de ficha como la pestaña seleccionada</span><span class="sxs-lookup"><span data-stu-id="78afa-112">To set a tab page as the selected tab</span></span>  
  
- <span data-ttu-id="78afa-113">Use la propiedad <xref:System.Windows.Forms.TabControl.SelectedTab%2A> junto con la propiedad <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> para especificar el nombre de la página de ficha que se va a establecer como la pestaña seleccionada.</span><span class="sxs-lookup"><span data-stu-id="78afa-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="78afa-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="78afa-114">See also</span></span>

- [<span data-ttu-id="78afa-115">Introducción a los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="78afa-115">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="78afa-116">Agregar o quitar imágenes con el componente ImageList de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="78afa-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
