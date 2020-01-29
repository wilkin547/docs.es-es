---
title: Agregar y quitar pestañas con TabControl
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
ms.openlocfilehash: 8292d8441f9b47334b98736cf3282c846673dbb4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732718"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="1e898-102">Cómo: Agregar y quitar fichas con el control TabControl de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1e898-102">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="1e898-103">De forma predeterminada, un control <xref:System.Windows.Forms.TabControl> contiene dos controles <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="1e898-103">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="1e898-104">Puede tener acceso a estas pestañas a través de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e898-104">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="1e898-105">Para agregar una pestaña mediante programación</span><span class="sxs-lookup"><span data-stu-id="1e898-105">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="1e898-106">Use el método <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e898-106">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="1e898-107">Para quitar una pestaña mediante programación</span><span class="sxs-lookup"><span data-stu-id="1e898-107">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="1e898-108">Para quitar las pestañas seleccionadas, use el método <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e898-108">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="1e898-109">O bien,</span><span class="sxs-lookup"><span data-stu-id="1e898-109">-or-</span></span>  
  
- <span data-ttu-id="1e898-110">Para quitar todas las pestañas, utilice el método <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e898-110">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1e898-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e898-111">See also</span></span>

- [<span data-ttu-id="1e898-112">Información general del control TabControl</span><span class="sxs-lookup"><span data-stu-id="1e898-112">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="1e898-113">Agregar un control a una página de fichas</span><span class="sxs-lookup"><span data-stu-id="1e898-113">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="1e898-114">Deshabilitar páginas de ficha</span><span class="sxs-lookup"><span data-stu-id="1e898-114">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="1e898-115">Cambiar la apariencia del control TabControl de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1e898-115">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
