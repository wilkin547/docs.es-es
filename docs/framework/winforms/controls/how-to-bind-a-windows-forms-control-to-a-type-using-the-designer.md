---
title: "Cómo: Enlazar un control de formularios Windows Forms a un tipo mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee932e7cb4a3333ac56242e281ec64d3016746f9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Cómo: Enlazar un control de formularios Windows Forms a un tipo mediante el Diseñador
Al crear controles que interactúan con datos, a veces necesita enlazar un control a un tipo, en lugar de a un objeto. Normalmente necesita enlazar un control a un tipo en tiempo de diseño, cuando quizá no estén disponibles los datos, pero aún desea que los controles enlazados a datos muestren datos de una interfaz pública del tipo. Los procedimientos siguientes muestran cómo crear un nuevo <xref:System.Windows.Forms.BindingSource> decir enlazado a un tipo y, a continuación, cómo enlazar una de las propiedades del tipo para el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad de un <xref:System.Windows.Forms.TextBox>.  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a>Para enlazar BindingSource a un tipo  
  
1.  Cree un proyecto de Windows Forms.  
  
     Para más información, consulte [Cómo: Crear un proyecto de aplicación para Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  En **diseño** ver, arrastre un <xref:System.Windows.Forms.BindingSource> componente al formulario.  
  
3.  En el **propiedades** ventana, haga clic en la flecha de la <xref:System.Windows.Forms.BindingSource.DataSource%2A> propiedad.  
  
4.  En el **Editor de tipos de la interfaz de usuario de orígenes de datos**, haga clic en **Agregar origen de datos del proyecto**.  
  
5.  En la página **Elegir un tipo de origen de datos**, seleccione **Objeto** y haga clic en **Siguiente**.  
  
6.  Seleccione el tipo al que desea enlazarlo:  
  
    -   Si el tipo al que desea enlazarlo se encuentra en el proyecto actual o el ensamblado que contiene el tipo ya se ha agregado como una referencia, expanda los nodos para encontrar el tipo que desee y a continuación selecciónelo.  
  
         O bien  
  
    -   Si el tipo al que desea enlazarlo se encuentra en otro ensamblado, no actualmente en la lista de referencias, haga clic en **Agregar referencia** y después haga clic en la pestaña **Proyectos**. Seleccione el proyecto que contiene el objeto comercial que desea y haga clic en **Aceptar**. Este proyecto aparecerá en la lista de ensamblados, por lo que puede expandir los nodos para encontrar el tipo desee y, a continuación, seleccionarlo.  
  
        > [!NOTE]
        >  Si desea enlazar a un tipo de un marco o un ensamblado de Microsoft, desactive la casilla **Ocultar los ensamblados que empiecen por Microsoft o sistema**.  
  
7.  Haga clic en **Siguiente** y después haga clic en **Finalizar**.  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a>Para enlazar el control a BindingSource  
  
1.  Agregue un control <xref:System.Windows.Forms.TextBox> al formulario.  
  
2.  En la ventana **Propiedades**, expanda el nodo **(DataBindings)**.  
  
3.  Haga clic en la flecha situada junto a la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad.  
  
4.  En el **Editor de tipos de interfaz de usuario de origen de datos**, expanda el nodo de la <xref:System.Windows.Forms.BindingSource> agregó anteriormente y seleccione la propiedad del tipo enlazado que desea enlazar el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad de la <xref:System.Windows.Forms.TextBox>.  
  
## <a name="see-also"></a>Vea también  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Cómo: Enlazar un control de Windows Forms a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
