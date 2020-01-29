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
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>Cómo: Agregar y quitar fichas con el control TabControl de Windows Forms
De forma predeterminada, un control <xref:System.Windows.Forms.TabControl> contiene dos controles <xref:System.Windows.Forms.TabPage>. Puede tener acceso a estas pestañas a través de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
### <a name="to-add-a-tab-programmatically"></a>Para agregar una pestaña mediante programación  
  
- Use el método <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a>Para quitar una pestaña mediante programación  
  
- Para quitar las pestañas seleccionadas, use el método <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
     O bien,  
  
- Para quitar todas las pestañas, utilice el método <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
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
  
## <a name="see-also"></a>Vea también

- [Información general del control TabControl](tabcontrol-control-overview-windows-forms.md)
- [Agregar un control a una página de fichas](how-to-add-a-control-to-a-tab-page.md)
- [Deshabilitar páginas de ficha](how-to-disable-tab-pages.md)
- [Cambiar la apariencia del control TabControl de Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
