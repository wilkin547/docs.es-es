---
title: "Cómo: Deshabilitar las operaciones de agregar y eliminar elementos DataRepeater (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, disabling delete
- DataRepeater, disabling add
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b15fe6fb5190855126ffa60ac488aaa74ad9b5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a>Cómo: Deshabilitar las operaciones de agregar y eliminar elementos DataRepeater (Visual Studio)
De forma predeterminada, los usuarios pueden agregar y eliminar elementos en una <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Los usuarios pueden agregar un nuevo elemento presionando CTRL+N cuando un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> tiene el foco o haciendo clic en el **AddNewItem** situado en el <xref:System.Windows.Forms.BindingNavigator> control. Los usuarios pueden eliminar un elemento presionando eliminar cuando un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> tiene el foco o haciendo clic en el **DeleteItem** situado en el <xref:System.Windows.Forms.BindingNavigator> control.  
  
 Puede deshabilitar la adición o eliminación en tiempo de diseño o en tiempo de ejecución.  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a>Para deshabilitar la adición y eliminación en tiempo de diseño  
  
1.  En el Diseñador de Windows Forms, seleccione el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
    > [!NOTE]
    >  Debe seleccionar la sección inferior del control. Si selecciona la sección de la plantilla de elemento, se mostrará un conjunto diferente de propiedades.  
  
2.  En la ventana Propiedades, establezca la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> propiedad **False**.  
  
3.  Establecer el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> propiedad **False**.  
  
4.  En el Diseñador de Windows Forms, seleccione la <xref:System.Windows.Forms.BindingNavigator> de control y, a continuación, haga clic en el **AddNewItem** botón (el botón con un signo más en él).  
  
5.  En la ventana Propiedades, establezca la <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> propiedad **False**.  
  
6.  En el Diseñador de Windows Forms, seleccione la <xref:System.Windows.Forms.BindingNavigator> de control y, a continuación, haga clic en el **DeleteItem** botón (el botón con una X roja en él).  
  
7.  En la ventana Propiedades, establezca la <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> propiedad **False**.  
  
8.  En la Bandeja de componentes, seleccione la <xref:System.Windows.Forms.BindingSource> a la que el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> está enlazado.  
  
9. En la ventana Propiedades, establezca la <xref:System.Windows.Forms.BindingSource.AllowNew%2A> propiedad **False**.  
  
10. En el Diseñador de Windows Forms, haga doble clic en el **DeleteItem** botón para abrir el Editor de código.  
  
11. En la lista desplegable de eventos, seleccione el `BindingNavigatorDeleteItem_EnabledChanged` eventos.  
  
12. Agregue el código siguiente al controlador de eventos `BindingNavigatorDeleteItem_EnabledChanged` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Este paso es necesario porque <xref:System.Windows.Forms.BindingSource> habilitará el botón **DeleteItem** cada vez que cambie el registro actual.  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a>Para deshabilitar la adición y eliminación en tiempo de ejecución  
  
1.  En el Diseñador de Windows Forms, haga doble clic en el formulario para abrir el Editor de código.  
  
2.  Agregue el código siguiente al evento `Form_Load` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  Agregue el código siguiente al controlador de eventos `BindingNavigatorDeleteItem_EnabledChanged` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Este paso es necesario porque <xref:System.Windows.Forms.BindingSource> habilitará el botón **DeleteItem** cada vez que cambie el registro actual.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
