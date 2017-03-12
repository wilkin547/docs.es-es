---
title: "C&#243;mo: Modificar datos en una base de datos usando LINQ (Visual Basic) | Microsoft Docs"
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
  - "datos [Visual Basic], actualizar"
  - "eliminar datos"
  - "eliminar filas [LINQ to SQL]"
  - "insertar datos [Visual Basic]"
  - "insertar filas [LINQ to SQL]"
  - "consultas [LINQ en Visual Basic], cambios de datos en bases de datos"
  - "consultas [LINQ en Visual Basic], temas Cómo"
  - "actualizar datos [LINQ]"
  - "actualizar filas [LINQ to SQL]"
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# C&#243;mo: Modificar datos en una base de datos usando LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las consultas Language\-Integrated Query \(LINQ\) simplifican el acceso a la información y la modificación de los valores de la base de datos.  
  
 El ejemplo siguiente muestra cómo crear una nueva aplicación que recupere y actualice la información de una base de datos de SQL Server.  
  
 En los ejemplos de este tema se usa la base de datos de ejemplo Northwind.  Si no tiene instalada la base de datos de ejemplo Northwind en el equipo de desarrollo, puede descargarla desde el sitio web del [Centro de descarga de Microsoft](http://go.microsoft.com/fwlink/?LinkID=98088).  Para obtener instrucciones, vea [Descargar bases de datos de ejemplo](../Topic/Downloading%20Sample%20Databases.md).  
  
### Para crear una conexión a una base de datos  
  
1.  En Visual Studio, abra el **Explorador de servidores**\/**Explorador de bases de datos** haciendo clic en el menú **Ver** y, a continuación, seleccione **Explorador de servidores**\/**Explorador de bases de datos**.  
  
2.  Haga clic con el botón secundario en **Conexiones de datos** en el **Explorador de servidores**\/**Explorador de bases de datos** y haga clic en **Agregar conexión**.  
  
3.  Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### Para agregar un proyecto con un archivo LINQ to SQL  
  
1.  En el menú **Archivo** de Visual Studio, elija **Nuevo** y, a continuación, haga clic en **Proyecto**.  Seleccione **Aplicación de Windows Forms** de Visual Basic como tipo de proyecto.  
  
2.  En el menú **Proyecto**, haga clic en **Agregar nuevo elemento**.  Seleccione la plantilla de elementos **Clases de LINQ to SQL**.  
  
3.  Asigne al archivo el nombre `northwind.dbml`.  Haga clic en **Agregar**.  Se abre el Object Relational Designer \(Diseñador R\/O\) para el archivo `northwind.dbml`.  
  
### Para agregar tablas con el fin de consultar y modificar el diseñador  
  
1.  En el **Explorador de servidores**\/**Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.  Expanda la carpeta **Tablas**.  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo `northwind.dbml` que agregó anteriormente.  
  
2.  Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.  
  
     El diseñador crea un nuevo objeto Customer para el proyecto.  
  
3.  Guarde los cambios y cierre el diseñador.  
  
4.  Guarde el proyecto.  
  
### Para agregar código con el fin de modificar la base de datos y mostrar los resultados  
  
1.  Desde el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.DataGridView> hasta el Windows Form predeterminado del proyecto, Form1.  
  
2.  Cuando agregó tablas al Object Relational Designer, éste agregó un objeto <xref:System.Data.Linq.DataContext> al proyecto.  Este objeto contiene código que puede utilizar para tener acceso a la tabla Customers.  También contiene código que define un objeto Customer local y una colección Customers para la tabla.  El nombre del objeto <xref:System.Data.Linq.DataContext> del proyecto se basa en el nombre del archivo .dbml.  En este proyecto, el objeto <xref:System.Data.Linq.DataContext> se denomina `northwindDataContext`.  
  
     Puede crear una instancia del objeto <xref:System.Data.Linq.DataContext> en el código, así como para consultar y modificar la colección Customers especificada por el Object Relational Designer.  Los cambios que realice en la colección Customers no se reflejan en la base de datos hasta que los envíe llamando al método <xref:System.Data.Linq.DataContext.SubmitChanges%2A> del objeto <xref:System.Data.Linq.DataContext>.  
  
     Haga doble clic en el Windows Form, Form1, para agregar el código al evento <xref:System.Windows.Forms.Form.Load> con el fin de consultar la tabla Customers que se expone como propiedad de <xref:System.Data.Linq.DataContext>.  Agregue el código siguiente:  
  
    ```vb#  
    Private db As northwindDataContext  
  
    Private Sub Form1_Load(ByVal sender As System.Object,   
                           ByVal e As System.EventArgs  
                          ) Handles MyBase.Load  
      db = New northwindDataContext()  
  
      RefreshData()  
    End Sub  
  
    Private Sub RefreshData()  
      Dim customers = From cust In db.Customers   
                      Where cust.City(0) = "W"   
                      Select cust  
  
      DataGridView1.DataSource = customers  
    End Sub  
    ```  
  
3.  Desde el **Cuadro de herramientas**, arrastre tres controles <xref:System.Windows.Forms.Button> hasta el formulario.  Seleccione el primer control `Button`.  En la ventana **Propiedades**, establezca el valor de `Name` del control `Button` en `AddButton` y `Text` en `Add`.  Seleccione el segundo botón y establezca la propiedad `Name` en `UpdateButton` y la propiedad `Text` en `Update`.  Seleccione el tercer botón y establezca la propiedad `Name` en `DeleteButton` y la propiedad `Text` en `Delete`.  
  
4.  Haga doble clic en el botón **Agregar** para agregar el código al evento `Click`.  Agregue el código siguiente:  
  
    ```vb#  
    Private Sub AddButton_Click(ByVal sender As System.Object,   
                                ByVal e As System.EventArgs  
                               ) Handles AddButton.Click  
      Dim cust As New Customer With {   
        .City = "Wellington",   
        .CompanyName = "Blue Yonder Airlines",   
        .ContactName = "Jill Frank",   
        .Country = "New Zealand",   
        .CustomerID = "JILLF"}  
  
      db.Customers.InsertOnSubmit(cust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
5.  Haga doble clic en el botón **Actualizar** para agregar el código al evento `Click`.  Agregue el código siguiente:  
  
    ```vb#  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  Haga doble clic en el botón **Eliminar** para agregar el código al evento `Click`.  Agregue el código siguiente:  
  
    ```vb#  
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles DeleteButton.Click  
      Dim deleteCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      db.Customers.DeleteOnSubmit(deleteCust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
7.  Presione F5 para ejecutar el proyecto.  Haga clic en **Agregar** para agregar un nuevo registro.  Haga clic en **Actualizar** para modificar el nuevo registro.  Haga clic en **Eliminar** para eliminar el nuevo registro.  
  
## Vea también  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ a SQL](../Topic/LINQ%20to%20SQL.md)   
 [Métodos DataContext \(Object Relational Designer\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones \(Object Relational Designer\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [Tutorial: Crear clases de LINQ to SQL \(Object Relational Designer\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)