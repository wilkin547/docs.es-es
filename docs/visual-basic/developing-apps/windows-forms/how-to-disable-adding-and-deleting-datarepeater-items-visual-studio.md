---
title: "C&#243;mo: Deshabilitar las operaciones de agregar y eliminar elementos DataRepeater (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, deshabilitar la agregación"
  - "DataRepeater, deshabilitar la eliminación"
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Deshabilitar las operaciones de agregar y eliminar elementos DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

De forma predeterminada, los usuarios pueden agregar y eliminar elementos en un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Los usuarios pueden agregar un nuevo elemento presionando CTRL\+N cuando <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> tiene el foco o haciendo clic en el botón **AddNewItem** del control <xref:System.Windows.Forms.BindingNavigator>.  Los usuarios pueden eliminar un elemento presionando SUPRIMIR cuando <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> tiene el foco o haciendo clic en el botón **DeleteItem** del control <xref:System.Windows.Forms.BindingNavigator>.  
  
 Puede deshabilitar las operaciones de agregar y eliminar en tiempo de diseño o en tiempo de ejecución.  
  
### Para deshabilitar las operaciones de agregar y eliminar en tiempo de diseño  
  
1.  En el Diseñador de Windows Forms, seleccione el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
    > [!NOTE]
    >  Debe seleccionar la sección inferior del control.  Si selecciona la sección de plantilla de elemento, se mostrará un conjunto de propiedades distinto.  
  
2.  En la ventana Propiedades, establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> en **False**.  
  
3.  Establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> en **False**.  
  
4.  En el Diseñador de Windows Forms, seleccione el control <xref:System.Windows.Forms.BindingNavigator> y, a continuación, haga clic en el botón **AddNewItem** \(el botón con un signo más en él\).  
  
5.  En la ventana Propiedades, establezca la propiedad <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> en **False**.  
  
6.  En el Diseñador de Windows Forms, seleccione el control <xref:System.Windows.Forms.BindingNavigator> y, a continuación, haga clic en el botón **DeleteItem** \(el botón con una X roja en él\).  
  
7.  En la ventana Propiedades, establezca la propiedad <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> en **False**.  
  
8.  En la Bandeja de componentes, seleccione el <xref:System.Windows.Forms.BindingSource> al que está enlazado <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
9. En la ventana Propiedades, establezca la propiedad <xref:System.Windows.Forms.BindingSource.AllowNew%2A> en **False**.  
  
10. En el Diseñador de Windows Forms, haga doble clic en el botón **DeleteItem** para abrir el Editor de código.  
  
11. En la lista desplegable de eventos, seleccione el evento `BindingNavigatorDeleteItem_EnabledChanged`.  
  
12. Agregue el código siguiente al controlador de eventos `BindingNavigatorDeleteItem_EnabledChanged`:  
  
     [!code-cs[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Se trata de un paso necesario porque el componente <xref:System.Windows.Forms.BindingSource> habilitará el botón **DeleteItem** cada vez que cambie el registro actual.  
  
### Para deshabilitar las operaciones de agregar y eliminar en tiempo de ejecución  
  
1.  En el Diseñador de Windows Forms, haga doble clic en el formulario para abrir el Editor de código.  
  
2.  Agregue el código siguiente al evento `Form_Load`:  
  
     [!code-cs[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  Agregue el código siguiente al controlador de eventos `BindingNavigatorDeleteItem_EnabledChanged`:  
  
     [!code-cs[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Se trata de un paso necesario porque el componente <xref:System.Windows.Forms.BindingSource> habilitará el botón **DeleteItem** cada vez que cambie el registro actual.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)