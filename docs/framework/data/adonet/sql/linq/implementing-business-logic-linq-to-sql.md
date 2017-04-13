---
title: "Implementar l&#243;gica empresarial (LINQ to SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c4577590-7b12-42e1-84a6-95aa2562727e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Implementar l&#243;gica empresarial (LINQ to SQL)
El término "lógica empresarial" de este tema se refiere a cualquier regla personalizada o prueba de validación que se aplica a los datos antes de insertarlos, actualizarlos o eliminarlos de la base de datos.  La lógica empresarial también se conoce a veces como "reglas de empresa" o "lógica del dominio". En aplicaciones de n niveles, se diseña generalmente como una capa lógica para que se pueda modificar independientemente de la capa de presentación o de la capa de acceso a datos.  La capa de acceso a datos puede invocar la lógica empresarial antes o después de cualquier actualización, inserción o eliminación de datos en la base de datos.  
  
 La lógica empresarial puede ser tan simple como una validación del esquema para asegurarse de que el tipo del campo es compatible con el tipo de la columna de la tabla.  Por el contrario, también puede estar compuesta por un conjunto de objetos que interactúan con diversos grados de complejidad.  Las reglas se pueden implementar como procedimientos almacenados en la base de datos o como objetos en memoria.  Independientemente de cómo se implemente la lógica empresarial, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] permite utilizar clases parciales y métodos parciales para separar la lógica empresarial del código de acceso a datos.  
  
## Invocación de la lógica empresarial desde LINQ to SQL  
 Cuando se genera una clase de entidad en tiempo de diseño, ya sea manualmente o mediante el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] o SQLMetal, se define como una clase parcial.  Esto significa que puede definir, en un archivo de código independiente, otra parte de la clase de entidad que contiene su lógica empresarial personalizada.  En tiempo de compilación, las dos partes se combinan en una única clase. Pero si tiene que volver a generar sus clases de entidad con el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] o SQLMetal, puede hacerlo; su parte de la clase no se modificará.  
  
 Las clases parciales que definen las entidades y el <xref:System.Data.Linq.DataContext> contienen métodos parciales.  Éstos son los puntos de extensibilidad que puede utilizar para aplicar su lógica empresarial antes y después de cualquier actualización, inserción o eliminación para una entidad o propiedad de entidad.  Los métodos parciales se pueden ver como eventos de tiempo de compilación.  El generador de código define una firma de método y llama a los métodos de los descriptores de acceso get y set de la propiedad, al constructor `DataContext` y, en algunos casos, en segundo plano, se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  Sin embargo, si no implementa un método parcial particular, entonces su definición y todas las referencias a él se eliminan en tiempo de compilación.  
  
 En la definición de la implementación que escriba en su archivo de código independiente, puede ejecutar cualquier lógica personalizada que requiera.  Puede utilizar su clase parcial por sí misma como la capa de dominio, o puede llamar desde la definición de implementación del método parcial a un objeto o varios objetos independientes.  De cualquier modo, su lógica empresarial se separa limpiamente de su código de acceso a datos y de su código de la capa de presentación.  
  
## Examen más detallado de los puntos de extensibilidad  
 El ejemplo siguiente muestra parte del código generado por el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para la clase `DataContext` que tiene dos tablas: `Customers` y `Orders`.  Observe que se definen métodos Insert, Update y Delete para cada tabla de la clase.  
  
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
  
 Si implementa los métodos Insert, Update y Delete en su clase parcial, el motor de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] los llamará en lugar de sus propios métodos predeterminados al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  Esto permite invalidar el comportamiento predeterminado para las operaciones de crear, leer, actualizar y eliminar datos.  Para obtener más información, consulte [Tutorial: Personalizar el comportamiento de inserción, actualización y eliminación de las clases de entidad](../Topic/Walkthrough:%20Customizing%20the%20insert,%20update,%20and%20delete%20behavior%20of%20entity%20classes.md).  
  
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
  
 Las clases de entidad tienen tres métodos a los que llama el motor de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] al crear, cargar y validar la entidad \(cuando se llama a `SubmitChanges`\).  Las clases de entidad también tienen dos métodos parciales para cada propiedad, uno al que se llama antes de que se establezca la propiedad y otro al que se llama después.  En el ejemplo de código siguiente se muestran algunos de los métodos generados por la clase `Customer`.  
  
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
  
 En su parte de la clase, escriba una definición de implementación del método.  En [!INCLUDE[vsprvs](../../../../../../includes/vsprvs-md.md)], después de escribir `partial`, aparecerá información de IntelliSense para las definiciones de método de la otra parte de la clase.  
  
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
  
 [Cómo: Agregar validación a clases de entidad](../Topic/How%20to:%20Add%20validation%20to%20entity%20classes.md)  
  
 [Tutorial: Personalizar el comportamiento de inserción, actualización y eliminación de las clases de entidad](../Topic/Walkthrough:%20Customizing%20the%20insert,%20update,%20and%20delete%20behavior%20of%20entity%20classes.md)  
  
 [Tutorial: Agregar validación a clases de entidad](../Topic/Walkthrough:%20Adding%20Validation%20to%20Entity%20Classes.md)  
  
## Vea también  
 [Clases y métodos parciales](../Topic/Partial%20Classes%20and%20Methods%20\(C%23%20Programming%20Guide\).md)   
 [Métodos Partial](../Topic/Partial%20Methods%20\(Visual%20Basic\).md)   
 [LINQ to SQL Tools en Visual Studio](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio2.md)   
 [SqlMetal.exe \(Herramienta de generación de código\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)