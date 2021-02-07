---
description: 'Más información acerca de: referencias a objetos'
title: Referencias a objetos
ms.date: 03/30/2017
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
ms.openlocfilehash: ae76cf13b4ccbbde2ad6d5022248bbcfeb263879
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732415"
---
# <a name="object-references"></a><span data-ttu-id="c5abe-103">Referencias a objetos</span><span class="sxs-lookup"><span data-stu-id="c5abe-103">Object References</span></span>

<span data-ttu-id="c5abe-104">En este ejemplo se muestra cómo pasar los objetos por referencias entre el servidor y cliente.</span><span class="sxs-lookup"><span data-stu-id="c5abe-104">This sample demonstrates how to pass objects by references between server and client.</span></span> <span data-ttu-id="c5abe-105">En el ejemplo se usan *redes sociales* simuladas.</span><span class="sxs-lookup"><span data-stu-id="c5abe-105">The sample uses simulated *social networks*.</span></span> <span data-ttu-id="c5abe-106">Una red social está compuesta de una clase `Person` que contiene una lista de amigos en la que cada amigo es una instancia de la clase `Person`, con su propia lista de amigos.</span><span class="sxs-lookup"><span data-stu-id="c5abe-106">A social network consists of a `Person` class that contains a list of friends in which each friend is an instance of the `Person` class, with its own list of friends.</span></span> <span data-ttu-id="c5abe-107">Esto crea un gráfico de objetos.</span><span class="sxs-lookup"><span data-stu-id="c5abe-107">This creates a graph of objects.</span></span> <span data-ttu-id="c5abe-108">El servicio expone las operaciones en estas redes sociales.</span><span class="sxs-lookup"><span data-stu-id="c5abe-108">The service exposes operations on these social networks.</span></span>  
  
 <span data-ttu-id="c5abe-109">En este ejemplo, el cliente es una aplicación de consola (.exe) e Internet Information Services (IIS) hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="c5abe-109">In this sample, the service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5abe-110">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="c5abe-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="c5abe-111">Servicio</span><span class="sxs-lookup"><span data-stu-id="c5abe-111">Service</span></span>  

 <span data-ttu-id="c5abe-112">La clase `Person` tiene el atributo <xref:System.Runtime.Serialization.DataContractAttribute> aplicado, con el campo <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> establecido como `true` para declararlo como un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="c5abe-112">The `Person` class has the <xref:System.Runtime.Serialization.DataContractAttribute> attribute applied, with the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> field set to `true` to declare it as a reference type.</span></span> <span data-ttu-id="c5abe-113">Todas las propiedades tienen el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> aplicado.</span><span class="sxs-lookup"><span data-stu-id="c5abe-113">All properties have the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute applied.</span></span>  
  
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
  
 <span data-ttu-id="c5abe-114">La operación `GetPeopleInNetwork` toma un parámetro de tipo `Person` y devuelve a todas las personas en la red; es decir, todas las personas de la lista `friends`, los amigos de cada amigo, etc., sin duplicados.</span><span class="sxs-lookup"><span data-stu-id="c5abe-114">The `GetPeopleInNetwork` operation takes a parameter of type `Person` and returns all the people in the network; that is, all the people in the `friends` list, the friend's friends, and so on, without duplicates.</span></span>  
  
```csharp
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 <span data-ttu-id="c5abe-115">La operación `GetMutualFriends` toma un parámetro de tipo `Person` y devuelve a todos los amigos de la lista que también tienen a esta persona en su lista `friends`.</span><span class="sxs-lookup"><span data-stu-id="c5abe-115">The `GetMutualFriends` operation takes a parameter of type `Person` and returns all the friends in the list who also have this person in their `friends` list.</span></span>  
  
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
  
 <span data-ttu-id="c5abe-116">La operación `GetCommonFriends` toma una lista de tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="c5abe-116">The `GetCommonFriends` operation takes a list of type `Person`.</span></span> <span data-ttu-id="c5abe-117">Se espera que la lista contenga dos objetos `Person`.</span><span class="sxs-lookup"><span data-stu-id="c5abe-117">The list is expected to have two `Person` objects in it.</span></span> <span data-ttu-id="c5abe-118">La operación devuelve una lista de los objetos `Person` que están en las listas `friends` de ambos objetos `Person` en la lista de entrada.</span><span class="sxs-lookup"><span data-stu-id="c5abe-118">The operation returns a list of `Person` objects that are in the `friends` lists of both `Person` objects in the input list.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="c5abe-119">Cliente</span><span class="sxs-lookup"><span data-stu-id="c5abe-119">Client</span></span>  

 <span data-ttu-id="c5abe-120">El proxy de cliente se crea con la característica **Agregar referencia de servicio** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c5abe-120">The client proxy is created using the **Add Service Reference** feature of Visual Studio.</span></span>  
  
 <span data-ttu-id="c5abe-121">Se crea una red social que está compuesta de cinco objetos `Person`.</span><span class="sxs-lookup"><span data-stu-id="c5abe-121">A social network that consists of five `Person` objects is created.</span></span> <span data-ttu-id="c5abe-122">El cliente llama a cada uno de los tres métodos del servicio.</span><span class="sxs-lookup"><span data-stu-id="c5abe-122">The client calls each of the three methods in the service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c5abe-123">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5abe-123">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c5abe-124">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c5abe-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="c5abe-125">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c5abe-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="c5abe-126">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c5abe-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c5abe-127">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c5abe-127">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c5abe-128">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="c5abe-128">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c5abe-129">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c5abe-129">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c5abe-130">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="c5abe-130">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a><span data-ttu-id="c5abe-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5abe-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- [<span data-ttu-id="c5abe-132">Referencias a objetos interoperables</span><span class="sxs-lookup"><span data-stu-id="c5abe-132">Interoperable Object References</span></span>](../feature-details/interoperable-object-references.md)
