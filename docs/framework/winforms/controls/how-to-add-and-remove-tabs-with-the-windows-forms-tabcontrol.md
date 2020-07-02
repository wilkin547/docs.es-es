---
title: Agregar y quitar pestañas con TabControl
description: Obtenga información sobre cómo agregar y quitar pestañas con el control TabControl Windows Forms, que contiene dos controles TabPage. Obtenga acceso a estas pestañas a través de la propiedad TabPages.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: 7e67d0bbc13bd7d9c8835dc6fb9b9c5c9333b8bf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618082"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="5504b-104">Procedimiento para agregar y quitar fichas con el control TabControl de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5504b-104">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="5504b-105">De forma predeterminada, un <xref:System.Windows.Forms.TabControl> control contiene dos <xref:System.Windows.Forms.TabPage> controles.</span><span class="sxs-lookup"><span data-stu-id="5504b-105">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="5504b-106">Puede tener acceso a estas pestañas a través de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5504b-106">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="5504b-107">Para agregar una pestaña mediante programación</span><span class="sxs-lookup"><span data-stu-id="5504b-107">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="5504b-108">Use el <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> método de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5504b-108">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="5504b-109">Para quitar una pestaña mediante programación</span><span class="sxs-lookup"><span data-stu-id="5504b-109">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="5504b-110">Para quitar las pestañas seleccionadas, use el <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> método de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5504b-110">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="5504b-111">o bien</span><span class="sxs-lookup"><span data-stu-id="5504b-111">-or-</span></span>  
  
- <span data-ttu-id="5504b-112">Para quitar todas las pestañas, utilice el <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> método de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5504b-112">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5504b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5504b-113">See also</span></span>

- [<span data-ttu-id="5504b-114">Información general sobre el control TabControl</span><span class="sxs-lookup"><span data-stu-id="5504b-114">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="5504b-115">Procedimiento para agregar un control a una ficha</span><span class="sxs-lookup"><span data-stu-id="5504b-115">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="5504b-116">Procedimiento para deshabilitar fichas</span><span class="sxs-lookup"><span data-stu-id="5504b-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="5504b-117">Procedimiento para cambiar el aspecto apariencia del control TabControl de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5504b-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
