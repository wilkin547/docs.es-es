---
title: Procedimiento para modificar datos en una base de datos mediante LINQ
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
ms.openlocfilehash: eb076d9156fa66858f2e560422eef0dc61ba22b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403490"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Cómo: Modificar datos en una base de datos usando LINQ (Visual Basic)

Las consultas Language-Integrated Query (LINQ) facilitan el acceso a la información de base de datos y la modificación de los valores de la base de datos.

En el ejemplo siguiente se muestra cómo crear una nueva aplicación que recupera y actualiza la información en una base de datos de SQL Server.

En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind. Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft. Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).

### <a name="to-create-a-connection-to-a-database"></a>Para crear una conexión a una base de datos

1. Para abrir **Explorador de servidores**explorador de bases de datos en Visual Studio, / **Database Explorer** haga clic en el menú **Ver** y, a continuación, seleccione **Explorador de servidores** / **Explorador de bases de datos**.

2. Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores** / **Explorador de bases de datos**y haga clic en **Agregar conexión**.

3. Especifique una conexión válida a la base de datos de ejemplo Northwind.

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Para agregar un proyecto con un archivo LINQ to SQL

1. En Visual Studio, en el menú **archivo** , seleccione **nuevo** y haga clic en **proyecto**. Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.

2. En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Seleccione la plantilla de elementos **LINQ to SQL clases** .

3. Ponga al archivo el nombre `northwind.dbml`. Haga clic en **Agregar**. Se abre el Object Relational Designer (Object Relational Designer) para el `northwind.dbml` archivo.

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Para agregar tablas que se van a consultar y modificar en el diseñador

1. En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind. Expanda la carpeta **Tablas** .

     Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el `northwind.dbml` archivo que agregó anteriormente.

2. Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.

     El diseñador crea un nuevo objeto Customer para el proyecto.

3. Guarde los cambios y cierre el diseñador.

4. Guarde el proyecto.

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Para agregar código con el fin de modificar la base de datos y mostrar los resultados

1. En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.

2. Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto al proyecto. Este objeto contiene código que se puede utilizar para tener acceso a la tabla customers. También contiene código que define un objeto de cliente local y una colección de clientes para la tabla. El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml. Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .

     Puede crear una instancia del <xref:System.Data.Linq.DataContext> objeto en el código y consultar y modificar la colección customers especificada por Object Relational Designer. Los cambios que realice en la colección customers no se reflejarán en la base de datos hasta que los envíe llamando al <xref:System.Data.Linq.DataContext.SubmitChanges%2A> método del <xref:System.Data.Linq.DataContext> objeto.

     Haga doble clic en Windows Forms, Form1, para agregar código al <xref:System.Windows.Forms.Form.Load> evento para consultar la tabla Customers que se expone como una propiedad de su <xref:System.Data.Linq.DataContext> . Agregue el código siguiente:

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

3. En el **cuadro de herramientas**, arrastre tres <xref:System.Windows.Forms.Button> controles al formulario. Seleccione el primer `Button` control. En la ventana **propiedades** , establezca la propiedad `Name` del `Button` control en `AddButton` y `Text` en `Add` . Seleccione el segundo botón y establezca la `Name` propiedad en `UpdateButton` y la `Text` propiedad en `Update` . Seleccione el tercer botón y establezca la `Name` propiedad en `DeleteButton` y la `Text` propiedad en `Delete` .

4. Haga doble clic en el botón **Agregar** para agregar código a su `Click` evento. Agregue el código siguiente:

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

5. Haga doble clic en el botón **Actualizar** para agregar código a su `Click` evento. Agregue el código siguiente:

    ```vb
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles UpdateButton.Click
      Dim updateCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

6. Haga doble clic en el botón **eliminar** para agregar código a su `Click` evento. Agregue el código siguiente:

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

7. Presione F5 para ejecutar el proyecto. Haga clic en **Agregar** para agregar un nuevo registro. Haga clic en **Actualizar** para modificar el nuevo registro. Haga clic en **eliminar** para eliminar el nuevo registro.

## <a name="see-also"></a>Consulte también

- [LINQ](index.md)
- [Consultas](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext (métodos) (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
