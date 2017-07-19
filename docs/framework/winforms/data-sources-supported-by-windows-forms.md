---
title: "Or&#237;genes de datos compatibles con formularios Windows Forms | Microsoft Docs"
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
  - "matrices [formularios Windows Forms]"
  - "colecciones [formularios Windows Forms], enlazar"
  - "datos [Windows Forms], proveedores de datos"
  - "proveedores de datos [formularios Windows Forms]"
  - "orígenes de datos [formularios Windows Forms]"
  - "DataColumn (clase)"
  - "DataSet (clase), enlace y formularios Windows Forms"
  - "DataTable (clase), enlace y formularios Windows Forms"
  - "DataView (clase), enlace y formularios Windows Forms"
  - "DataViewManager (clase), enlace y formularios Windows Forms"
  - "proveedores OLE DB, Windows Forms"
  - "Windows Forms, enlace de datos"
  - "Windows Forms, datos de origen"
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Or&#237;genes de datos compatibles con formularios Windows Forms
Tradicionalmente, el enlace de datos se utilizaba dentro de las aplicaciones para utilizar datos almacenados en bases de datos.  Con el enlace de datos de formularios Windows Forms puede tener acceso a los datos de bases de datos, así como a datos de otras estructuras tales como matrices y colecciones, siempre que se cumplan ciertos requisitos mínimos.  
  
