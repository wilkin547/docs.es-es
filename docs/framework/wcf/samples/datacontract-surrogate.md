---
description: 'Más información sobre: el suplente de DataContract'
title: Suplente de DataContract
ms.date: 03/30/2017
ms.assetid: b0188f3c-00a9-4cf0-a887-a2284c8fb014
ms.openlocfilehash: 739471efcea1d04752f3065c7a28f55f9ff9a0f8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755829"
---
# <a name="datacontract-surrogate"></a><span data-ttu-id="dc004-103">Suplente de DataContract</span><span class="sxs-lookup"><span data-stu-id="dc004-103">DataContract Surrogate</span></span>

<span data-ttu-id="dc004-104">Este ejemplo muestra cómo se pueden personalizar procesos como la serialización, la deserialización, la exportación e importación del esquema mediante una clase suplente de contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="dc004-104">This sample demonstrates how processes like serialization, deserialization, schema export, and schema import can be customized using a data contract surrogate class.</span></span> <span data-ttu-id="dc004-105">En este ejemplo se muestra cómo utilizar un suplente en un escenario de cliente y servidor en el que los datos se serializan y se transmiten entre un servicio y un cliente de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="dc004-105">This sample shows how to use a surrogate in a client and server scenario where data is serialized and transmitted between a Windows Communication Foundation (WCF) client and service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc004-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="dc004-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="dc004-107">El ejemplo utiliza el siguiente contrato de servicio:</span><span class="sxs-lookup"><span data-stu-id="dc004-107">The sample uses the following service contract:</span></span>  
  
```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[AllowNonSerializableTypes]  
public interface IPersonnelDataService  
{  
    [OperationContract]  
    void AddEmployee(Employee employee);  
  
    [OperationContract]  
    Employee GetEmployee(string name);  
}  
```  
  
 <span data-ttu-id="dc004-108">La operación `AddEmployee` permite a los usuarios agregar datos sobre nuevos empleados y la operación `GetEmployee` admite la búsqueda de empleados basada en nombre.</span><span class="sxs-lookup"><span data-stu-id="dc004-108">The `AddEmployee` operation allows users to add data about new employees and the `GetEmployee` operation supports search for employees based on name.</span></span>  
  
 <span data-ttu-id="dc004-109">Estas operaciones utilizan el tipo de datos siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc004-109">These operations use the following data type:</span></span>  
  
```csharp
[DataContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
class Employee  
{  
    [DataMember]  
    public DateTime dateHired;  
  
    [DataMember]  
    public Decimal salary;  
  
    [DataMember]  
    public Person person;  
}  
```  
  
 <span data-ttu-id="dc004-110">En el tipo `Employee` , la clase `Person` (mostrada en el siguiente código de ejemplo) no puede ser serializada por <xref:System.Runtime.Serialization.DataContractSerializer> porque no es una clase de contrato de datos válida.</span><span class="sxs-lookup"><span data-stu-id="dc004-110">In the `Employee` type, the `Person` class (shown in the following sample code) cannot be serialized by the <xref:System.Runtime.Serialization.DataContractSerializer> because it is not a valid data contract class.</span></span>  
  
```csharp
public class Person  
{  
    public string firstName;  
  
    public string lastName;  
  
    public int age;  
  
    public Person() { }  
}  
```  
  
 <span data-ttu-id="dc004-111">Puede aplicar el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a la clase `Person`, pero esto es no siempre posible.</span><span class="sxs-lookup"><span data-stu-id="dc004-111">You can apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the `Person` class, but this is not always possible.</span></span> <span data-ttu-id="dc004-112">Por ejemplo, la clase `Person` se puede definir en un ensamblado independiente sobre el que no tiene ningún control.</span><span class="sxs-lookup"><span data-stu-id="dc004-112">For example, the `Person` class can be defined in a separate assembly over which you have no control.</span></span>  
  
 <span data-ttu-id="dc004-113">Dada esta restricción, una manera de serializar la clase `Person` es sustituirla con otra clase que se marca con <xref:System.Runtime.Serialization.DataContractAttribute> y copiar los datos necesarios en la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="dc004-113">Given this restriction, one way to serialize the `Person` class is to substitute it with another class that is marked with <xref:System.Runtime.Serialization.DataContractAttribute> and copy over necessary data to the new class.</span></span> <span data-ttu-id="dc004-114">El objetivo es hacer que la clase `Person` aparezca como un DataContract a <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="dc004-114">The objective is to make the `Person` class appear as a DataContract to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="dc004-115">Tenga en cuenta que se trata de una manera de serializar las clases de contrato de no datos.</span><span class="sxs-lookup"><span data-stu-id="dc004-115">Note that this is one way to serialize non-data contract classes.</span></span>  
  
 <span data-ttu-id="dc004-116">El ejemplo reemplaza lógicamente la clase `Person` con una clase diferente denominada `PersonSurrogated`.</span><span class="sxs-lookup"><span data-stu-id="dc004-116">The sample logically replaces the `Person` class with a different class named `PersonSurrogated`.</span></span>  
  
