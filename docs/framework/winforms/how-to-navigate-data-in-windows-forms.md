---
title: "C&#243;mo: Desplazarse por datos en formularios Windows Forms | Microsoft Docs"
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
  - "CurrencyManager (clase), explorar datos en formularios Windows Forms"
  - "cursores, orígenes de datos"
  - "datos [Windows Forms], navegar"
  - "orígenes de datos, Windows Forms"
  - "Windows Forms, navegar"
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Desplazarse por datos en formularios Windows Forms
En una aplicación para Windows, el modo más sencillo de navegar por los registros de un origen de datos es enlazar un componente <xref:System.Windows.Forms.BindingSource> al origen de datos y luego enlazar controles a <xref:System.Windows.Forms.BindingSource>.  Puede utilizar a continuación el método de navegación integrado en  <xref:System.Windows.Forms.BindingSource> como un método: <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> y <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.  Al utilizar estos métodos, se ajustarán adecuadamente las propiedades <xref:System.Windows.Forms.BindingSource.Position%2A> y <xref:System.Windows.Forms.BindingSource.Current%2A> de <xref:System.Windows.Forms.BindingSource>.  También puede encontrar un elemento y establecerlo como el elemento actual definiendo la propiedad <xref:System.Windows.Forms.BindingSource.Position%2A>.  
  
### Para incrementar la posición en un origen de datos  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.BindingSource.Position%2A> del objeto <xref:System.Windows.Forms.BindingSource> correspondiente a los datos enlazados en la posición de registro a la que desea ir.  En el ejemplo siguiente se muestra cómo utilizar el método <xref:System.Windows.Forms.BindingSource.MoveNext%2A> de <xref:System.Windows.Forms.BindingSource> para incrementar la propiedad <xref:System.Windows.Forms.BindingSource.Position%2A> cuando se hace clic en `nextButton`.  <xref:System.Windows.Forms.BindingSource> está asociado a la tabla `Customers` de un conjunto de datos `Northwind`.  
  
    > [!NOTE]
    >  Si se establece la propiedad <xref:System.Windows.Forms.BindingSource.Position%2A> en un valor más allá del primer o último registro, no se produce un error, puesto que [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] no permitirá que se establezca la posición en un valor que esté fuera de los límites de la lista.  Si es importante para la aplicación saber si se fue más allá del primer o el último registro, incluya lógica que compruebe si se superó la cuenta de elementos de datos.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### Para comprobar si se fue más allá del principio o del final  
  
1.  Cree un controlador de eventos para el evento <xref:System.Windows.Forms.BindingSource.PositionChanged>.  En el controlador, puede comprobar si el valor de la posición propuesta supera la cuenta real de elementos de datos.  
  
     En el ejemplo siguiente se ilustra cómo comprobar si se alcanzó el último elemento de datos.  En el ejemplo, si se encuentra en el último elemento, el botón **Next** \(Siguiente\) del formulario se deshabilita.  
  
    > [!NOTE]
    >  Tenga en cuenta que, en caso de cambiar la lista por la que se está navegando mediante código, deberá volver a habilitar el botón **Siguiente**, de modo que los usuarios puedan examinar toda la lista nueva.  Además, tenga en cuenta que el evento <xref:System.Windows.Forms.BindingSource.PositionChanged> anterior para el <xref:System.Windows.Forms.BindingSource> concreto con el que se está trabajando debe estar asociado a su método de control de eventos.  A continuación figura un ejemplo de un método para controlar el evento <xref:System.Windows.Forms.BindingSource.PositionChanged>:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### Para encontrar un elemento y establecerlo como el elemento actual  
  
1.  Encuentre el registro que desea establecer como el elemento actual.  Puede hacer esto utilizando el método <xref:System.Windows.Forms.BindingSource.Find%2A> de <xref:System.Windows.Forms.BindingSource>, si el origen de datos implementa <xref:System.ComponentModel.IBindingList>.  Algunos ejemplos de orígenes de datos que implementan <xref:System.ComponentModel.IBindingList> son <xref:System.ComponentModel.BindingList%601> y <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## Vea también  
 [Orígenes de datos compatibles con formularios Windows Forms](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)   
 [Notificación de cambios en el enlace de datos de Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Enlace de datos y formularios Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)