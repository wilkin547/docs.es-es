---
title: "C&#243;mo: Devolver el resultado de una consulta con LINQ como tipo espec&#237;fico (Visual Basic) | Microsoft Docs"
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
  - "tipos anónimos [Visual Basic]"
  - "proyección [LINQ in Visual Basic]"
  - "consultas [LINQ en Visual Basic], temas Cómo"
  - "consultas [LINQ en Visual Basic], tipos específicos devueltos"
  - "consultas de ejemplo [Visual Basic]"
  - "consultar bases de datos [LINQ]"
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Devolver el resultado de una consulta con LINQ como tipo espec&#237;fico (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Language\-Integrated Query \(LINQ\) simplifica el acceso a la información de las bases de datos y la ejecución de consultas.  De forma predeterminada, las consultas LINQ devuelven una lista de objetos como un tipo anónimo.  También se puede especificar que una consulta devuelva una lista de un tipo determinado mediante la cláusula `Select`.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server y proyecta los resultados como un tipo con nombre específico.  Para obtener más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) y [Select \(Cláusula\)](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
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
  
### Para agregar tablas al Object Relational Designer  
  
1.  En el **Explorador de servidores**\/**Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.  Expanda la carpeta **Tablas**.  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.  
  
2.  Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.  
  
     El diseñador crea un nuevo objeto `Customer` para el proyecto.  Se puede proyectar el resultado de una consulta como el tipo `Customer` o como un tipo creado por el usuario.  En este ejemplo se crea un nuevo tipo en un procedimiento posterior y se proyecta un resultado de consulta como ese tipo.  
  
3.  Guarde los cambios y cierre el diseñador.  
  
4.  Guarde el proyecto.  
  
### Para agregar código de consulta a la base de datos y mostrar los resultados  
  
1.  Desde el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.DataGridView> hasta el Windows Form predeterminado del proyecto, Form1.  
  
2.  Haga doble clic en Form1 para modificar la clase Form1.  
  
3.  Después de la instrucción `End Class` de la clase Form1, agregue el código siguiente para crear un tipo `CustomerInfo` que contenga los resultados de consulta de este ejemplo.  
  
     [!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]  
  
4.  Cuando agregó tablas al Object Relational Designer, éste agregó un objeto <xref:System.Data.Linq.DataContext> al proyecto.  Este objeto contiene el código necesario para obtener acceso a esas tablas y a los objetos individuales y colecciones de cada tabla.  El nombre del objeto <xref:System.Data.Linq.DataContext> del proyecto se basa en el nombre del archivo .dbml.  En este proyecto, el objeto <xref:System.Data.Linq.DataContext> se denomina `northwindDataContext`.  
  
     Puede crear una instancia de <xref:System.Data.Linq.DataContext> en el código y consultar las tablas que especifica el Object Relational Designer.  
  
     En el evento `Load` de la clase Form1, agregue el código siguiente para consultar las tablas que se exponen como propiedades del contexto de datos.  La cláusula `Select` de la consulta creará un nuevo tipo `CustomerInfo` en lugar de un tipo anónimo para cada elemento del resultado de la consulta.  
  
     [!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]  
  
5.  Presione F5 para ejecutar el proyecto y ver los resultados.  
  
## Vea también  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ a SQL](../Topic/LINQ%20to%20SQL.md)   
 [Métodos DataContext \(Object Relational Designer\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [Tutorial: Crear clases de LINQ to SQL \(Object Relational Designer\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)