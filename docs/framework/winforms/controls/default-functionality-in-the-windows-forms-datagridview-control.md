---
title: "Funcionalidad predeterminada en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, funcionalidad predeterminada en el control DataGridView"
  - "DataGridView (control) [Windows Forms], funcionalidad predeterminada"
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Funcionalidad predeterminada en el control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> de formularios Windows Forms proporciona a los usuarios gran cantidad de funciones predeterminadas.  
  
## Funcionalidad predeterminada  
 De manera predeterminada, un control <xref:System.Windows.Forms.DataGridView>:  
  
-   Muestra automáticamente encabezados de columna y de fila que permanecen visibles cuando se recorre la tabla verticalmente.  
  
-   Tiene un encabezado de fila que contiene un indicador de selección para la fila actual.  
  
-   Tiene un rectángulo de selección en la primera celda.  
  
-   Tiene columnas cuyo tamaño se puede cambiar automáticamente si el usuario hace doble clic en los divisores de columnas.  
  
-   Admite automáticamente estilos visuales en Windows XP y la familia de servidores de Windows Server 2003 cuando se llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> desde el método `Main` de la aplicación.  
  
 Además, se puede editar el contenido de un control <xref:System.Windows.Forms.DataGridView> de manera predeterminada:  
  
-   Si el usuario hace doble clic o presiona F2 en una celda, el control aplica automáticamente a la celda el modo de edición y actualiza el contenido de la celda conforme teclea el usuario.  
  
-   Si el usuario se desplaza al final de la cuadrícula, verá que hay una fila para agregar registros nuevos.  Cuando el usuario hace clic en esta fila, se agrega una nueva fila al control <xref:System.Windows.Forms.DataGridView>, con valores predeterminados.  Cuando el usuario presiona ESC, esta nueva fila desaparece.  
  
-   Si el usuario hace clic en el encabezado de una fila, se selecciona la fila completa.  
  
 Cuando se enlaza un control <xref:System.Windows.Forms.DataGridView> a un origen de datos estableciendo su propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A>, el control:  
  
-   Utiliza automáticamente los nombres de las columnas del origen de datos como texto de los encabezados de columna.  
  
-   Se rellena con el contenido del origen de datos.  Las columnas <xref:System.Windows.Forms.DataGridView> se crean automáticamente para cada columna en el origen de datos.  
  
-   Crea una fila para cada fila visible de la tabla.  
  
-   Ordena automáticamente las filas tomando como base los datos subyacentes cuando el usuario hace clic en el encabezado de una columna.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 [Control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)