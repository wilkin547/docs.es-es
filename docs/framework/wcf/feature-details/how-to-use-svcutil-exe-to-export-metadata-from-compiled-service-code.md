---
title: Procedimiento para usar Svcutil.exe para exportar metadatos desde el código de servicio compilado
ms.date: 03/30/2017
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
ms.openlocfilehash: f60d0c9ad3f6fc4e9596d466b5eabdaab0f4822f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280616"
---
# <a name="how-to-use-svcutilexe-to-export-metadata-from-compiled-service-code"></a><span data-ttu-id="11df9-102">Procedimiento para usar Svcutil.exe para exportar metadatos desde el código de servicio compilado</span><span class="sxs-lookup"><span data-stu-id="11df9-102">How to: Use Svcutil.exe to Export Metadata from Compiled Service Code</span></span>

<span data-ttu-id="11df9-103">Svcutil.exe puede exportar metadatos para los servicios, contratos y tipos de datos en ensamblados compilados del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="11df9-103">Svcutil.exe can export metadata for services, contracts, and data types in compiled assemblies, as follows:</span></span>  
  
- <span data-ttu-id="11df9-104">Para exportar los metadatos para todos los contratos de servicios compilados para un conjunto de ensamblados utilizando Svcutil.exe, especifique los ensamblados como parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="11df9-104">To export metadata for all compiled service contracts for a set of assemblies using Svcutil.exe, specify the assemblies as input parameters.</span></span> <span data-ttu-id="11df9-105">Éste es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="11df9-105">This is the default behavior.</span></span>  
  
- <span data-ttu-id="11df9-106">Para exportar los metadatos para un servicio compilado utilizando Svcutil.exe, especifique el ensamblado de servicio o ensamblados como parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="11df9-106">To export metadata for a compiled service using Svcutil.exe, specify the service assembly or assemblies as input parameters.</span></span> <span data-ttu-id="11df9-107">Debe utilizar la opción `/serviceName` para indicar el nombre de configuración del servicio que quiere exportar.</span><span class="sxs-lookup"><span data-stu-id="11df9-107">You must use the `/serviceName` option to indicate the configuration name of the service you want to export.</span></span> <span data-ttu-id="11df9-108">Svcutil.exe carga automáticamente el archivo de configuración para el ensamblado ejecutable especificado.</span><span class="sxs-lookup"><span data-stu-id="11df9-108">Svcutil.exe automatically loads the configuration file for the specified executable assembly.</span></span>  
  
- <span data-ttu-id="11df9-109">Para exportar todos los tipos de contrato de datos dentro de un conjunto de ensamblados, utilice la opción `/dataContractOnly`.</span><span class="sxs-lookup"><span data-stu-id="11df9-109">To export all data contract types within a set of assemblies, use the `/dataContractOnly` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11df9-110">Utilice la opción `/reference` para especificar las rutas de acceso del archivo a cualquier ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="11df9-110">Use the `/reference` option to specify the file paths to any dependent assemblies.</span></span>  
  
### <a name="to-export-metadata-for-compiled-service-contracts"></a><span data-ttu-id="11df9-111">Para exportar los metadatos para los contratos de servicios compilados</span><span class="sxs-lookup"><span data-stu-id="11df9-111">To export metadata for compiled service contracts</span></span>  
  
1. <span data-ttu-id="11df9-112">Compile sus implementaciones del contrato de servicios en una o más bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="11df9-112">Compile your service contract implementations into one or more class libraries.1</span></span>  
  
2. <span data-ttu-id="11df9-113">Ejecute Svcutil.exe en los ensamblados compilados.</span><span class="sxs-lookup"><span data-stu-id="11df9-113">Run Svcutil.exe on the compiled assemblies.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="11df9-114">Quizás necesite utilizar el modificador `/reference` para especificar la ruta de acceso del archivo a cualquier ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="11df9-114">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```console
    svcutil.exe Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-a-compiled-service"></a><span data-ttu-id="11df9-115">Para exportar los metadatos para un servicio compilado</span><span class="sxs-lookup"><span data-stu-id="11df9-115">To export metadata for a compiled service</span></span>  
  
1. <span data-ttu-id="11df9-116">Compile su implementación del servicio en un ensamblado ejecutable.</span><span class="sxs-lookup"><span data-stu-id="11df9-116">Compile your service implementation into an executable assembly.</span></span>  
  
2. <span data-ttu-id="11df9-117">Cree un archivo de configuración para su ejecutable de servicio y agregue una configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="11df9-117">Create a configuration file for your service executable and add a service configuration.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="MyService" >  
            <endpoint address="finder" contract="IPeopleFinder" binding="wsHttpBinding" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
3. <span data-ttu-id="11df9-118">Ejecute Svcutil.exe en el ejecutable de servicio compilado utilizando el modificador `/serviceName` para especificar el nombre de configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="11df9-118">Run Svcutil.exe on the compiled service executable using the `/serviceName` switch to specify the configuration name of the service.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="11df9-119">Quizás necesite utilizar el modificador `/reference` para especificar la ruta de acceso del archivo a cualquier ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="11df9-119">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```console  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-compiled-data-contracts"></a><span data-ttu-id="11df9-120">Para exportar los metadatos para los contratos de datos compilados</span><span class="sxs-lookup"><span data-stu-id="11df9-120">To export metadata for compiled data contracts</span></span>  
  
