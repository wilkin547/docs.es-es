---
title: "Cómo: modificar datos en una base de datos usando LINQ (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 44ca3e44d8411a6329d176eb778677bfab2b365c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Cómo: Modificar datos en una base de datos usando LINQ (Visual Basic)
Consultas integradas del lenguaje de consulta (LINQ) facilitan el acceso a la información de la base de datos y modificar los valores en la base de datos.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva aplicación que recupera y actualiza la información en una base de datos de SQL Server.  
  
 Los ejemplos de este tema utilizan la base de datos de ejemplo Northwind. Si no tiene la base de datos de ejemplo Northwind en el equipo de desarrollo, puede descargarla desde el [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sitio Web. Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](https://msdn.microsoft.com/library/bb399411).  
  
### <a name="to-create-a-connection-to-a-database"></a>Para crear una conexión a una base de datos  
  
1.  En Visual Studio, abra **Explorador de servidores**/**Database Explorer** haciendo clic en el **vista** menú y, a continuación, seleccione **Explorador de servidores**/**Database Explorer**.  
  
2.  Haga clic en **las conexiones de datos** en **Explorador de servidores**/**Database Explorer**y haga clic en **Agregar conexión**.  
  
3.  Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Para agregar un proyecto con LINQ a archivo SQL  
  
1.  En Visual Studio, en el **archivo** menú, seleccione **nueva** y, a continuación, haga clic en **proyecto**. Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.  
  
2.  En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Seleccione el **clases LINQ to SQL** plantilla de elemento.  
  
3.  Nombre de archivo `northwind.dbml`. Haga clic en **Agregar**. Se abre el Object Relational Designer (Object Relational Designer) para el `northwind.dbml` archivo.  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Para agregar tablas para consultar y modificar el diseñador  
  
1.  En **Explorador de servidores**/**Database Explorer**, expanda la conexión de la base de datos Northwind. Expanda el **tablas** carpeta.  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el `northwind.dbml` archivo que agregó anteriormente.  
  
2.  Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.  
  
     El diseñador crea un nuevo objeto Customer para el proyecto.  
  
3.  Guarde los cambios y cierre el diseñador.  
  
4.  Guarde el proyecto.  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Para agregar código para modificar la base de datos y mostrar los resultados  
  
1.  Desde el **herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView>control en el formulario Windows Forms predeterminado del proyecto, Form1.</xref:System.Windows.Forms.DataGridView>  
  
2.  Cuando agrega tablas a Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext>objeto a su proyecto.</xref:System.Data.Linq.DataContext> Este objeto contiene código que puede utilizar para tener acceso a la tabla Customers. También contiene código que define un objeto de cliente local y un conjunto de clientes de la tabla. La <xref:System.Data.Linq.DataContext>objeto para su proyecto se denomina según el nombre del archivo .dbml.</xref:System.Data.Linq.DataContext> Para este proyecto, el <xref:System.Data.Linq.DataContext>se denomina objeto `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     Puede crear una instancia de la <xref:System.Data.Linq.DataContext>objeto en el código y consultar y modificar la colección Customers especificada por el Object Relational Designer.</xref:System.Data.Linq.DataContext> Los cambios realizados en la colección Customers no se reflejan en la base de datos hasta que los envíe llamando el <xref:System.Data.Linq.DataContext.SubmitChanges%2A>método de la <xref:System.Data.Linq.DataContext>objeto.</xref:System.Data.Linq.DataContext> </xref:System.Data.Linq.DataContext.SubmitChanges%2A>  
  
     Haga doble clic en el formulario Windows Forms, Form1, para agregar código al <xref:System.Windows.Forms.Form.Load>evento para consultar la tabla Customers que se expone como una propiedad de su <xref:System.Data.Linq.DataContext>.</xref:System.Data.Linq.DataContext> </xref:System.Windows.Forms.Form.Load> Agregue el código siguiente:  
  
    ```vb  
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
  
3.  Desde el **herramientas**, arrastre tres <xref:System.Windows.Forms.Button>controles al formulario.</xref:System.Windows.Forms.Button> Seleccione el primer `Button` control. En el **propiedades** ventana, establezca la `Name` de la `Button` control a `AddButton` y `Text` a `Add`. Seleccione el segundo botón y establezca la `Name` propiedad `UpdateButton` y `Text` propiedad `Update`. Seleccione el tercer botón y establezca la `Name` propiedad `DeleteButton` y `Text` propiedad `Delete`.  
  
4.  Haga doble clic en el **agregar** botón para agregar código a su `Click` eventos. Agregue el código siguiente:  
  
    ```vb  
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
  
5.  Haga doble clic en el **actualización** botón para agregar código a su `Click` eventos. Agregue el código siguiente:  
  
    ```vb  
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
  
6.  Haga doble clic en el **eliminar** botón para agregar código a su `Click` eventos. Agregue el código siguiente:  
  
    ```vb  
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
  
7.  Presione F5 para ejecutar el proyecto. Haga clic en **agregar** para agregar un nuevo registro. Haga clic en **actualización** para modificar el nuevo registro. Haga clic en **eliminar** para eliminar el registro nuevo.  
  
## <a name="see-also"></a>Vea también  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [Métodos de DataContext (Object Relational Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)   
 [Cómo: asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
