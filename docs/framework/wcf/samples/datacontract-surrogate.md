---
title: Suplente de DataContract
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0188f3c-00a9-4cf0-a887-a2284c8fb014
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ffb8ec71d6a8bbbdf365b78ad13af7524cc33ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="datacontract-surrogate"></a>Suplente de DataContract
Este ejemplo muestra cómo se pueden personalizar procesos como la serialización, la deserialización, la exportación e importación del esquema mediante una clase suplente de contrato de datos. Este ejemplo muestra cómo utilizar un suplente en un escenario de cliente y servidor donde los datos se serializan y transmiten entre un cliente y un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El ejemplo utiliza el siguiente contrato de servicio:  
  
```  
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
  
 La operación `AddEmployee` permite a los usuarios agregar datos sobre nuevos empleados y la operación `GetEmployee` admite la búsqueda de empleados basada en nombre.  
  
 Estas operaciones utilizan el tipo de datos siguiente:  
  
```  
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
  
 En el tipo `Employee` , la clase `Person` (mostrada en el siguiente código de ejemplo) no puede ser serializada por <xref:System.Runtime.Serialization.DataContractSerializer> porque no es una clase de contrato de datos válida.  
  
```  
public class Person  
{  
    public string firstName;  
  
    public string lastName;  
  
    public int age;  
  
    public Person() { }  
}  
```  
  
 Puede aplicar el atributo `DataContract` a la clase `Person`, pero esto es no siempre posible. Por ejemplo, la clase `Person` se puede definir en un ensamblado independiente sobre el que no tiene ningún control.  
  
 Dada esta restricción, una manera de serializar la clase `Person` es sustituirla con otra clase que se marca con `DataContractAttribute` y copiar los datos necesarios en la nueva clase. El objetivo es hacer que la clase `Person` aparezca como un DataContract a <xref:System.Runtime.Serialization.DataContractSerializer>. Tenga en cuenta que se trata de una manera de serializar las clases de contrato de no datos.  
  
 El ejemplo reemplaza lógicamente la clase `Person` con una clase diferente denominada `PersonSurrogated`.  
  
```  
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
  
 El suplente del contrato de datos se utiliza para lograr este reemplazo. Un suplente del contrato de datos es una clase que implementa <xref:System.Runtime.Serialization.IDataContractSurrogate>. En este ejemplo, la clase `AllowNonSerializableTypesSurrogate`implementa este interfaz.  
  
 En la implementación de interfaces, la primera tarea es establecer una asignación de tipo de `Person` a `PersonSurrogated`. Esto se utiliza tanto a la hora de serializar como a la de exportar esquemas. Esta asignación se logra implementando el método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29>.  
  
```  
public Type GetDataContractType(Type type)  
{  
    if (typeof(Person).IsAssignableFrom(type))  
    {  
        return typeof(PersonSurrogated);  
    }  
    return type;  
}  
```  
  
 El método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> asigna una instancia `Person` a una instancia `PersonSurrogated` durante la serialización, como se muestra en el código muestra siguiente.  
  
```  
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
  
 El método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> proporciona la asignación inversa para la deserialización, como se muestra en el código muestra siguiente.  
  
```  
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
  
 Para asignar el contrato de datos `PersonSurrogated` a la clase `Person` existente durante la importación del esquema, el ejemplo implementa el método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29>, como se muestra en el código muestra siguiente.  
  
```  
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
  
 El siguiente código muestra completa la implementación de la interfaz <xref:System.Runtime.Serialization.IDataContractSurrogate>.  
  
```  
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
  
 En este ejemplo, el suplente está habilitado en ServiceModel por un atributo llamado `AllowNonSerializableTypesAttribute`. Los programadores necesitarían aplicar este atributo en su contrato de servicios como se muestra en el contrato de servicios anterior `IPersonnelDataService`. Este atributo implementa `IContractBehavior` y establece el suplente en operaciones en su`ApplyClientBehavior` y métodos `ApplyDispatchBehavior`.  
  
 El atributo no es necesario en este caso - se utiliza como demostración en este ejemplo. Los usuarios pueden habilitar alternativamente un suplente agregando manualmente un `IContractBehavior`similar, `IEndpointBehavior` o `IOperationBehavior` utilizando código o utilizando la configuración.  
  
 La implementación `IContractBehavior` busca operaciones que utilizan DataContract comprobando si tienen `DataContractSerializerOperationBehavior` registrado. Si lo tienen, establece la propiedad `DataContractSurrogate` en ese comportamiento. En el siguiente código de muestra se explica cómo se hace. Establecer el suplente en este comportamiento de la operación lo habilita para la serialización y deserialización.  
  
```  
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
  
 Se necesitan dar pasos adicionales para conectar el suplente para su uso durante la generación de metadatos. Un mecanismo para ello es proporcionar un `IWsdlExportExtension` que es lo que este ejemplo muestra. Otra manera es modificar directamente `WsdlExporter`.  
  
 El `AllowNonSerializableTypesAttribute` atributo implementa `IWsdlExportExtension` y `IContractBehavior`. La extensión puede ser un `IContractBehavior` o `IEndpointBehavior` en este caso. Su implementación de método `IWsdlExportExtension.ExportContract` habilita el suplente agregándolo a `XsdDataContractExporter` usado durante la generación del esquema para DataContract. El siguiente fragmento de código muestra cómo hacerlo:  
  
```  
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
  
 Al ejecutar el ejemplo, el cliente llama AddEmployee seguido por una llamada a GetEmployee para comprobar si la primera llamada tuvo éxito. El resultado de la solicitud de operación de GetEmployee se muestra en la ventana de la consola del cliente. La operación de GetEmployee debe tener éxito al buscar al empleado e imprimir "encontrado".  
  
> [!NOTE]
>  Este ejemplo muestra cómo conectar un suplente para serializar, deserializar y generar metadatos. No muestra cómo conectar un suplente para la generación de código a partir de metadatos. Para ver un ejemplo de cómo se puede utilizar un suplente para conectar a la generación de código de cliente, consulte la [publicación de WSDL personalizado](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) ejemplo.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar la edición de C# de la solución, siga las instrucciones que aparecen en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DataContract`  
  
## <a name="see-also"></a>Vea también