## Estructuras con las que realizar el enlace  
 En formularios Windows Forms puede enlazar con una amplia gama de estructuras, desde objetos sencillos \(enlace sencillos\) hasta listas complejas como tablas de datos ADO.NET \(enlace complejo\).  Para el enlace sencillo, los formularios Windows Forms admiten el enlace a las propiedades públicas en el objeto sencillo.  El enlace basado en lista de formularios Windows Forms generalmente requiere que el objeto sea compatible con la interfaz <xref:System.Collections.IList> o la interfaz <xref:System.ComponentModel.IListSource>.  Además, si está realizando el enlace a través de un componente <xref:System.Windows.Forms.BindingSource>, se puede enlazar a un objeto que admite la interfaz <xref:System.Collections.IEnumerable>.  Para obtener más información sobre las interfaces relacionadas con enlace de datos, vea [Interfaces relacionadas con el enlace de datos](../../../docs/framework/winforms/interfaces-related-to-data-binding.md).  
  
 En la lista siguiente se muestran las estructuras con las que se puede realizar el enlace en formularios Windows Forms.  
  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingSource> es el origen de datos de formularios Windows Forms más común y representa un servidor proxy entre un origen de datos y controles de formularios Windows Forms.  El modelo de uso de <xref:System.Windows.Forms.BindingSource> general es enlazar los controles a <xref:System.Windows.Forms.BindingSource> y enlazar <xref:System.Windows.Forms.BindingSource> al origen de datos \(por ejemplo, una tabla de datos ADO.NET o un objeto comercial\).  <xref:System.Windows.Forms.BindingSource> proporciona servicios que habilitan y mejoran el nivel de compatibilidad del enlace de datos.  Por ejemplo, los controles basados en lista de formularios Windows Forms como <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.ComboBox> no admiten directamente el enlace a orígenes de datos <xref:System.Collections.IEnumerable>, no obstante, puede habilitar este escenario realizando el enlace mediante un <xref:System.Windows.Forms.BindingSource>.  En este caso, <xref:System.Windows.Forms.BindingSource> convertirá el origen de datos a una interfaz <xref:System.Collections.IList>.  
  
 Objetos sencillos  
 Los formularios Windows Forms admiten el enlace de datos de propiedades de control a propiedades públicas en la instancia de un objeto utilizando el tipo <xref:System.Windows.Forms.Binding>.  Los formularios Windows Forms también admiten el enlace de controles basados en lista, como una clase <xref:System.Windows.Forms.ListControl> a una instancia de objeto cuando se utiliza <xref:System.Windows.Forms.BindingSource>.  
  
 Matriz o colección  
 Para que actúe de origen de datos, una lista debe implementar la interfaz <xref:System.Collections.IList>; un ejemplo sería una matriz que es una instancia de la clase <xref:System.Array>.  Para obtener más información sobre matrices, consulte [How to: Create an Array of Objects \(Visual Basic\)](http://msdn.microsoft.com/es-es/6b64e069-0387-400c-9081-3bdc581020c3).  
  
 En general, debe utilizar <xref:System.ComponentModel.BindingList%601> al crear listas de objetos para el enlace de datos.  <xref:System.ComponentModel.BindingList%601> es una versión genérica de la interfaz <xref:System.ComponentModel.IBindingList>.  La interfaz <xref:System.ComponentModel.IBindingList> amplía la interfaz <xref:System.Collections.IList> agregando propiedades, métodos y eventos necesarios para el enlace de datos bidireccional.  
  
 <xref:System.Collections.IEnumerable>  
 Los controles de formularios Windows Forms se pueden enlazar a orígenes de datos que sólo admiten la interfaz <xref:System.Collections.IEnumerable> si se enlazan a través de un componente <xref:System.Windows.Forms.BindingSource>.  
  
 Objetos de datos de [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] proporciona varias estructuras de datos adecuadas para el enlace.  Cada una de ellas varía en sofisticación y complejidad.  
  
-   <xref:System.Data.DataColumn>.  Un objeto <xref:System.Data.DataColumn> es el bloque de compilación esencial de <xref:System.Data.DataTable>, por el hecho de que varias columnas componen una tabla.  Cada objeto <xref:System.Data.DataColumn> tiene una propiedad <xref:System.Data.DataColumn.DataType%2A> que determina el tipo de datos que contiene la columna \(por ejemplo, el modelo en una tabla que describa automóviles\).  Puede enlazar un control de forma sencilla \(por ejemplo la propiedad <xref:System.Windows.Forms.TextBox> de un control <xref:System.Windows.Forms.Control.Text%2A>\) a una columna dentro de una tabla de datos.  
  
-   <xref:System.Data.DataTable>.  Un objeto <xref:System.Data.DataTable> es la representación de una tabla, con filas y columnas, en [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].  Una tabla de datos contiene dos colecciones: <xref:System.Data.DataColumn>, que representa las columnas de datos de una tabla determinada \(que en última instancia determinan los tipos de datos que se pueden introducir en esa tabla\) y <xref:System.Data.DataRow>, que representa las filas de datos de una tabla determinada.  Puede enlazar un control de forma compleja a la información contenida en una tabla de datos \(como al enlazar el control <xref:System.Windows.Forms.DataGridView> a una tabla de datos\).  No obstante, cuando establezca un enlace con un objeto <xref:System.Data.DataTable>, en realidad estará estableciendo un enlace a la vista predeterminada de la tabla.  
  
-   <xref:System.Data.DataView>.  Un objeto <xref:System.Data.DataView> es una vista personalizada de una tabla de datos única que se puede filtrar u ordenar.  Una vista de datos es la "instantánea" de los datos que utilizan los controles de enlace complejo.  Puede establecer enlaces sencillos o complejos a los datos de una vista de datos, pero debe tener en cuenta que estará estableciendo enlaces con una "imagen" fija de los datos, en lugar de hacerlo con un origen de datos limpio y actualizado.  
  
-   <xref:System.Data.DataSet>.  Un <xref:System.Data.DataSet> es una colección de tablas, relaciones y restricciones de los datos de una base de datos.  Puede establecer enlaces sencillos o complejos a los datos dentro de un conjunto de datos, pero tenga en cuenta que estará estableciendo el enlace al <xref:System.Data.DataViewManager> predeterminado para el <xref:System.Data.DataSet> \(vea el siguiente punto de viñeta\).  
  
-   <xref:System.Data.DataViewManager>.  Un <xref:System.Data.DataViewManager> es una vista personalizada de todo <xref:System.Data.DataSet>, análogo a <xref:System.Data.DataView>, pero con relaciones incluidas.  Con una colección <xref:System.Data.DataViewManager.DataViewSettings%2A>, puede establecer filtros predeterminados y opciones de ordenación para cualquier vista que <xref:System.Data.DataViewManager> tenga para una tabla determinada.  
  
## Vea también  
 [Notificación de cambios en el enlace de datos de Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Enlace de datos y formularios Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)