```csharp
[DataContract(Name="Person", Namespace = "http://Microsoft.ServiceModel.Samples")]  
public class PersonSurrogated  
{  
    [DataMember]  
    public string FirstName;  
  
    [DataMember]  
    public string LastName;  
  
    [DataMember]  
    public int Age;  
}  
```  
  
 <span data-ttu-id="dc004-117">El suplente del contrato de datos se utiliza para lograr este reemplazo.</span><span class="sxs-lookup"><span data-stu-id="dc004-117">The data contract surrogate is used to achieve this replacement.</span></span> <span data-ttu-id="dc004-118">Un suplente del contrato de datos es una clase que implementa <xref:System.Runtime.Serialization.IDataContractSurrogate>.</span><span class="sxs-lookup"><span data-stu-id="dc004-118">A data contract surrogate is a class that implements <xref:System.Runtime.Serialization.IDataContractSurrogate>.</span></span> <span data-ttu-id="dc004-119">En este ejemplo, la clase `AllowNonSerializableTypesSurrogate`implementa este interfaz.</span><span class="sxs-lookup"><span data-stu-id="dc004-119">In this sample, the `AllowNonSerializableTypesSurrogate` class implements this interface.</span></span>  
  
 <span data-ttu-id="dc004-120">En la implementación de interfaces, la primera tarea es establecer una asignación de tipo de `Person` a `PersonSurrogated`.</span><span class="sxs-lookup"><span data-stu-id="dc004-120">In the interface implementation, the first task is to establish a type mapping from `Person` to `PersonSurrogated`.</span></span> <span data-ttu-id="dc004-121">Esto se utiliza tanto a la hora de serializar como a la de exportar esquemas.</span><span class="sxs-lookup"><span data-stu-id="dc004-121">This is used both at serialization time as well as at schema export time.</span></span> <span data-ttu-id="dc004-122">Esta asignación se logra implementando el método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29>.</span><span class="sxs-lookup"><span data-stu-id="dc004-122">This mapping is achieved by implementing the <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29> method.</span></span>  
  
```csharp
public Type GetDataContractType(Type type)  
{  
    if (typeof(Person).IsAssignableFrom(type))  
    {  
        return typeof(PersonSurrogated);  
    }  
    return type;  
}  
```  
  
 <span data-ttu-id="dc004-123">El método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> asigna una instancia `Person` a una instancia `PersonSurrogated` durante la serialización, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="dc004-123">The <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> method maps a `Person` instance to a `PersonSurrogated` instance during serialization, as shown in the following sample code.</span></span>  
  
```csharp
public object GetObjectToSerialize(object obj, Type targetType)  
{  
    if (obj is Person)  
    {  
        Person person = (Person)obj;  
        PersonSurrogated personSurrogated = new PersonSurrogated();  
        personSurrogated.FirstName = person.firstName;  
        personSurrogated.LastName = person.lastName;  
        personSurrogated.Age = person.age;  
        return personSurrogated;  
    }  
    return obj;  
}  
```  
  
 <span data-ttu-id="dc004-124">El método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> proporciona la asignación inversa para la deserialización, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="dc004-124">The <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> method provides the reverse mapping for deserialization, as shown in the following sample code.</span></span>  
  
```csharp
public object GetDeserializedObject(object obj,
Type targetType)  
{  
    if (obj is PersonSurrogated)  
    {  
        PersonSurrogated personSurrogated = (PersonSurrogated)obj;  
        Person person = new Person();  
        person.firstName = personSurrogated.FirstName;  
        person.lastName = personSurrogated.LastName;  
        person.age = personSurrogated.Age;  
        return person;  
    }  
    return obj;  
}  
```  
  
 <span data-ttu-id="dc004-125">Para asignar el contrato de datos `PersonSurrogated` a la clase `Person` existente durante la importación del esquema, el ejemplo implementa el método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29>, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="dc004-125">To map the `PersonSurrogated` data contract to the existing `Person` class during schema import, the sample implements the <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29> method, as shown in the following sample code.</span></span>  
  
```csharp
public Type GetReferencedTypeOnImport(string typeName,
               string typeNamespace, object customData)  
{  
if (  
typeNamespace.Equals("http://schemas.datacontract.org/2004/07/DCSurrogateSample")  
)  
    {  
         if (typeName.Equals("PersonSurrogated"))  
        {  
             return typeof(Person);  
        }  
     }  
     return null;  
}  
```  
  
 <span data-ttu-id="dc004-126">El siguiente código muestra completa la implementación de la interfaz <xref:System.Runtime.Serialization.IDataContractSurrogate>.</span><span class="sxs-lookup"><span data-stu-id="dc004-126">The following sample code completes the implementation of the <xref:System.Runtime.Serialization.IDataContractSurrogate> interface.</span></span>  
  
