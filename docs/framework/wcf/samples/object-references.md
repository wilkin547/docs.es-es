---
title: Referencias a objetos
ms.date: 03/30/2017
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
ms.openlocfilehash: bc9c318fc0e05f384a00df7cd1436a138315d880
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714679"
---
# <a name="object-references"></a>Referencias a objetos
En este ejemplo se muestra cómo pasar los objetos por referencias entre el servidor y cliente. En el ejemplo se usan *redes sociales*simuladas. Una red social está compuesta de una clase `Person` que contiene una lista de amigos en la que cada amigo es una instancia de la clase `Person`, con su propia lista de amigos. Esto crea un gráfico de objetos. El servicio expone las operaciones en estas redes sociales.  
  
 En este ejemplo, el cliente es una aplicación de consola (.exe) e Internet Information Services (IIS) hospeda el servicio.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
## <a name="service"></a>Servicio  
 La clase `Person` tiene el atributo <xref:System.Runtime.Serialization.DataContractAttribute> aplicado, con el campo <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> establecido como `true` para declararlo como un tipo de referencia. Todas las propiedades tienen el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> aplicado.  
  
```csharp
[DataContract(IsReference=true)]  
public class Person  
{  
    string name;  
    string location;  
    string gender;  
    int age;  
    List<Person> friends;  
    [DataMember()]  
    public string Name  
    {  
        get { return name; }  
        set { name = value; }  
    }  
    [DataMember()]  
    public string Location  
    {  
        get { return location; }  
        set { location = value; }  
    }  
    [DataMember()]  
    public string Gender  
    {  
        get { return gender; }  
        set { gender = value; }  
    }  
…  
}  
```  
  
 La operación `GetPeopleInNetwork` toma un parámetro de tipo `Person` y devuelve a todas las personas en la red; es decir, todas las personas de la lista `friends`, los amigos de cada amigo, etc., sin duplicados.  
  
```csharp
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 La operación `GetMutualFriends` toma un parámetro de tipo `Person` y devuelve a todos los amigos de la lista que también tienen a esta persona en su lista `friends`.  
  
```csharp
public List<Person> GetMutualFriends(Person p)  
{  
    List<Person> mutual = new List<Person>();  
    foreach (Person friend in p.Friends)  
    {  
        if (friend.Friends.Contains(p))  
            mutual.Add(friend);  
    }  
    return mutual;  
}  
```  
  
 La operación `GetCommonFriends` toma una lista de tipo `Person`. Se espera que la lista contenga dos objetos `Person`. La operación devuelve una lista de los objetos `Person` que están en las listas `friends` de ambos objetos `Person` en la lista de entrada.  
  
```csharp
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## <a name="client"></a>Client  
 El proxy de cliente se crea con la característica **Agregar referencia de servicio** de Visual Studio.  
  
 Se crea una red social que está compuesta de cinco objetos `Person`. El cliente llama a cada uno de los tres métodos del servicio.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- [Referencias a objetos interoperables](../../../../docs/framework/wcf/feature-details/interoperable-object-references.md)
