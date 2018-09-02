---
title: 'Cómo: Modificar datos en una base de datos usando LINQ (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: 02aaf2924c6230615d7d1cbcceac72265419b541
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402901"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Cómo: Modificar datos en una base de datos usando LINQ (Visual Basic)
Language Integrated Query de Query (LINQ) facilitan el acceso a la información de la base de datos y modificar los valores de la base de datos.  
  
 El ejemplo siguiente muestra cómo crear una nueva aplicación que recupera y actualiza la información en una base de datos de SQL Server.  
  
 Los ejemplos de este tema usan la base de datos de ejemplo Northwind. Si no tiene esta base de datos en el equipo de desarrollo, puede descargarlo desde Microsoft Download Center. Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
### <a name="to-create-a-connection-to-a-database"></a>Para crear una conexión a una base de datos  
  
1.  En Visual Studio, abra **Explorador de servidores**/**Database Explorer** haciendo clic en el **vista** menú y, a continuación, seleccione **delexploradordeservidores** / **El Explorador de la base de datos**.  
  
2.  Haga clic en **conexiones de datos** en **Explorador de servidores**/**Database Explorer**y haga clic en **Agregar conexión**.  
  
3.  Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Para agregar un proyecto con LINQ a archivo SQL  
  
1.  En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**. Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.  
  
2.  En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Seleccione el **clases LINQ to SQL** plantilla de elemento.  
  
3.  Asigne al archivo el nombre `northwind.dbml`. Haga clic en **Agregar**. Se abre el Object Relational Designer (Object Relational Designer) para el `northwind.dbml` archivo.  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Para agregar las tablas para consultar y modificar el diseñador  
  
1.  En **Explorador de servidores**/**Database Explorer**, expanda la conexión a la base de datos Northwind. Expanda el **tablas** carpeta.  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el `northwind.dbml` archivo que agregó anteriormente.  
  
2.  Haga clic en la tabla Customers y arrástrelo hasta el panel izquierdo del diseñador.  
  
     El diseñador crea un nuevo objeto de cliente para el proyecto.  
  
3.  Guarde los cambios y cierre el diseñador.  
  
4.  Guarde el proyecto.  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Para agregar código para modificar la base de datos y mostrar los resultados  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control en el formulario de Windows predeterminada para el proyecto, Form1.  
  
2.  Cuando agrega tablas a Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext> objeto a su proyecto. Este objeto contiene código que puede usar para tener acceso a la tabla Customers. También contiene código que define un objeto de cliente local y una colección de los clientes de la tabla. La <xref:System.Data.Linq.DataContext> objeto para el proyecto se denomina según el nombre del archivo dbml. Para este proyecto, el <xref:System.Data.Linq.DataContext> se denomina objeto `northwindDataContext`.  
  
     Puede crear una instancia de la <xref:System.Data.Linq.DataContext> de objetos en el código y consultar y modificar la colección de los clientes especificada por el Object Relational Designer. Los cambios realizados en la colección de los clientes no se reflejan en la base de datos hasta que los envíe al llamar a la <xref:System.Data.Linq.DataContext.SubmitChanges%2A> método de la <xref:System.Data.Linq.DataContext> objeto.  
  
     Haga doble clic en el formulario de Windows, Form1, para agregar código a la <xref:System.Windows.Forms.Form.Load> eventos para consultar la tabla Customers que se exponen como una propiedad de su <xref:System.Data.Linq.DataContext>. Agregue el código siguiente:  
  
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
  
3.  Desde el **cuadro de herramientas**, arrastre tres <xref:System.Windows.Forms.Button> controles al formulario. Seleccione el primer `Button` control. En el **propiedades** ventana, establezca el `Name` de la `Button` el control a `AddButton` y `Text` a `Add`. Seleccione el segundo botón y establezca el `Name` propiedad `UpdateButton` y el `Text` propiedad `Update`. Seleccione el tercer botón y establezca el `Name` propiedad `DeleteButton` y el `Text` propiedad `Delete`.  
  
4.  Haga doble clic en el **agregar** para agregar código a su `Click` eventos. Agregue el código siguiente:  
  
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
  
5.  Haga doble clic en el **actualización** para agregar código a su `Click` eventos. Agregue el código siguiente:  
  
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
  
6.  Haga doble clic en el **eliminar** para agregar código a su `Click` eventos. Agregue el código siguiente:  
  
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
  
7.  Presione F5 para ejecutar el proyecto. Haga clic en **agregar** para agregar un nuevo registro. Haga clic en **actualización** para modificar el nuevo registro. Haga clic en **eliminar** para eliminar el nuevo registro.  
  
## <a name="see-also"></a>Vea también  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Consultas](../../../../visual-basic/language-reference/queries/index.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [Métodos DataContext (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](https://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