```csharp
public System.CodeDom.CodeTypeDeclaration ProcessImportedType(  
          System.CodeDom.CodeTypeDeclaration typeDeclaration,
          System.CodeDom.CodeCompileUnit compileUnit)  
{  
    return typeDeclaration;  
}  
public object GetCustomDataToExport(Type clrType,
                               Type dataContractType)  
{  
    return null;  
}  
  
public object GetCustomDataToExport(  
System.Reflection.MemberInfo memberInfo, Type dataContractType)  
{  
    return null;  
}  
public void GetKnownCustomDataTypes(  
        KnownTypeCollection customDataTypes)  
{  
    // It does not matter what we do here.  
    throw new NotImplementedException();  
}  
```  
  
 <span data-ttu-id="dc004-127">En este ejemplo, el suplente está habilitado en ServiceModel por un atributo llamado `AllowNonSerializableTypesAttribute`.</span><span class="sxs-lookup"><span data-stu-id="dc004-127">In this sample, the surrogate is enabled in ServiceModel by an attribute called `AllowNonSerializableTypesAttribute`.</span></span> <span data-ttu-id="dc004-128">Los programadores necesitarían aplicar este atributo en su contrato de servicios como se muestra en el contrato de servicios anterior `IPersonnelDataService`.</span><span class="sxs-lookup"><span data-stu-id="dc004-128">Developers would need to apply this attribute on their service contract as shown on the `IPersonnelDataService` service contract above.</span></span> <span data-ttu-id="dc004-129">Este atributo implementa `IContractBehavior` y establece el suplente en operaciones en su`ApplyClientBehavior` y métodos `ApplyDispatchBehavior`.</span><span class="sxs-lookup"><span data-stu-id="dc004-129">This attribute implements `IContractBehavior` and sets up the surrogate on operations in its `ApplyClientBehavior` and `ApplyDispatchBehavior` methods.</span></span>  
  
 <span data-ttu-id="dc004-130">El atributo no es necesario en este caso - se utiliza como demostración en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dc004-130">The attribute is not necessary in this case - it is used for demonstration purposes in this sample.</span></span> <span data-ttu-id="dc004-131">Los usuarios pueden habilitar alternativamente un suplente agregando manualmente un `IContractBehavior`similar, `IEndpointBehavior` o `IOperationBehavior` utilizando código o utilizando la configuración.</span><span class="sxs-lookup"><span data-stu-id="dc004-131">Users can alternatively enable a surrogate by manually adding a similar `IContractBehavior`, `IEndpointBehavior` or `IOperationBehavior` using code or using configuration.</span></span>  
  
 <span data-ttu-id="dc004-132">La implementación `IContractBehavior` busca operaciones que utilizan DataContract comprobando si tienen `DataContractSerializerOperationBehavior` registrado.</span><span class="sxs-lookup"><span data-stu-id="dc004-132">The `IContractBehavior` implementation looks for operations that use DataContract by checking if they have a `DataContractSerializerOperationBehavior` registered.</span></span> <span data-ttu-id="dc004-133">Si lo tienen, establece la propiedad `DataContractSurrogate` en ese comportamiento.</span><span class="sxs-lookup"><span data-stu-id="dc004-133">If they do, it sets the `DataContractSurrogate` property on that behavior.</span></span> <span data-ttu-id="dc004-134">En el siguiente código de muestra se explica cómo se hace.</span><span class="sxs-lookup"><span data-stu-id="dc004-134">The following sample code shows how this is done.</span></span> <span data-ttu-id="dc004-135">Establecer el suplente en este comportamiento de la operación lo habilita para la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="dc004-135">Setting the surrogate on this operation behavior enables it for serialization and deserialization.</span></span>  
  
