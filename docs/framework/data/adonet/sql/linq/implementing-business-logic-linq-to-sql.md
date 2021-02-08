---
description: Más información acerca de cómo implementar la lógica de negocios (LINQ to SQL)
title: Implementar la lógica de negocios (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c4577590-7b12-42e1-84a6-95aa2562727e
ms.openlocfilehash: 3f2b7085db3832f37da7520c8f75b6bc120125f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803885"
---
# <a name="implementing-business-logic-linq-to-sql"></a>Implementar la lógica de negocios (LINQ to SQL)

El término "lógica empresarial" de este tema se refiere a cualquier regla personalizada o prueba de validación que se aplica a los datos antes de insertarlos, actualizarlos o eliminarlos de la base de datos. La lógica empresarial también se conoce a veces como "reglas de empresa" o "lógica del dominio". En aplicaciones de n niveles, se diseña generalmente como una capa lógica para que se pueda modificar independientemente de la capa de presentación o de la capa de acceso a datos. La capa de acceso a datos puede invocar la lógica empresarial antes o después de cualquier actualización, inserción o eliminación de datos en la base de datos.  
  
 La lógica empresarial puede ser tan simple como una validación del esquema para asegurarse de que el tipo del campo es compatible con el tipo de la columna de la tabla. Por el contrario, también puede estar compuesta por un conjunto de objetos que interactúan con diversos grados de complejidad. Las reglas se pueden implementar como procedimientos almacenados en la base de datos o como objetos en memoria. Sin embargo, se implementa la lógica [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de negocios, que permite usar clases parciales y métodos parciales para separar la lógica de negocios del código de acceso a datos.  
  
## <a name="how-linq-to-sql-invokes-your-business-logic"></a>Invocación de la lógica empresarial desde LINQ to SQL  

 Cuando se genera una clase de entidad en tiempo de diseño, ya sea manualmente o mediante el Object Relational Designer o SQLMetal, se define como una clase parcial. Esto significa que puede definir, en un archivo de código independiente, otra parte de la clase de entidad que contiene su lógica empresarial personalizada. En tiempo de compilación, las dos partes se combinan en una única clase. Pero si tiene que volver a generar las clases de entidad mediante el Object Relational Designer o SQLMetal, puede hacerlo y su parte de la clase no se modificará.  
  
 Las clases parciales que definen las entidades y el <xref:System.Data.Linq.DataContext> contienen métodos parciales. Éstos son los puntos de extensibilidad que puede utilizar para aplicar su lógica empresarial antes y después de cualquier actualización, inserción o eliminación para una entidad o propiedad de entidad. Los métodos parciales se pueden ver como eventos de tiempo de compilación. El generador de código define una firma de método y llama a los métodos de los descriptores de acceso get y set de la propiedad, al constructor `DataContext` y, en algunos casos, en segundo plano, se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Sin embargo, si no implementa un método parcial particular, entonces su definición y todas las referencias a él se eliminan en tiempo de compilación.  
  
 En la definición de la implementación que escriba en su archivo de código independiente, puede ejecutar cualquier lógica personalizada que requiera. Puede utilizar su clase parcial por sí misma como la capa de dominio, o puede llamar desde la definición de implementación del método parcial a un objeto o varios objetos independientes. De cualquier modo, su lógica empresarial se separa limpiamente de su código de acceso a datos y de su código de la capa de presentación.  
  
## <a name="a-closer-look-at-the-extensibility-points"></a>Examen más detallado de los puntos de extensibilidad  

 En el ejemplo siguiente se muestra parte del código generado por el Object Relational Designer para la `DataContext` clase que tiene dos tablas: `Customers` y `Orders` . Observe que se definen métodos Insert, Update y Delete para cada tabla de la clase.  
  
```vb  
Partial Public Class Northwnd  
    Inherits System.Data.Linq.DataContext  
  
    Private Shared mappingSource As _  
        System.Data.Linq.Mapping.MappingSource = New _  
        AttributeMappingSource  
  
    #Region "Extensibility Method Definitions"  
    Partial Private Sub OnCreated()  
    End Sub  
    Partial Private Sub InsertCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub UpdateCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub DeleteCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub InsertOrder(instance As [Order])  
    End Sub  
    Partial Private Sub UpdateOrder(instance As [Order])  
    End Sub  
    Partial Private Sub DeleteOrder(instance As [Order])  
    End Sub  
    #End Region  
```  
  
```csharp  
public partial class MyNorthWindDataContext : System.Data.Linq.DataContext  
    {  
        private static System.Data.Linq.Mapping.MappingSource mappingSource = new AttributeMappingSource();  
  
        #region Extensibility Method Definitions  
        partial void OnCreated();  
        partial void InsertCustomer(Customer instance);  
        partial void UpdateCustomer(Customer instance);  
        partial void DeleteCustomer(Customer instance);  
        partial void InsertOrder(Order instance);  
        partial void UpdateOrder(Order instance);  
        partial void DeleteOrder(Order instance);  
        #endregion  
```  
  
 Si implementa los métodos Insert, Update y Delete en su clase parcial, el motor de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] los llamará en lugar de sus propios métodos predeterminados al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Esto permite invalidar el comportamiento predeterminado para las operaciones de crear, leer, actualizar y eliminar datos. Para obtener más información, vea [Tutorial: personalizar el comportamiento de inserción, actualización y eliminación de las clases de entidad](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).  
  
 Al método `OnCreated` se le llama en el constructor de la clase.  
  
```vb  
Public Sub New(ByVal connection As String)  
    MyBase.New(connection, mappingSource)  
    OnCreated()  
End Sub  
```  
  
```csharp  
public MyNorthWindDataContext(string connection) :  
            base(connection, mappingSource)  
        {  
            OnCreated();  
        }  
```  
  
 Las clases de entidad tienen tres métodos a los que llama el motor de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] al crear, cargar y validar la entidad (cuando se llama a `SubmitChanges`). Las clases de entidad también tienen dos métodos parciales para cada propiedad, uno al que se llama antes de que se establezca la propiedad y otro al que se llama después. En el ejemplo de código siguiente se muestran algunos de los métodos generados por la clase `Customer`.  
  
