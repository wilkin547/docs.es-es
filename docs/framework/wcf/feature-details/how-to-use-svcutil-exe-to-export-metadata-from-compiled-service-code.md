---
title: Procedimiento para usar Svcutil.exe para exportar metadatos desde el código de servicio compilado
ms.date: 03/30/2017
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
ms.openlocfilehash: 9acefdec63a6f518ead6cdbcb19ebc8c75609dd6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595367"
---
# <a name="how-to-use-svcutilexe-to-export-metadata-from-compiled-service-code"></a>Procedimiento para usar Svcutil.exe para exportar metadatos desde el código de servicio compilado
Svcutil.exe puede exportar metadatos para los servicios, contratos y tipos de datos en ensamblados compilados del siguiente modo:  
  
- Para exportar los metadatos para todos los contratos de servicios compilados para un conjunto de ensamblados utilizando Svcutil.exe, especifique los ensamblados como parámetros de entrada. Éste es el comportamiento predeterminado.  
  
- Para exportar los metadatos para un servicio compilado utilizando Svcutil.exe, especifique el ensamblado de servicio o ensamblados como parámetros de entrada. Debe utilizar la opción `/serviceName` para indicar el nombre de configuración del servicio que quiere exportar. Svcutil.exe carga automáticamente el archivo de configuración para el ensamblado ejecutable especificado.  
  
- Para exportar todos los tipos de contrato de datos dentro de un conjunto de ensamblados, utilice la opción `/dataContractOnly`.  
  
> [!NOTE]
> Utilice la opción `/reference` para especificar las rutas de acceso del archivo a cualquier ensamblado dependiente.  
  
### <a name="to-export-metadata-for-compiled-service-contracts"></a>Para exportar los metadatos para los contratos de servicios compilados  
  
1. Compile sus implementaciones del contrato de servicios en una o más bibliotecas de clases.  
  
2. Ejecute Svcutil.exe en los ensamblados compilados.  
  
    > [!NOTE]
    > Quizás necesite utilizar el modificador `/reference` para especificar la ruta de acceso del archivo a cualquier ensamblado dependiente.  
  
    ```console
    svcutil.exe Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-a-compiled-service"></a>Para exportar los metadatos para un servicio compilado  
  
1. Compile su implementación del servicio en un ensamblado ejecutable.  
  
2. Cree un archivo de configuración para su ejecutable de servicio y agregue una configuración de servicio.  
  
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
  
3. Ejecute Svcutil.exe en el ejecutable de servicio compilado utilizando el modificador `/serviceName` para especificar el nombre de configuración del servicio.  
  
    > [!NOTE]
    > Quizás necesite utilizar el modificador `/reference` para especificar la ruta de acceso del archivo a cualquier ensamblado dependiente.  
  
    ```console  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-compiled-data-contracts"></a>Para exportar los metadatos para los contratos de datos compilados  
  
1. Compile sus implementaciones del contrato de datos en una o más bibliotecas de clases.  
  
2. Ejecute Svcutil.exe en los ensamblados compilados utilizando el modificador `/dataContract` para especificar que solo se deberían generar los metadatos para los contratos de datos.  
  
    > [!NOTE]
    > Quizás necesite utilizar el modificador `/reference` para especificar la ruta de acceso del archivo a cualquier ensamblado dependiente.  
  
    ```console  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo generar los metadatos para una implementación de servicio simple y configuración.  
  
 Para exportar los metadatos para el contrato de servicios.  
  
```console  
svcutil.exe Contracts.dll  
```  
  
 Para exportar los metadatos para los contratos de datos.  
  
```console  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 Para exportar los metadatos para la implementación del servicio.  
  
```console  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 `<path>` es la ruta de acceso a Contracts.dll.  
  
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
  
## <a name="see-also"></a>Vea también

- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Exportación e importación de metadatos](exporting-and-importing-metadata.md)
