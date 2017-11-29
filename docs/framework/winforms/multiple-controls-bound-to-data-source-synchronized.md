---
title: "Cómo: Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2573f342530e59fa05e7f24342f251990b2ce47d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>Cómo: Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados
A menudo, cuando se trabaja con enlace de datos en formularios Windows Forms, varios controles están enlazados al mismo origen de datos. En algunos casos, puede ser necesario realizar pasos adicionales para asegurarse de que las propiedades de los controles enlazadas sigan estando sincronizadas con entre sí y el origen de datos. Estos pasos son necesarios en dos situaciones:  
  
-   Si el origen de datos no implementa <xref:System.ComponentModel.IBindingList>y, por tanto, generar <xref:System.ComponentModel.IBindingList.ListChanged> eventos de tipo <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
-   Si el origen de datos implementa <xref:System.ComponentModel.IEditableObject>.  
  
 En el primer caso, puede usar un <xref:System.Windows.Forms.BindingSource> para enlazar el origen de datos a los controles. En este último caso, se utiliza un <xref:System.Windows.Forms.BindingSource> y controlar la <xref:System.Windows.Forms.BindingSource.BindingComplete> eventos y llame al método <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> en asociado <xref:System.Windows.Forms.BindingManagerBase>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo enlazar tres controles: dos controles de cuadro de texto y un <xref:System.Windows.Forms.DataGridView> control: en la misma columna de un <xref:System.Data.DataSet> mediante un <xref:System.Windows.Forms.BindingSource> componente. Este ejemplo muestra cómo controlar la <xref:System.Windows.Forms.BindingSource.BindingComplete> eventos y asegúrese de que cuando se cambia el valor de texto de un cuadro de texto, el cuadro de texto adicionales y el <xref:System.Windows.Forms.DataGridView> control se actualizan con el valor correcto.  
  
 El ejemplo se usa un <xref:System.Windows.Forms.BindingSource> para enlazar el origen de datos y los controles. Como alternativa, puede enlazar los controles directamente al origen de datos y recuperar el <xref:System.Windows.Forms.BindingManagerBase> para el enlace desde el formulario <xref:System.Windows.Forms.Control.BindingContext%2A> y, a continuación, controlar el <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> eventos para el <xref:System.Windows.Forms.BindingManagerBase>. Para obtener un ejemplo de cómo hacerlo, consulte la página de ayuda la <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> eventos de <xref:System.Windows.Forms.BindingManagerBase>.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Este ejemplo de código se necesita  
  
-   Referencias a los ensamblados <xref:System>, <xref:System.Windows.Forms> y <xref:System.Drawing>.  
  
-   Un formulario con el <xref:System.Windows.Forms.Form.Load> evento como controlado y una llamada a la `InitializeControlsAndDataSource` método en el ejemplo de la forma <xref:System.Windows.Forms.Form.Load> controlador de eventos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Compartir datos enlazados entre formularios mediante el componente BindingSource](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 [Notificación de cambios en el enlace de datos de Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Interfaces relacionadas con el enlace de datos](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)
