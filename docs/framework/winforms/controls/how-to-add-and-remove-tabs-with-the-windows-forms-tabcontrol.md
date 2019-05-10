---
title: Procedimiento para agregar y quitar fichas con el control TabControl de formularios Windows Forms
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
ms.openlocfilehash: 938f1210eaa3479822e752327123737a3286fe9a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624057"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="22807-102">Procedimiento para agregar y quitar fichas con el control TabControl de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22807-102">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="22807-103">De forma predeterminada, un <xref:System.Windows.Forms.TabControl> control contiene dos <xref:System.Windows.Forms.TabPage> controles.</span><span class="sxs-lookup"><span data-stu-id="22807-103">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="22807-104">Puede tener acceso a estas pestañas a través de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="22807-104">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="22807-105">Para agregar una ficha mediante programación</span><span class="sxs-lookup"><span data-stu-id="22807-105">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="22807-106">Use la <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> método de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="22807-106">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="22807-107">Para quitar una ficha mediante programación</span><span class="sxs-lookup"><span data-stu-id="22807-107">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="22807-108">Para quitar las fichas seleccionadas, use el <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> método de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="22807-108">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="22807-109">-o bien-</span><span class="sxs-lookup"><span data-stu-id="22807-109">-or-</span></span>  
  
- <span data-ttu-id="22807-110">Para quitar todas las pestañas, use el <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> método de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="22807-110">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="22807-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="22807-111">See also</span></span>

- [<span data-ttu-id="22807-112">Información general del control TabControl</span><span class="sxs-lookup"><span data-stu-id="22807-112">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="22807-113">Cómo: Agregar un Control a una página de ficha</span><span class="sxs-lookup"><span data-stu-id="22807-113">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="22807-114">Cómo: Deshabilitar páginas de fichas</span><span class="sxs-lookup"><span data-stu-id="22807-114">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="22807-115">Cómo: Cambiar la apariencia del control TabControl de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="22807-115">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
