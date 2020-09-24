---
title: Implementar la lógica de negocios (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c4577590-7b12-42e1-84a6-95aa2562727e
ms.openlocfilehash: 3d703f7a13f21947fb5d2b5adcac8ae4df6a1547
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158375"
---
# <a name="implementing-business-logic-linq-to-sql"></a><span data-ttu-id="1067a-102">Implementar la lógica de negocios (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="1067a-102">Implementing Business Logic (LINQ to SQL)</span></span>

<span data-ttu-id="1067a-103">El término "lógica empresarial" de este tema se refiere a cualquier regla personalizada o prueba de validación que se aplica a los datos antes de insertarlos, actualizarlos o eliminarlos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1067a-103">The term "business logic" in this topic refers to any custom rules or validation tests that you apply to data before it is inserted, updated or deleted from the database.</span></span> <span data-ttu-id="1067a-104">La lógica empresarial también se conoce a veces como "reglas de empresa" o "lógica del dominio".</span><span class="sxs-lookup"><span data-stu-id="1067a-104">Business logic is also sometimes referred to as "business rules" or "domain logic."</span></span> <span data-ttu-id="1067a-105">En aplicaciones de n niveles, se diseña generalmente como una capa lógica para que se pueda modificar independientemente de la capa de presentación o de la capa de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="1067a-105">In n-tier applications it is typically designed as a logical layer so that it can be modified independently of the presentation layer or data access layer.</span></span> <span data-ttu-id="1067a-106">La capa de acceso a datos puede invocar la lógica empresarial antes o después de cualquier actualización, inserción o eliminación de datos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1067a-106">The business logic can be invoked by the data access layer before or after any update, insertion, or deletion of data in the database.</span></span>  
  
 <span data-ttu-id="1067a-107">La lógica empresarial puede ser tan simple como una validación del esquema para asegurarse de que el tipo del campo es compatible con el tipo de la columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1067a-107">The business logic can be as simple as a schema validation to make sure that the type of the field is compatible with the type of the table column.</span></span> <span data-ttu-id="1067a-108">Por el contrario, también puede estar compuesta por un conjunto de objetos que interactúan con diversos grados de complejidad.</span><span class="sxs-lookup"><span data-stu-id="1067a-108">Or it can consist of a set of objects that interact in arbitrarily complex ways.</span></span> <span data-ttu-id="1067a-109">Las reglas se pueden implementar como procedimientos almacenados en la base de datos o como objetos en memoria.</span><span class="sxs-lookup"><span data-stu-id="1067a-109">The rules may be implemented as stored procedures on the database or as in-memory objects.</span></span> <span data-ttu-id="1067a-110">Sin embargo, se implementa la lógica [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de negocios, que permite usar clases parciales y métodos parciales para separar la lógica de negocios del código de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="1067a-110">However the business logic is implemented, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] enables you use partial classes and partial methods to separate the business logic from the data access code.</span></span>  
  
## <a name="how-linq-to-sql-invokes-your-business-logic"></a><span data-ttu-id="1067a-111">Invocación de la lógica empresarial desde LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1067a-111">How LINQ to SQL Invokes Your Business Logic</span></span>  

 <span data-ttu-id="1067a-112">Cuando se genera una clase de entidad en tiempo de diseño, ya sea manualmente o mediante el Object Relational Designer o SQLMetal, se define como una clase parcial.</span><span class="sxs-lookup"><span data-stu-id="1067a-112">When you generate an entity class at design time, either manually or by using the Object Relational Designer or SQLMetal, it is defined as a partial class.</span></span> <span data-ttu-id="1067a-113">Esto significa que puede definir, en un archivo de código independiente, otra parte de la clase de entidad que contiene su lógica empresarial personalizada.</span><span class="sxs-lookup"><span data-stu-id="1067a-113">This means that, in a separate code file, you can define another part of the entity class that contains your custom business logic.</span></span> <span data-ttu-id="1067a-114">En tiempo de compilación, las dos partes se combinan en una única clase.</span><span class="sxs-lookup"><span data-stu-id="1067a-114">At compile time, the two parts are merged into a single class.</span></span> <span data-ttu-id="1067a-115">Pero si tiene que volver a generar las clases de entidad mediante el Object Relational Designer o SQLMetal, puede hacerlo y su parte de la clase no se modificará.</span><span class="sxs-lookup"><span data-stu-id="1067a-115">But if you have to regenerate your entity classes by using the Object Relational Designer or SQLMetal, you can do so and your part of the class will not be modified.</span></span>  
  
 <span data-ttu-id="1067a-116">Las clases parciales que definen las entidades y el <xref:System.Data.Linq.DataContext> contienen métodos parciales.</span><span class="sxs-lookup"><span data-stu-id="1067a-116">The partial classes that define entities and the <xref:System.Data.Linq.DataContext> contain partial methods.</span></span> <span data-ttu-id="1067a-117">Éstos son los puntos de extensibilidad que puede utilizar para aplicar su lógica empresarial antes y después de cualquier actualización, inserción o eliminación para una entidad o propiedad de entidad.</span><span class="sxs-lookup"><span data-stu-id="1067a-117">These are the extensibility points that you can use to apply your business logic before and after any update, insert, or delete for an entity or entity property.</span></span> <span data-ttu-id="1067a-118">Los métodos parciales se pueden ver como eventos de tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1067a-118">Partial methods can be thought of as compile-time events.</span></span> <span data-ttu-id="1067a-119">El generador de código define una firma de método y llama a los métodos de los descriptores de acceso get y set de la propiedad, al constructor `DataContext` y, en algunos casos, en segundo plano, se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="1067a-119">The code-generator defines a method signature and calls the methods in the get and set property accessors, the `DataContext` constructor, and in some cases behind the scenes when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="1067a-120">Sin embargo, si no implementa un método parcial particular, entonces su definición y todas las referencias a él se eliminan en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1067a-120">However, if you do not implement a particular partial method, then all the references to it and the definition are removed at compile time.</span></span>  
  
 <span data-ttu-id="1067a-121">En la definición de la implementación que escriba en su archivo de código independiente, puede ejecutar cualquier lógica personalizada que requiera.</span><span class="sxs-lookup"><span data-stu-id="1067a-121">In the implementing definition that you write in your separate code file, you can perform whatever custom logic is required.</span></span> <span data-ttu-id="1067a-122">Puede utilizar su clase parcial por sí misma como la capa de dominio, o puede llamar desde la definición de implementación del método parcial a un objeto o varios objetos independientes.</span><span class="sxs-lookup"><span data-stu-id="1067a-122">You can use your partial class itself as your domain layer, or you can call from your implementing definition of the partial method into a separate object or objects.</span></span> <span data-ttu-id="1067a-123">De cualquier modo, su lógica empresarial se separa limpiamente de su código de acceso a datos y de su código de la capa de presentación.</span><span class="sxs-lookup"><span data-stu-id="1067a-123">Either way, your business logic is cleanly separated from both your data access code and your presentation layer code.</span></span>  
  
## <a name="a-closer-look-at-the-extensibility-points"></a><span data-ttu-id="1067a-124">Examen más detallado de los puntos de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="1067a-124">A Closer Look at the Extensibility Points</span></span>  

 <span data-ttu-id="1067a-125">En el ejemplo siguiente se muestra parte del código generado por el Object Relational Designer para la `DataContext` clase que tiene dos tablas: `Customers` y `Orders` .</span><span class="sxs-lookup"><span data-stu-id="1067a-125">The following example shows part of the code generated by the Object Relational Designer for the `DataContext` class that has two tables: `Customers` and `Orders`.</span></span> <span data-ttu-id="1067a-126">Observe que se definen métodos Insert, Update y Delete para cada tabla de la clase.</span><span class="sxs-lookup"><span data-stu-id="1067a-126">Note that Insert, Update, and Delete methods are defined for each table in the class.</span></span>  
  
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
  
 <span data-ttu-id="1067a-127">Si implementa los métodos Insert, Update y Delete en su clase parcial, el motor de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] los llamará en lugar de sus propios métodos predeterminados al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="1067a-127">If you implement the Insert, Update and Delete methods in your partial class, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime will call them instead of its own default methods when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="1067a-128">Esto permite invalidar el comportamiento predeterminado para las operaciones de crear, leer, actualizar y eliminar datos.</span><span class="sxs-lookup"><span data-stu-id="1067a-128">This enables you to override the default behavior for create / read / update / delete operations.</span></span> <span data-ttu-id="1067a-129">Para obtener más información, vea [Tutorial: personalizar el comportamiento de inserción, actualización y eliminación de las clases de entidad](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).</span><span class="sxs-lookup"><span data-stu-id="1067a-129">For more information, see [Walkthrough: Customizing the insert, update, and delete behavior of entity classes](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).</span></span>  
  
 <span data-ttu-id="1067a-130">Al método `OnCreated` se le llama en el constructor de la clase.</span><span class="sxs-lookup"><span data-stu-id="1067a-130">The `OnCreated` method is called in the class constructor.</span></span>  
  
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
  
 <span data-ttu-id="1067a-131">Las clases de entidad tienen tres métodos a los que llama el motor de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] al crear, cargar y validar la entidad (cuando se llama a `SubmitChanges`).</span><span class="sxs-lookup"><span data-stu-id="1067a-131">The entity classes have three methods that are called by the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime when the entity is created, loaded, and validated (when `SubmitChanges` is called).</span></span> <span data-ttu-id="1067a-132">Las clases de entidad también tienen dos métodos parciales para cada propiedad, uno al que se llama antes de que se establezca la propiedad y otro al que se llama después.</span><span class="sxs-lookup"><span data-stu-id="1067a-132">The entity classes also have two partial methods for each property, one that is called before the property is set, and one that is called after.</span></span> <span data-ttu-id="1067a-133">En el ejemplo de código siguiente se muestran algunos de los métodos generados por la clase `Customer`.</span><span class="sxs-lookup"><span data-stu-id="1067a-133">The following code example shows some of the methods generated for the `Customer` class:</span></span>  
  
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
  
 <span data-ttu-id="1067a-134">Se llama a los métodos en el descriptor de acceso set de la propiedad, como se muestra en el ejemplo siguiente para la propiedad `CustomerID`:</span><span class="sxs-lookup"><span data-stu-id="1067a-134">The methods are called in the property set accessor as shown in the following example for the `CustomerID` property:</span></span>  
  
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
  
 <span data-ttu-id="1067a-135">En su parte de la clase, escriba una definición de implementación del método.</span><span class="sxs-lookup"><span data-stu-id="1067a-135">In your part of the class, you write an implementing definition of the method.</span></span> <span data-ttu-id="1067a-136">En Visual Studio, después de escribir, `partial` verá IntelliSense para las definiciones de método en la otra parte de la clase.</span><span class="sxs-lookup"><span data-stu-id="1067a-136">In Visual Studio, after you type `partial` you will see IntelliSense for the method definitions in the other part of the class.</span></span>  
  
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
  
 <span data-ttu-id="1067a-137">Para obtener más información sobre cómo agregar lógica empresarial a su aplicación utilizando métodos parciales, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1067a-137">For more information about how to add business logic to your application by using partial methods, see the following topics:</span></span>  
  
 [<span data-ttu-id="1067a-138">Cómo: Agregar validación a clases de entidad</span><span class="sxs-lookup"><span data-stu-id="1067a-138">How to: Add validation to entity classes</span></span>](/visualstudio/data-tools/how-to-add-validation-to-entity-classes)  
  
 [<span data-ttu-id="1067a-139">Tutorial: Personalizar el comportamiento de inserción, actualización y eliminación de las clases de entidad</span><span class="sxs-lookup"><span data-stu-id="1067a-139">Walkthrough: Customizing the insert, update, and delete behavior of entity classes</span></span>](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes)  
  
 <span data-ttu-id="1067a-140">[Tutorial: Agregar validación a clases de entidad](/previous-versions/visualstudio/visual-studio-2013/bb629301(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1067a-140">[Walkthrough: Adding Validation to Entity Classes](/previous-versions/visualstudio/visual-studio-2013/bb629301(v=vs.120))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1067a-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="1067a-141">See also</span></span>

- [<span data-ttu-id="1067a-142">Clases y métodos parciales</span><span class="sxs-lookup"><span data-stu-id="1067a-142">Partial Classes and Methods</span></span>](../../../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)
- [<span data-ttu-id="1067a-143">Métodos parciales</span><span class="sxs-lookup"><span data-stu-id="1067a-143">Partial Methods</span></span>](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
- [<span data-ttu-id="1067a-144">Herramientas LINQ to SQL en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1067a-144">LINQ to SQL Tools in Visual Studio</span></span>](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [<span data-ttu-id="1067a-145">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="1067a-145">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
