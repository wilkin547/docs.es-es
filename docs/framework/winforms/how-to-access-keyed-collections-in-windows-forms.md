---
title: "Cómo: Obtener acceso a colecciones con claves en Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2bca9b56f37c815bfa9f1520467ae0ae864c14ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="8bad5-102">Cómo: Obtener acceso a colecciones con claves en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8bad5-102">How to: Access Keyed Collections in Windows Forms</span></span>
-   <span data-ttu-id="8bad5-103">Puede tener acceso a elementos de colección individuales por clave.</span><span class="sxs-lookup"><span data-stu-id="8bad5-103">You can access individual collection items by key.</span></span> <span data-ttu-id="8bad5-104">Esta funcionalidad se ha agregado a muchas clases de colección que se suelen usar en aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8bad5-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="8bad5-105">En la lista siguiente muestra algunas de las clases de colección que tienen colecciones con claves accesibles:</span><span class="sxs-lookup"><span data-stu-id="8bad5-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="8bad5-106">La clave asociada con un elemento de una colección normalmente es el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="8bad5-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="8bad5-107">Los procedimientos siguientes muestran cómo utilizar las clases de colección para realizar tareas comunes.</span><span class="sxs-lookup"><span data-stu-id="8bad5-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="8bad5-108">Para buscar y asignar el foco a un control anidado en una colección de controles</span><span class="sxs-lookup"><span data-stu-id="8bad5-108">To find and give focus to a nested control in a control collection</span></span>  
  
-   <span data-ttu-id="8bad5-109">Use la <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> y <xref:System.Windows.Forms.Control.Focus%2A> métodos para especificar el nombre del control para buscar y asignar el foco a.</span><span class="sxs-lookup"><span data-stu-id="8bad5-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="8bad5-110">Para obtener acceso a una imagen en una colección de imágenes</span><span class="sxs-lookup"><span data-stu-id="8bad5-110">To access an image in an image collection</span></span>  
  
-   <span data-ttu-id="8bad5-111">Use la <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> propiedad para especificar el nombre de la imagen que desea tener acceso.</span><span class="sxs-lookup"><span data-stu-id="8bad5-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="8bad5-112">Para establecer una página de fichas como la ficha seleccionada</span><span class="sxs-lookup"><span data-stu-id="8bad5-112">To set a tab page as the selected tab</span></span>  
  
-   <span data-ttu-id="8bad5-113">Use la <xref:System.Windows.Forms.TabControl.SelectedTab%2A> propiedad junto con la <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> propiedad para especificar el nombre de la página de fichas para establecer como la ficha seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8bad5-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8bad5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bad5-114">See Also</span></span>  
 [<span data-ttu-id="8bad5-115">Introducción a los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8bad5-115">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [<span data-ttu-id="8bad5-116">Agregar o quitar imágenes con el componente ImageList de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8bad5-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
