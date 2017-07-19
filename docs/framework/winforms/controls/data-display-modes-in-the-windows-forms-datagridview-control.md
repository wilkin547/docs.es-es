---
title: "Modos de presentaci&#243;n de datos en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "datos [Windows Forms], modos de presentación"
  - "cuadrículas de datos, modos de presentación"
  - "DataGridView (control) [Windows Forms], modos de presentación"
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Modos de presentaci&#243;n de datos en el control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> puede mostrar los datos en tres modos distintos: de enlace, sin enlazar y virtual.  Elija el modo más adecuado en función de sus necesidades.  
  
## Sin enlazar  
 El modo sin enlazar es adecuado para mostrar cantidades relativamente pequeñas de datos que se pueden administrar mediante programación.  No asocie directamente el control <xref:System.Windows.Forms.DataGridView> a un origen de datos como en modo de enlace.  En su lugar, debe rellenar el control, utilizando normalmente el método <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=fullName>.  
  
 El modo sin enlazar puede ser particularmente útil para datos estáticos y de sólo lectura, o cuando desea proporcionar su propio código que interactúe con un almacén de datos externo.  Sin embargo, si desea que los usuarios interactúen con un origen de datos externo, utilice el modo de enlace.  
  
 Para obtener un ejemplo que utiliza un <xref:System.Windows.Forms.DataGridView> sin enlazar y de sólo lectura, vea [Cómo: Crear un control DataGridView no enlazado en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## De enlace  
 El modo de enlace es adecuado para administrar datos mediante la interacción automática con el almacén de datos.  Puede asociar directamente el control <xref:System.Windows.Forms.DataGridView> a su origen de datos estableciendo la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A>.  Cuando el control está enlazado a datos, se insertan y se extraen las filas de datos sin la necesidad de una administración explícita por su parte.  Cuando la propiedad <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> es `true`, cada columna del origen de datos producirá una columna correspondiente que se creará en el control.  Si prefiere crear sus propias columnas, puede establecer esta propiedad en `false` y utilizar la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> para enlazar cada columna cuando la configure.  Esto resulta muy útil cuando desea utilizar un tipo de columna distinto de los tipos que se generan de forma predeterminada.  Para obtener más información, vea [Tipos de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).  
  
 Para obtener un ejemplo que utiliza un control <xref:System.Windows.Forms.DataGridView> enlazado, vea [Tutorial: Validar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 También puede agregar las columnas sin enlazar a un control <xref:System.Windows.Forms.DataGridView> en modo de enlace.  Esto resulta útil cuando desea mostrar una columna de botones o vínculos que permiten a los usuarios realizar acciones en filas determinadas.  También resulta útil para mostrar columnas con valores calculados de las columnas enlazadas.  Puede rellenar los valores de celda para las columnas calculadas en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting>.  Sin embargo, si está utilizando un <xref:System.Data.DataSet> o <xref:System.Data.DataTable> como origen de datos, podría desear utilizar la propiedad <xref:System.Data.DataColumn.Expression%2A?displayProperty=fullName> para crear en su lugar una columna calculada.  En este caso, el control <xref:System.Windows.Forms.DataGridView> tratará la columna calculada como cualquier otra columna del origen de datos.  
  
 En modo de enlace no se admite la ordenación por columnas sin enlazar.  Si crea una columna sin enlazar en modo de enlace que contiene valores que puede modificar el usuario, debe implementar el modo virtual para conservar estos valores cuando el control se ordena por una columna enlazada.  
  
## Virtual  
 Con el modo virtual, puede implementar sus propias operaciones de administración de datos.  Esto es necesario para conservar los valores de las columnas sin enlazar en modo de enlace cuando las columnas enlazadas ordenan el control.  Sin embargo, el uso principal del modo virtual es optimizar el rendimiento al interactuar con cantidades grandes de datos.  
  
 Asocie el control <xref:System.Windows.Forms.DataGridView> a una caché que administre y el código controla cuando se insertan y se extraen las filas de datos.  Para que la huella de la memoria sea pequeña, la caché debería ser similar en tamaño al número de filas mostrado.  Cuando el usuario desplaza las nuevas filas a la vista, el código solicita los nuevos datos de la caché y opcionalmente vacía los datos antiguos de la memoria.  
  
 Si está implementando el modo virtual, necesitará saber si se necesita una nueva fila en el modelo de datos y si hay que revertir la adición de la nueva fila.  La implementación exacta de esta funcionalidad depende de la implementación del modelo de datos y de la semántica de la transacción del modelo de datos; por ejemplo, si el ámbito de confirmación se encuentra en el nivel de la celda o de la fila.  
  
 Para obtener más información sobre el modo virtual, vea [Modo virtual del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  Para obtener un ejemplo que muestra cómo utilizar los eventos de modo virtual, vea [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=fullName>   
 [Mostrar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Tipos de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)   
 [Cómo: Enlazar datos al control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)   
 [Modo virtual del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)