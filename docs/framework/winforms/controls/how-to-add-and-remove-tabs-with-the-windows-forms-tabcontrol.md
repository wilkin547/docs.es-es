---
title: "C&#243;mo: Agregar y quitar fichas con el control TabControl de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "páginas de fichas"
  - "TabControl (control) [Windows Forms], agregar y quitar fichas"
  - "TabPage (control)"
  - "pestañas, agregar a páginas"
  - "pestañas, quitar de páginas"
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Agregar y quitar fichas con el control TabControl de formularios Windows Forms
De forma predeterminada, un control <xref:System.Windows.Forms.TabControl> contiene dos controles <xref:System.Windows.Forms.TabPage>.  Puede tener acceso a estas fichas a través de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
### Para agregar una ficha mediante programación  
  
-   Utilice el método <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
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
  
### Para quitar una ficha mediante programación  
  
-   Para quitar las fichas seleccionadas, utilice el método <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
     O bien  
  
-   Para quitar todas las fichas, utilice el método <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> de la propiedad <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
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
  
## Vea también  
 [Información general del control TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Cómo: Agregar un control a una página de fichas](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [Cómo: Deshabilitar páginas de ficha](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [Cómo: Cambiar la apariencia del control TabControl de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)