```vb  
#Region "Extensibility Method Definitions"  
    Partial Private Sub OnLoaded()  
    End Sub  
    Partial Private Sub OnValidate(action As _  
        System.Data.Linq.ChangeAction)  
    End Sub  
    Partial Private Sub OnCreated()  
    End Sub  
    Partial Private Sub OnCustomerIDChanging(value As String)  
    End Sub  
    Partial Private Sub OnCustomerIDChanged()  
    End Sub  
    Partial Private Sub OnCompanyNameChanging(value As String)  
    End Sub  
    Partial Private Sub OnCompanyNameChanged()  
    End Sub  
' ...Additional Changing/Changed methods for each property.  
```  
  
```csharp  
#region Extensibility Method Definitions  
    partial void OnLoaded();  
    partial void OnValidate();  
    partial void OnCreated();  
    partial void OnCustomerIDChanging(string value);  
    partial void OnCustomerIDChanged();  
    partial void OnCompanyNameChanging(string value);  
    partial void OnCompanyNameChanged();  
// ...additional Changing/Changed methods for each property  
```  
  
 Se llama a los métodos en el descriptor de acceso set de la propiedad, como se muestra en el ejemplo siguiente para la propiedad `CustomerID`:  
  
```vb  
Public Property CustomerID() As String  
    Set  
        If (String.Equals(Me._CustomerID, value) = False) Then  
            Me.OnCustomerIDChanging(value)  
            Me.SendPropertyChanging()  
            Me._CustomerID = value  
            Me.SendPropertyChanged("CustomerID")  
            Me.OnCustomerIDChanged()  
        End If  
    End Set  
End Property  
```  
  
```csharp  
public string CustomerID  
{  
    set  
    {  
        if ((this._CustomerID != value))  
        {  
            this.OnCustomerIDChanging(value);  
            this.SendPropertyChanging();  
            this._CustomerID = value;  
            this.SendPropertyChanged("CustomerID");  
            this.OnCustomerIDChanged();  
        }  
     }  
}  
```  
  
 En su parte de la clase, escriba una definición de implementación del método. En Visual Studio, después de escribir, `partial` verá IntelliSense para las definiciones de método en la otra parte de la clase.  
  
```vb  
Partial Public Class Customer  
    Private Sub OnCustomerIDChanging(value As String)  
        ' Perform custom validation logic here.  
    End Sub  
End Class  
```  
  
```csharp  
partial class Customer
    {  
        partial void OnCustomerIDChanging(string value)  
        {  
            //Perform custom validation logic here.  
        }  
    }  
```  
  
 Para obtener más información sobre cómo agregar lógica empresarial a su aplicación utilizando métodos parciales, vea los temas siguientes:  
  
 [Cómo: Agregar validación a clases de entidad](/visualstudio/data-tools/how-to-add-validation-to-entity-classes)  
  
 [Tutorial: Personalizar el comportamiento de inserción, actualización y eliminación de las clases de entidad](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes)  
  
 [Tutorial: Agregar validación a clases de entidad](/previous-versions/visualstudio/visual-studio-2013/bb629301(v=vs.120))  
  
## <a name="see-also"></a>Vea también

- [Clases y métodos parciales](../../../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)
- [Métodos parciales](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
- [Herramientas LINQ to SQL en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
