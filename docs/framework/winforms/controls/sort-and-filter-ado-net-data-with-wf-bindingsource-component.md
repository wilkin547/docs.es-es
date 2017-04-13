---
title: "C&#243;mo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de formularios Windows Forms | Microsoft Docs"
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
  - "ADO.NET [Windows Forms]"
  - "BindingSource (componente) [Windows Forms], ordenar y filtrar datos"
  - "datos [Windows Forms], filtrar"
  - "datos [Windows Forms], ordenar"
  - "ordenación de datos, ADO.NET"
  - "filtrar [Windows Forms], ADO.NET"
  - "ordenar datos"
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de formularios Windows Forms
Puede exponer la función de ordenación y filtrado del control <xref:System.Windows.Forms.BindingSource> a través de las propiedades <xref:System.Windows.Forms.BindingSource.Sort%2A> y <xref:System.Windows.Forms.BindingSource.Filter%2A>.  Puede aplicar la ordenación simple si el origen de datos subyacente es una <xref:System.ComponentModel.IBindingList>, y puede aplicar la ordenación y el filtrado avanzados si el origen de datos es una <xref:System.ComponentModel.IBindingListView>.  La propiedad <xref:System.Windows.Forms.BindingSource.Sort%2A> requiere una sintaxis de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] estándar: una cadena representa el nombre de una columna de datos del origen de datos seguida de `ASC` o de `DESC` para indicar si la lista debe ordenarse en orden ascendente o descendente.  Puede establecer una ordenación avanzada o de múltiples columnas separando cada columna con un separador de coma.  La propiedad <xref:System.Windows.Forms.BindingSource.Filter%2A> toma una expresión de cadena.  
  
> [!NOTE]
>  El hecho de almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.  El uso de la autenticación de Windows \(también conocida como seguridad integrada\) es un modo más seguro de controlar el acceso a una base de datos.  Para obtener más información, vea [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
### Para filtrar los datos con BindingSource  
  
-   Establezca la propiedad <xref:System.Windows.Forms.BindingSource.Filter%2A> en la expresión que desee.  
  
     En el ejemplo de código siguiente, la expresión es un nombre de columna seguido del valor que desea para la columna.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### Para ordenar los datos con BindingSource  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.BindingSource.Sort%2A> en el nombre de columna que desee seguido de `ASC` o `DESC` para indicar el orden ascendente o descendente.  
  
2.  Separe varias columnas con una coma.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## Ejemplo  
 El siguiente ejemplo de código carga los datos de la tabla Customers de la base de datos de ejemplo Northwind dentro de un control <xref:System.Windows.Forms.DataGridView> y filtra y ordena los datos mostrados.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## Compilar el código  
 Para ejecutar este ejemplo, pegue el siguiente código en un formulario que contiene un objeto <xref:System.Windows.Forms.BindingSource> denominado `BindingSource1` y un <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  Controle el evento <xref:System.Windows.Forms.Form.Load> del formulario y llame a `InitializeSortedFilteredBindingSource` en el método de control de eventos de carga.  
  
## Vea también  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>   
 <xref:System.Windows.Forms.BindingSource.Filter%2A>   
 [Cómo: Instalar bases de datos de ejemplo](../Topic/How%20to:%20Install%20Sample%20Databases.md)   
 [BindingSource \(Componente\)](../../../../docs/framework/winforms/controls/bindingsource-component.md)