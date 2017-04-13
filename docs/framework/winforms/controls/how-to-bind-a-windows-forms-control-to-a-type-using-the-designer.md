---
title: "C&#243;mo: Enlazar un control de formularios Windows Forms a un tipo mediante el Dise&#241;ador | Microsoft Docs"
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
  - "BindingSource (componente) [Windows Forms], enlazar a un tipo"
  - "controles [Windows Forms], enlazar a un tipo"
  - "tipos [formularios Windows Forms], enlazar controles"
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Enlazar un control de formularios Windows Forms a un tipo mediante el Dise&#241;ador
Al crear controles que interactúan con datos, a veces necesitará enlazar un control a un tipo mejor que a un objeto.  Normalmente tendrá que enlazar un control a un tipo en tiempo de diseño, cuando quizá no estén disponibles los datos, pero aún desea que los controles enlazados a datos muestren datos de una interfaz pública del tipo.  En los procedimientos siguientes se muestra cómo crear un nuevo <xref:System.Windows.Forms.BindingSource> que está enlazado a un tipo y a continuación cómo enlazar una de las propiedades del tipo a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> del control  <xref:System.Windows.Forms.TextBox>.  
  
### Para enlazar BindingSource a un tipo  
  
1.  Cree un proyecto de formularios Windows Forms.  
  
     Para obtener más información, consulte [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  En la vista **Diseño**, arrastre un componente <xref:System.Windows.Forms.BindingSource> al formulario.  
  
3.  En la ventana **Propiedades**, haga clic en la flecha correspondiente a la propiedad <xref:System.Windows.Forms.BindingSource.DataSource%2A>.  
  
4.  En el **Editor de tipos de la interfaz de usuario de orígenes de datos**, haga clic en **Agregar origen de datos de proyecto**.  
  
5.  En la página **Elegir un tipo de origen de datos**, seleccione **Objeto** y, a continuación, haga clic en **Siguiente**.  
  
6.  Seleccione el tipo al que desea enlazarlo:  
  
    -   Si el tipo al que desea enlazarlo se encuentra en el proyecto actual o el ensamblado que contiene el tipo ya se ha agregado de referencia, expanda los nodos para encontrar el tipo que desee y a continuación selecciónelo.  
  
         O bien  
  
    -   Si el tipo al que desea enlazarlo se encuentra en otro ensamblado, no actualmente en la lista de referencias, haga clic en **Agregar referencia** y, a continuación, haga clic en la ficha **Proyectos**.  Seleccione el proyecto que contiene el objeto comercial que desea y haga clic en **Aceptar**.  Aparecerá el proyecto en la lista de ensamblados, de manera que puede expandir los nodos para encontrar el tipo que desee y, a continuación, seleccionarlo.  
  
        > [!NOTE]
        >  Si desea enlazarlo a un tipo de un Framework o un ensamblado de Microsoft, desactive la casilla **Ocultar los ensamblados que empiecen por Microsoft o sistema**.  
  
7.  Haga clic en **Siguiente** y, a continuación, en **Finalizar**.  
  
### Para enlazar el control al BindingSource  
  
1.  Agregue un control <xref:System.Windows.Forms.TextBox> al formulario.  
  
2.  En la ventana **Propiedades**, expanda el nodo **\(DataBindings\)**.  
  
3.  Haga clic en la flecha que se encuentra junto a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.  
  
4.  En el **Editor de tipos de la interfaz de usuario de orígenes de datos** expanda el nodo del <xref:System.Windows.Forms.BindingSource> agregado previamente y seleccione la propiedad del tipo enlazado que desea enlazar a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> del control <xref:System.Windows.Forms.TextBox>.  
  
## Vea también  
 [BindingSource \(Componente\)](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Cómo: Enlazar un control de Windows Forms a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)   
 [Enlazar controles a los datos en Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md)