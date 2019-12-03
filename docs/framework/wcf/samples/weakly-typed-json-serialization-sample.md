---
title: Ejemplo de serialización JSON débilmente tipada
ms.date: 03/30/2017
ms.assetid: 0b30e501-4ef5-474d-9fad-a9d559cf9c52
ms.openlocfilehash: 8893c466b347b97a7845234a8182af7ca7feba83
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715046"
---
# <a name="weakly-typed-json-serialization-sample"></a>Ejemplo de serialización JSON débilmente tipada
Al serializar un tipo definido por el usuario en un formato de conexión determinado o deserializar un formato de conexión en un tipo definido por el usuario, el tipo definido por el usuario determinado debe estar disponible en el servicio y en el cliente. Normalmente, para lograr esto, se aplica el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a estos tipos definidos por el usuario y el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> se aplica a sus miembros. Este mecanismo también se aplica al trabajar con los objetos JSON (JavaScript Object Notation), tal y como se describe en el tema [How to: Serialize and Deserialize JSON Data](../../../../docs/framework/wcf/feature-details/how-to-serialize-and-deserialize-json-data.md).  
  
 En algunos escenarios, un servicio o cliente Windows Communication Foundation (WCF) debe tener acceso a los objetos JSON generados por un servicio o cliente que está fuera del control del desarrollador. A medida que más servicios web exponen públicamente las API JSON, puede resultar poco práctico para que el desarrollador de WCF construya tipos locales definidos por el usuario en los que deserializar objetos JSON arbitrarios. Este ejemplo proporciona un mecanismo que permite a los desarrolladores de WCF trabajar con objetos JSON deserializados e arbitrarios sin crear tipos definidos por el usuario. Esto se conoce como *serialización débilmente tipada* de objetos JSON, porque no se conoce el tipo en el que un objeto JSON se deserializa en el momento de la compilación.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Por ejemplo, una API pública de servicio Web devuelve el siguiente objeto JSON, que describe información sobre un usuario del servicio.  
  
```json  
{"personal": {"name": "Paul", "age": 23, "height": 1.7, "isSingle": true, "luckyNumbers": [5,17,21]}, "favoriteBands": ["Band ABC", "Band XYZ"]}  
```  
  
 Para deserializar este objeto, un cliente de WCF debe implementar los siguientes tipos definidos por el usuario.  
  
```csharp  
[DataContract]  
 public class MemberProfile  
 {  
     [DataMember]  
     public PersonalInfo personal;  
  
     [DataMember]  
     public string[] favoriteBands;  
 }  
  
 [DataContract]  
 public class PersonalInfo  
 {  
     [DataMember]  
     public string name;  
  
     [DataMember]  
     public int age;  
  
     [DataMember]  
     public double height;  
  
     [DataMember]  
     public bool isSingle;  
  
     [DataMember]  
     public int[] luckyNumbers;  
 }  
```  
  
 Esto puede ser embarazoso, sobre todo si el cliente tiene que administrar más de un tipo de objeto JSON.  
  
 El tipo `JsonObject` proporcionado por este ejemplo presenta una representación débilmente tipada del objeto JSON deserializado. `JsonObject` se basa en la asignación natural entre los objetos JSON y .NET Framework diccionarios, y la asignación entre las matrices JSON y .NET Framework. En el código siguiente se muestra el tipo `JsonObject` :  
  
```csharp  
// Instantiation of JsonObject json omitted  
  
string name = json["root"]["personal"]["name"];  
int age = json["root"]["personal"]["age"];  
double height = json["root"]["personal"]["height"];  
bool isSingle = json["root"]["personal"]["isSingle"];  
int[] luckyNumbers = {  
                                     json["root"]["personal"]["luckyNumbers"][0],  
                                     json["root"]["personal"]["luckyNumbers"][1],  
                                     json["root"]["personal"]["luckyNumbers"][2]   
                                 };  
string[] favoriteBands = {  
                                        json["root"]["favoriteBands"][0],  
                                        json["root"]["favoriteBands"][1]  
                                    };  
```  
  
 Observe que puede examinar los objetos y matrices JSON sin necesidad de declarar el tipo en el momento de la compilación. Para acceder a una explicación del requisito del objeto `["root"]` de nivel superior, consulte el tema [Mapping Between JSON and XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).  
  
> [!NOTE]
> La clase `JsonObject` solo se proporciona como un ejemplo. No se ha probado en profundidad y no debería usarse en entornos de producción. Una implicación obvia de serialización de JSON débilmente tipada es la falta de seguridad de tipos al trabajar con `JsonObject`.  
  
 Para utilizar el tipo `JsonObject` , el contrato de operación del cliente debe utilizar <xref:System.ServiceModel.Channels.Message> como su tipo de valor devuelto.  
  
```csharp  
[ServiceContract]  
    interface IClientSideProfileService  
    {  
        // There is no need to write a DataContract for the complex type returned by the service.  
        // The client will use a JsonObject to browse the JSON in the received message.  
  
        [OperationContract]  
        [WebGet(ResponseFormat = WebMessageFormat.Json)]  
        Message GetMemberProfile();  
    }  
```  
  
 Se crean instancias de `JsonObject` a continuación tal y como se muestran en el código siguiente.  
  
```csharp  
// Code to instantiate IClientSideProfileService channel omitted…  
  
// Make a request to the service and obtain the Json response  
XmlDictionaryReader reader = channel.GetMemberProfile().GetReaderAtBodyContents();  
  
// Go through the Json as though it is a dictionary. There is no need to map it to a .NET CLR type.  
JsonObject json = new JsonObject(reader);  
```  
  
 El constructor `JsonObject` toma un <xref:System.Xml.XmlDictionaryReader>, que se obtiene a través del método <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> . El lector contiene una representación XML del mensaje de JSON recibida por el cliente. Para obtener más información, vea el tema sobre la [asignación entre JSON y XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).  
  
 El programa produce el siguiente resultado:  
  
```console  
Service listening at http://localhost:8000/.  
To view the JSON output from the sample, navigate to http://localhost:8000/GetMemberProfile  
This is Paul's page. I am 23 years old and I am 1.7 meters tall.  
I am single.  
My lucky numbers are 5, 17, and 21.  
My favorite bands are Band ABC and Band XYZ.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Compile la solución WeaklyTypedJson.sln tal y como se describe en [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Ejecute la solución.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Ajax\WeaklyTypedJson`  
