---
title: Procedimiento para obtener acceso a colecciones con claves en formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: a88e4766a1e774582bcd0356c9b6e77bc31f1960
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928527"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="ad646-102">Procedimiento para obtener acceso a colecciones con claves en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad646-102">How to: Access Keyed Collections in Windows Forms</span></span>

- <span data-ttu-id="ad646-103">Puede tener acceso a elementos individuales de la colección por clave.</span><span class="sxs-lookup"><span data-stu-id="ad646-103">You can access individual collection items by key.</span></span> <span data-ttu-id="ad646-104">Esta funcionalidad se ha agregado a muchas clases de colección que suelen usar Windows Forms aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ad646-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="ad646-105">En la lista siguiente se muestran algunas de las clases de colección que tienen colecciones con clave accesibles:</span><span class="sxs-lookup"><span data-stu-id="ad646-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="ad646-106">La clave asociada con un elemento de una colección es normalmente el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="ad646-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="ad646-107">Los procedimientos siguientes muestran cómo usar las clases de colección para realizar tareas comunes.</span><span class="sxs-lookup"><span data-stu-id="ad646-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="ad646-108">Para buscar y dar el foco a un control anidado en una colección de controles</span><span class="sxs-lookup"><span data-stu-id="ad646-108">To find and give focus to a nested control in a control collection</span></span>  
  
- <span data-ttu-id="ad646-109">Utilice los <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> métodos <xref:System.Windows.Forms.Control.Focus%2A> y para especificar el nombre del control que se va a buscar y proporcionar el foco.</span><span class="sxs-lookup"><span data-stu-id="ad646-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="ad646-110">Para tener acceso a una imagen en una colección de imágenes</span><span class="sxs-lookup"><span data-stu-id="ad646-110">To access an image in an image collection</span></span>  
  
- <span data-ttu-id="ad646-111">Utilice la <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> propiedad para especificar el nombre de la imagen a la que desea obtener acceso.</span><span class="sxs-lookup"><span data-stu-id="ad646-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="ad646-112">Para establecer una página de ficha como la pestaña seleccionada</span><span class="sxs-lookup"><span data-stu-id="ad646-112">To set a tab page as the selected tab</span></span>  
  
- <span data-ttu-id="ad646-113">Utilice la <xref:System.Windows.Forms.TabControl.SelectedTab%2A> propiedad junto con la <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> propiedad para especificar el nombre de la página de ficha que se va a establecer como la pestaña seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ad646-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ad646-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad646-114">See also</span></span>

- [<span data-ttu-id="ad646-115">Introducción a los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad646-115">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="ad646-116">Cómo: Agregar o quitar imágenes con el componente de ImageList Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad646-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