```csharp
public void ApplyClientBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime proxy)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
public void ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatch)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
private static void ApplyDataContractSurrogate(OperationDescription description)  
{  
    DataContractSerializerOperationBehavior dcsOperationBehavior = description.Behaviors.Find<DataContractSerializerOperationBehavior>();  
    if (dcsOperationBehavior != null)  
    {  
        if (dcsOperationBehavior.DataContractSurrogate == null)  
            dcsOperationBehavior.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
    }  
}  
```  
  
 <span data-ttu-id="dc004-136">Se necesitan dar pasos adicionales para conectar el suplente para su uso durante la generación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="dc004-136">Additional steps need to be taken to plug in the surrogate for use during metadata generation.</span></span> <span data-ttu-id="dc004-137">Un mecanismo para ello es proporcionar un `IWsdlExportExtension` que es lo que este ejemplo muestra.</span><span class="sxs-lookup"><span data-stu-id="dc004-137">One mechanism to do this is to provide an `IWsdlExportExtension` which is what this sample demonstrates.</span></span> <span data-ttu-id="dc004-138">Otra manera es modificar directamente `WsdlExporter`.</span><span class="sxs-lookup"><span data-stu-id="dc004-138">Another way is to modify the `WsdlExporter` directly.</span></span>  
  
 <span data-ttu-id="dc004-139">El `AllowNonSerializableTypesAttribute` atributo implementa `IWsdlExportExtension` y `IContractBehavior` .</span><span class="sxs-lookup"><span data-stu-id="dc004-139">The `AllowNonSerializableTypesAttribute` attribute implements `IWsdlExportExtension` and `IContractBehavior`.</span></span> <span data-ttu-id="dc004-140">La extensión puede ser `IContractBehavior` o `IEndpointBehavior` en este caso.</span><span class="sxs-lookup"><span data-stu-id="dc004-140">The extension can be either an `IContractBehavior` or `IEndpointBehavior` in this case.</span></span> <span data-ttu-id="dc004-141">Su implementación de método `IWsdlExportExtension.ExportContract` habilita el suplente agregándolo a `XsdDataContractExporter` usado durante la generación del esquema para DataContract.</span><span class="sxs-lookup"><span data-stu-id="dc004-141">Its `IWsdlExportExtension.ExportContract` method implementation enables the surrogate by adding it to the `XsdDataContractExporter` used during schema generation for DataContract.</span></span> <span data-ttu-id="dc004-142">El siguiente fragmento de código muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="dc004-142">The following code snippet shows how to do this.</span></span>  
  
```csharp
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
{  
    if (exporter == null)  
        throw new ArgumentNullException("exporter");  
  
    object dataContractExporter;  
    XsdDataContractExporter xsdDCExporter;  
    if (!exporter.State.TryGetValue(typeof(XsdDataContractExporter), out dataContractExporter))  
    {  
        xsdDCExporter = new XsdDataContractExporter(exporter.GeneratedXmlSchemas);  
        exporter.State.Add(typeof(XsdDataContractExporter), xsdDCExporter);  
    }  
    else  
    {  
        xsdDCExporter = (XsdDataContractExporter)dataContractExporter;  
    }  
    if (xsdDCExporter.Options == null)  
        xsdDCExporter.Options = new ExportOptions();  
  
    if (xsdDCExporter.Options.DataContractSurrogate == null)  
        xsdDCExporter.Options.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
}  
```  
  
 <span data-ttu-id="dc004-143">Al ejecutar el ejemplo, el cliente llama AddEmployee seguido por una llamada a GetEmployee para comprobar si la primera llamada tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="dc004-143">When you run the sample, the client calls AddEmployee followed by a GetEmployee call to check if the first call was successful.</span></span> <span data-ttu-id="dc004-144">El resultado de la solicitud de operación de GetEmployee se muestra en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="dc004-144">The result of the GetEmployee operation request is displayed in the client console window.</span></span> <span data-ttu-id="dc004-145">La operación GetEmployee debe realizarse correctamente al buscar el empleado e imprimir "encontrado".</span><span class="sxs-lookup"><span data-stu-id="dc004-145">The GetEmployee operation must succeed in finding the employee and print "found".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc004-146">Este ejemplo muestra cómo conectar un suplente para serializar, deserializar y generar metadatos.</span><span class="sxs-lookup"><span data-stu-id="dc004-146">This sample shows how to plug in a surrogate for serialize, deserialize and metadata generation.</span></span> <span data-ttu-id="dc004-147">No muestra cómo conectar un suplente para la generación de código a partir de metadatos.</span><span class="sxs-lookup"><span data-stu-id="dc004-147">It does not show how to plug in a surrogate for code generation from metadata.</span></span> <span data-ttu-id="dc004-148">Para ver un ejemplo de cómo se puede usar un suplente para conectarse a la generación de código de cliente, vea el ejemplo de [publicación de WSDL personalizado](custom-wsdl-publication.md) .</span><span class="sxs-lookup"><span data-stu-id="dc004-148">To see a sample of how a surrogate can be used to plug into client code generation, see the [Custom WSDL Publication](custom-wsdl-publication.md) sample.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dc004-149">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc004-149">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="dc004-150">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dc004-150">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="dc004-151">Para compilar la edición de C# de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dc004-151">To build the C# edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="dc004-152">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dc004-152">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="dc004-153">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="dc004-153">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dc004-154">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="dc004-154">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="dc004-155">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="dc004-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dc004-156">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="dc004-156">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DataContract`  
