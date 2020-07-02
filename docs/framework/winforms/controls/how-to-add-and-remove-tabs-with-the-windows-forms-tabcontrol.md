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
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>Procedimiento para agregar y quitar fichas con el control TabControl de formularios Windows Forms
De forma predeterminada, un <xref:System.Windows.Forms.TabControl> control contiene dos <xref:System.Windows.Forms.TabPage> controles. Puede tener acceso a estas pestañas a través de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.  
  
### <a name="to-add-a-tab-programmatically"></a>Para agregar una pestaña mediante programación  
  
- Use el <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> método de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.  
  
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
  
- Para quitar las pestañas seleccionadas, use el <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> método de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.  
  
     o bien  
  
- Para quitar todas las pestañas, utilice el <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> método de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propiedad.  
  
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

- [Información general sobre el control TabControl](tabcontrol-control-overview-windows-forms.md)
- [Procedimiento para agregar un control a una ficha](how-to-add-a-control-to-a-tab-page.md)
- [Procedimiento para deshabilitar fichas](how-to-disable-tab-pages.md)
- [Procedimiento para cambiar el aspecto apariencia del control TabControl de formularios Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
