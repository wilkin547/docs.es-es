---
title: "C&#243;mo: Llamar a un procedimiento almacenado usando LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "consultas [LINQ en Visual Basic], temas Cómo"
  - "consultas [LINQ en Visual Basic], llamadas a procedimientos almacenados"
  - "procedimientos almacenados [LINQ to SQL]"
  - "ejemplo de procedimientos almacenados [Visual Basic]"
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Llamar a un procedimiento almacenado usando LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Language\-Integrated Query \(LINQ\) simplifica el acceso a la información de las bases de datos, incluidos los objetos de base de datos como los procedimientos almacenados.  
  
 En el ejemplo siguiente se muestra cómo crear una aplicación que llama a un procedimiento almacenado en una base de datos de SQL Server.  En el ejemplo se muestra cómo llamar a dos procedimientos almacenados diferentes en la base de datos.  Cada procedimiento devuelve los resultados de una consulta.  Uno de los procedimientos toma parámetros de entrada y el otro no toma ningún parámetro.  
  
 En los ejemplos de este tema se usa la base de datos de ejemplo Northwind.  Si no tiene instalada la base de datos de ejemplo Northwind en el equipo de desarrollo, puede descargarla desde el sitio web del [Centro de descarga de Microsoft](http://go.microsoft.com/fwlink/?LinkID=98088).  Para obtener instrucciones, vea [Descargar bases de datos de ejemplo](../Topic/Downloading%20Sample%20Databases.md).  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Para crear una conexión a una base de datos  
  
1.  En Visual Studio, haga clic en **Explorador de servidores**\/**Explorador de bases de datos** en el menú **Ver** para abrir el **Explorador de servidores**\/**Explorador de bases de datos**.  
  
2.  En el **Explorador de servidores**\/**Explorador de bases de datos**, haga clic con el botón secundario del mouse en **Conexiones de datos** y, a continuación, haga clic en **Agregar conexión**.  
  
3.  Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### Para agregar un proyecto que contiene un archivo de LINQ to SQL  
  
1.  En el menú **Archivo** de Visual Studio, elija **Nuevo** y, a continuación, haga clic en **Proyecto**.  Seleccione **Aplicación de Windows Forms** de Visual Basic como tipo de proyecto.  
  
2.  En el menú **Proyecto**, haga clic en **Agregar nuevo elemento**.  Seleccione la plantilla de elementos **Clases de LINQ to SQL**.  
  
3.  Asigne al archivo el nombre `northwind.dbml`.  Haga clic en **Agregar**.  Se abre el Object Relational Designer para el archivo northwind.dbml.  
  
### Para agregar procedimientos almacenados al Object Relational Designer  
  
1.  En el **Explorador de servidores**\/**Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.  Expanda la carpeta **Procedimientos almacenados**.  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.  
  
2.  Haga clic en el procedimiento almacenado **Sales by Year** y arrástrelo hasta el panel derecho del diseñador.  Haga clic en el procedimiento almacenado **Ten Most Expensive Products** y arrástrelo hasta el panel derecho del diseñador.  
  
3.  Guarde los cambios y cierre el diseñador.  
  
4.  Guarde el proyecto.  
  
### Para agregar código para mostrar los resultados de los procedimientos almacenados  
  
1.  Desde el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.DataGridView> hasta el Windows Form predeterminado del proyecto, Form1.  
  
2.  Haga doble clic en Form1 para agregar código a su evento `Load`.  
  
3.  Cuando agregó procedimientos almacenados al Object Relational Designer, éste agregó un objeto <xref:System.Data.Linq.DataContext> al proyecto.  Este objeto contiene el código necesario para obtener acceso a esos procedimientos.  El nombre del objeto <xref:System.Data.Linq.DataContext> del proyecto se basa en el nombre del archivo .dbml.  En este proyecto, el objeto <xref:System.Data.Linq.DataContext> se denomina `northwindDataContext`.  
  
     Puede crear una instancia de <xref:System.Data.Linq.DataContext> en el código y llamar a los métodos de procedimiento almacenado especificados por el Object Relational Designer.  Para enlazar al objeto <xref:System.Windows.Forms.DataGridView>, puede que tenga que forzar la consulta a que se ejecute inmediatamente llamando al método <xref:System.Linq.Enumerable.ToList%2A> en los resultados del procedimiento almacenado.  
  
     Agregue el código siguiente al evento `Load` para llamar a cualquiera de los procedimientos almacenados expuestos como métodos para el contexto de datos.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  Presione F5 para ejecutar el proyecto y ver los resultados.  
  
## Vea también  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ a SQL](../Topic/LINQ%20to%20SQL.md)   
 [Métodos DataContext \(Object Relational Designer\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones \(Object Relational Designer\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [Tutorial: Crear clases de LINQ to SQL \(Object Relational Designer\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)