---
title: "C&#243;mo: Consultar una base de datos usando LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "consultar bases de datos [LINQ]"
  - "consultas [LINQ en Visual Basic], consultar bases de datos"
  - "consultas [LINQ en Visual Basic], temas Cómo"
  - "ejemplos de consultas [LINQ]"
  - "consultas de ejemplo [Visual Basic]"
  - "consultar bases de datos [LINQ]"
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# C&#243;mo: Consultar una base de datos usando LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Language\-Integrated Query \(LINQ\) simplifica el acceso a la información de las bases de datos y la ejecución de consultas.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server.  
  
 En los ejemplos de este tema se usa la base de datos de ejemplo Northwind.  Si no tiene instalada la base de datos de ejemplo Northwind en el equipo de desarrollo, puede descargarla desde el sitio web del [Centro de descarga de Microsoft](http://go.microsoft.com/fwlink/?LinkID=98088).  Para obtener instrucciones, vea [Descargar bases de datos de ejemplo](../Topic/Downloading%20Sample%20Databases.md).  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para crear una conexión a una base de datos  
  
1.  En Visual Studio, haga clic en **Explorador de servidores**\/**Explorador de bases de datos** en el menú **Ver** para abrir el **Explorador de servidores**\/**Explorador de bases de datos**.  
  
2.  En el **Explorador de servidores**\/**Explorador de bases de datos**, haga clic con el botón secundario del mouse en **Conexiones de datos** y, a continuación, haga clic en **Agregar conexión**.  
  
3.  Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### Para agregar un proyecto que contiene un archivo de LINQ to SQL  
  
1.  En el menú **Archivo** de Visual Studio, elija **Nuevo** y, a continuación, haga clic en **Proyecto**.  Seleccione **Aplicación de Windows Forms** de Visual Basic como tipo de proyecto.  
  
2.  En el menú **Proyecto**, haga clic en **Agregar nuevo elemento**.  Seleccione la plantilla de elementos **Clases de LINQ to SQL**.  
  
3.  Asigne al archivo el nombre `northwind.dbml`.  Haga clic en **Agregar**.  Se abre el Object Relational Designer para el archivo northwind.dbml.  
  
### Para agregar tablas al Object Relational Designer  
  
1.  En el **Explorador de servidores**\/**Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.  Expanda la carpeta **Tablas**.  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.  
  
2.  Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.  Haga clic en la tabla Orders y arrástrela hasta el panel izquierdo del diseñador.  
  
     El diseñador crea nuevos objetos `Customer` y `Order` para el proyecto.  Observe que el diseñador detecta automáticamente las relaciones entre las tablas y crea propiedades secundarias para los objetos relacionados.  Por ejemplo, IntelliSense mostrará que el objeto `Customer` tiene una propiedad `Orders` para todos los pedidos relacionados con ese cliente.  
  
3.  Guarde los cambios y cierre el diseñador.  
  
4.  Guarde el proyecto.  
  
### Para agregar código de consulta a la base de datos y mostrar los resultados  
  
1.  Desde el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.DataGridView> hasta el Windows Form predeterminado del proyecto, Form1.  
  
2.  Haga doble clic en Form1 para agregar código al evento `Load` del formulario.  
  
3.  Cuando agregó tablas al Object Relational Designer, éste agregó un objeto <xref:System.Data.Linq.DataContext> al proyecto.  Este objeto contiene el código necesario para obtener acceso a esas tablas y a los objetos individuales y colecciones de cada tabla.  El nombre del objeto <xref:System.Data.Linq.DataContext> del proyecto se basa en el nombre del archivo .dbml.  En este proyecto, el objeto <xref:System.Data.Linq.DataContext> se denomina `northwindDataContext`.  
  
     Puede crear una instancia de <xref:System.Data.Linq.DataContext> en el código y consultar las tablas que especifica el Object Relational Designer.  
  
     Agregue el código siguiente al evento `Load` para consultar las tablas que se exponen como propiedades del contexto de datos.  
  
     [!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/StoredProcedureHowTo/Form2.vb#3)]  
  
4.  Presione F5 para ejecutar el proyecto y ver los resultados.  
  
5.  A continuación, se proporcionan algunas consultas adicionales que puede probar:  
  
     [!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/StoredProcedureHowTo/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/StoredProcedureHowTo/Form2.vb#5)]  
  
## Vea también  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ a SQL](../Topic/LINQ%20to%20SQL.md)   
 [Métodos DataContext \(Object Relational Designer\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [Tutorial: Crear clases de LINQ to SQL \(Object Relational Designer\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)