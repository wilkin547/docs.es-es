---
title: "C&#243;mo: Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], enlazar varios"
  - "controles [Windows Forms], sincronizar con origen de datos"
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados
A menudo, al trabajar con el enlace de datos en formularios Windows Forms, se enlazan varios controles al mismo origen de datos.  En algunos casos, puede ser necesario adoptar medidas adicionales para garantizar que las propiedades enlazadas de los controles permanezcan sincronizadas entre sí y con el origen de datos.  Estas medidas son necesarias en dos situaciones:  
  
-   Si el origen de datos no implementa <xref:System.ComponentModel.IBindingList> y, por consiguiente, genera eventos <xref:System.ComponentModel.IBindingList.ListChanged> de tipo <xref:System.ComponentModel.ListChangedType>.  
  
-   Si el origen de datos implementa <xref:System.ComponentModel.IEditableObject>.  
  
 En el primer caso, puede utilizar un objeto <xref:System.Windows.Forms.BindingSource> para enlazar el origen de datos a los controles.  En el segundo caso, se utiliza un objeto <xref:System.Windows.Forms.BindingSource>, se controla el evento <xref:System.Windows.Forms.BindingSource.BindingComplete> y se llama al método <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> en el objeto <xref:System.Windows.Forms.BindingManagerBase> asociado.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo enlazar tres controles \(dos controles de cuadro de texto y un control <xref:System.Windows.Forms.DataGridView>\) a la misma columna de un <xref:System.Data.DataSet> mediante un componente <xref:System.Windows.Forms.BindingSource>.  En este ejemplo se muestra cómo controlar el evento <xref:System.Windows.Forms.BindingSource.BindingComplete> y garantizar que, cuando cambie el valor de texto de uno de los cuadros de texto, se actualicen con el valor correcto el otro cuadro de texto y el control <xref:System.Windows.Forms.DataGridView>.  
  
 En el ejemplo se utiliza un <xref:System.Windows.Forms.BindingSource> para enlazar el origen de datos y los controles.  Asimismo, se puede enlazar directamente los controles al origen de datos y recuperar un objeto <xref:System.Windows.Forms.BindingManagerBase> para el enlace del <xref:System.Windows.Forms.Control.BindingContext%2A> del formulario y, a continuación, controlar el evento <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> correspondiente al objeto <xref:System.Windows.Forms.BindingManagerBase>.  Para obtener un ejemplo de cómo hacerlo, vea la página de Ayuda correspondiente al evento <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> de <xref:System.Windows.Forms.BindingManagerBase>.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## Compilar el código  
  
-   Este ejemplo de código requiere  
  
-   Referencias a los ensamblados <xref:System>, <xref:System.Windows.Forms> y <xref:System.Drawing>.  
  
-   Un formulario con el evento <xref:System.Windows.Forms.Form.Load> controlado y una llamada al método `InitializeControlsAndDataSource` en el ejemplo del controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario.  
  
## Vea también  
 [Cómo: Compartir datos enlazados entre formularios mediante el componente BindingSource](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)   
 [Notificación de cambios en el enlace de datos de Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Interfaces relacionadas con el enlace de datos](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)   
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)