1. <span data-ttu-id="11df9-121">Compile sus implementaciones del contrato de datos en una o más bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="11df9-121">Compile your data contract implementations into one or more class libraries.</span></span>  
  
2. <span data-ttu-id="11df9-122">Ejecute Svcutil.exe en los ensamblados compilados utilizando el modificador `/dataContract` para especificar que solo se deberían generar los metadatos para los contratos de datos.</span><span class="sxs-lookup"><span data-stu-id="11df9-122">Run Svcutil.exe on the compiled assemblies using the `/dataContract` switch to specify that only metadata for data contracts should be generated.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="11df9-123">Quizás necesite utilizar el modificador `/reference` para especificar la ruta de acceso del archivo a cualquier ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="11df9-123">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```console  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## <a name="example"></a><span data-ttu-id="11df9-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11df9-124">Example</span></span>  

 <span data-ttu-id="11df9-125">El ejemplo siguiente muestra cómo generar los metadatos para una implementación de servicio simple y configuración.</span><span class="sxs-lookup"><span data-stu-id="11df9-125">The following example demonstrates how to generate metadata for a simple service implementation and configuration.</span></span>  
  
 <span data-ttu-id="11df9-126">Para exportar los metadatos para el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="11df9-126">To export metadata for the service contract.</span></span>  
  
```console  
svcutil.exe Contracts.dll  
```  
  
 <span data-ttu-id="11df9-127">Para exportar los metadatos para los contratos de datos.</span><span class="sxs-lookup"><span data-stu-id="11df9-127">To export metadata for the data contracts.</span></span>  
  
```console  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 <span data-ttu-id="11df9-128">Para exportar los metadatos para la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="11df9-128">To export metadata for the service implementation.</span></span>  
  
```console  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 <span data-ttu-id="11df9-129">`<path>` es la ruta de acceso a Contracts.dll.</span><span class="sxs-lookup"><span data-stu-id="11df9-129">The `<path>` is the path to Contracts.dll.</span></span>  
  
```csharp
// The following service contract and data contracts are compiled into
// Contracts.dll.  
[ServiceContract(ConfigurationName="IPeopleFinder")]  
public interface IPersonFinder  
{  
    [OperationContract]  
    Address GetAddress(Person s);  
}  
  
[DataContract]  
public class Person  
{  
    [DataMember]  
    public string firstName;  
    [DataMember]  
    public string lastName;  
    [DataMember]  
    public int age;  
}  
  
[DataContract]  
public class Address  
{  
    [DataMember]  
    public string city;  
    [DataMember]  
    public string state;  
    [DataMember]  
    public string street;  
    [DataMember]  
    public int zipCode;  
    [DataMember]  
    public Person person;  
}  
```

```csharp
// The following service implementation is compiled into Service.exe.
// This service uses the contracts specified in Contracts.dll.  
[ServiceBehavior(ConfigurationName = "MyService")]  
public class MyService : IPersonFinder  
{  
    public Address GetAddress(Person person)  
    {  
        Address address = new Address();  
        address.person = person;  
        return address;  
    }  
}  
```

```xml  
<!-- The following is the configuration file for Service.exe. -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="MyService">  
         <endpoint  address="finder"  
                    binding="basicHttpBinding"  
                    contract="IPeopleFinder"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="11df9-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="11df9-130">See also</span></span>

- [<span data-ttu-id="11df9-131">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="11df9-131">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="11df9-132">Exportación e importación de metadatos</span><span class="sxs-lookup"><span data-stu-id="11df9-132">Exporting and Importing Metadata</span></span>](exporting-and-importing-metadata.md)
