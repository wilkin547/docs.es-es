---
title: Filtrar para agregar elementos de menú a un objeto ContextMenuStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: 534bbd2c2edb68dca0f2a1c2997ff1ba762ef07c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135088"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="b5e41-102">Filtrar para agregar elementos de menú a un objeto ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="b5e41-102">How to: Add Menu Items to a ContextMenuStrip</span></span>
<span data-ttu-id="b5e41-103">Puede agregar simplemente un elemento de menú o varios elementos a la vez a un <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b5e41-103">You can add just one menu item or several items at a time to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a><span data-ttu-id="b5e41-104">Para agregar un solo elemento de menú a ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="b5e41-104">To add a single menu item to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="b5e41-105">Use la <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> método para agregar un elemento de menú a un <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b5e41-105">Use the <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add one menu item to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="b5e41-106">Para agregar varios elementos de menú a ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="b5e41-106">To add several menu items to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="b5e41-107">Use la <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> método para agregar varios elementos de menú a un <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b5e41-107">Use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> method to add several menu items to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b5e41-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5e41-108">See also</span></span>

- [<span data-ttu-id="b5e41-109">ContextMenuStrip (Control)</span><span class="sxs-lookup"><span data-stu-id="b5e41-109">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
