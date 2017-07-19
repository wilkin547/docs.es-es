---
title: "C&#243;mo: Obtener acceso a objetos de una lista desplegable DataGridViewComboBoxCell en Windows Forms | Microsoft Docs"
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
  - "cuadros combinados, obtener acceso a objetos en listas desplegables DataGridViewComboBoxCell"
  - "cuadros combinados, en el control DataGridView"
  - "DataGridView (control) [Windows Forms], obtener acceso a objetos en celdas de cuadros combinados"
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Obtener acceso a objetos de una lista desplegable DataGridViewComboBoxCell en Windows Forms
Como sucede con el control <xref:System.Windows.Forms.ComboBox>, los tipos <xref:System.Windows.Forms.DataGridViewComboBoxColumn> y <xref:System.Windows.Forms.DataGridViewComboBoxCell> permiten agregar objetos arbitrarios a las listas desplegables.  Con esta característica, puede representar estados complejos en una lista desplegable sin tener que almacenar los objetos correspondientes en una colección independiente.  
  
 A diferencia del control <xref:System.Windows.Forms.ComboBox>, los tipos <xref:System.Windows.Forms.DataGridView> no tienen una propiedad <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> para recuperar el objeto actualmente seleccionado.  En su lugar, se debe establecer la propiedad <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=fullName> o <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=fullName> en el nombre de una propiedad del objeto comercial.  Cuando el usuario realiza una selección, la propiedad indicada del objeto comercial establece la propiedad <xref:System.Windows.Forms.DataGridViewCell.Value%2A> de la celda.  
  
 Para recuperar el objeto comercial a través del valor de la celda, la propiedad `ValueMember` debe indicar una propiedad que devuelva una referencia al propio objeto comercial.  Por consiguiente, si el tipo del objeto comercial no está bajo su control, debe agregar esta propiedad extendiendo el tipo a través de herencia.  
  
 Los procedimientos siguientes muestran cómo rellenar una lista desplegable con objetos comerciales y cómo recuperar los objetos a través de la propiedad <xref:System.Windows.Forms.DataGridViewCell.Value%2A> de la celda.  
  
### Para agregar objetos comerciales a la lista desplegable  
  
1.  Cree un nuevo objeto <xref:System.Windows.Forms.DataGridViewComboBoxColumn> y rellene la colección <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>.  Alternativamente, puede establecer la propiedad <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> de la columna en la colección de objetos comerciales.  Sin embargo, en ese caso no puede agregar "unassigned" a la lista desplegable sin crear el objeto comercial correspondiente en su colección.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2.  Establezca las propiedades <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> y <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>.  <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indica la propiedad del objeto comercial que se va a mostrar en la lista desplegable.  <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indica la propiedad que devuelve una referencia al objeto comercial.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3.  Asegúrese de que el tipo de objeto comercial contenga una propiedad que devuelva una referencia a la instancia actual.  Esta propiedad debe llevar el nombre del valor asignado a <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> en el paso anterior.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### Para recuperar el objeto comercial actualmente seleccionado  
  
-   Obtenga la propiedad <xref:System.Windows.Forms.DataGridViewCell.Value%2A> de la celda y conviértala en el tipo del objeto comercial.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## Ejemplo  
 El ejemplo completo muestra el uso de objetos comerciales en una lista desplegable.  En el ejemplo, un control <xref:System.Windows.Forms.DataGridView> se encuentra enlazado a una colección de objetos `Task`.  Cada objeto `Task` tiene una propiedad `AssignedTo` que indica el objeto `Employee` actualmente asignado a esa tarea.  La columna `Assigned To` muestra el valor de propiedad `Name` para cada empleado asignado, o "unassigned" si el valor de propiedad `Task.AssignedTo` es `null`.  
  
 Para ver el comportamiento de este ejemplo, realice los pasos siguientes:  
  
1.  Cambie las asignaciones de la columna `Assigned To`; para ello, seleccione otros valores en las listas desplegables o presione CTRL\+0 en una celda de cuadro combinado.  
  
2.  Haga clic en `Generate Report` para mostrar las asignaciones actuales.  Esto demuestra que un cambio en la columna `Assigned To` actualiza automáticamente la colección `tasks`.  
  
3.  Haga clic en un botón `Request Status` para llamar al método `RequestStatus` del objeto `Employee` actual para esa fila.  Esto demuestra cómo el objeto seleccionado se recupera correctamente.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ComboBox>   
 [Mostrar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)