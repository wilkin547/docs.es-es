---
title: "Cómo: Crear una interfaz similar a la del Explorador de Windows en Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 96f2ca8189d6840bc68f063ef9b97539c24b0e6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>Cómo: Crear una interfaz similar a la del Explorador de Windows en Windows Forms
El Explorador de Windows es una opción de interfaz de usuario común para aplicaciones debido a su familiaridad inmediata.  
  
 El Explorador de Windows es, básicamente, un <xref:System.Windows.Forms.TreeView> control y un <xref:System.Windows.Forms.ListView> control en paneles independientes. Los paneles se realizan puede cambiar por un divisor. Esta disposición de controles es muy eficaz para mostrar y explorar información.  
  
 Los pasos siguientes muestran cómo organizar los controles en un formulario similar al explorador de Windows. No muestra cómo agregar la funcionalidad de exploración de archivos de la aplicación de explorador de Windows.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a>Para crear un formulario de Windows de estilo Explorador de Windows  
  
1.  Crear un nuevo proyecto de aplicación de Windows. Para ver detalles, consulte [Cómo: Crear un nuevo proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Desde el **cuadro de herramientas**:  
  
    1.  Arrastre un <xref:System.Windows.Forms.SplitContainer> control al formulario.  
  
    2.  Arrastre un <xref:System.Windows.Forms.TreeView> controlar en **SplitterPanel1** (el panel de la <xref:System.Windows.Forms.SplitContainer> los controles marcados como **Panel1**).  
  
    3.  Arrastre un <xref:System.Windows.Forms.ListView> controlar en **SplitterPanel2** (el panel de la <xref:System.Windows.Forms.SplitContainer> los controles marcados como **Panel2**).  
  
3.  Seleccione los tres controles presionando la tecla CTRL y haciendo clic a su vez. Cuando se selecciona el <xref:System.Windows.Forms.SplitContainer> de control, haga clic en la barra de división, en lugar de los paneles.  
  
    > [!NOTE]
    >  No utilice la **seleccionar todo** comando el **editar** menú. Si lo hace, la propiedad necesaria en el paso siguiente no aparecerá en la **propiedades** ventana.  
  
4.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.  
  
5.  Presione F5 para ejecutar la aplicación.  
  
     El formulario muestra una interfaz de usuario de dos partes, similar a la que el Explorador de Windows.  
  
    > [!NOTE]
    >  Cuando se arrastra el divisor, los paneles de tamaño.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.SplitContainer>  
 [Crear una interfaz de usuario de varios paneles con Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [Definir el comportamiento de cambio de tamaño y colocación de una ventana dividida](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [Dividir una ventana horizontalmente](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [SplitContainer (control)](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
