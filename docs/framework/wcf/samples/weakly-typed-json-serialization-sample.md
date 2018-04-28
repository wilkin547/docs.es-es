---
title: Ejemplo de serialización JSON débilmente tipada
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b30e501-4ef5-474d-9fad-a9d559cf9c52
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4cc75ff1078c35c177f0809d25cd32ca3b2b8e16
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="weakly-typed-json-serialization-sample"></a>Ejemplo de serialización JSON débilmente tipada
Al serializar un tipo definido por el usuario en un formato de conexión determinado o deserializar un formato de conexión en un tipo definido por el usuario, el tipo definido por el usuario determinado debe estar disponible en el servicio y en el cliente. Normalmente, para lograr esto, se aplica el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a estos tipos definidos por el usuario y el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> se aplica a sus miembros. Este mecanismo también se aplica al trabajar con los objetos JSON (JavaScript Object Notation), tal y como se describe en el tema [How to: Serialize and Deserialize JSON Data](../../../../docs/framework/wcf/feature-details/how-to-serialize-and-deserialize-json-data.md).  
  
 En algunos escenarios, un servicio o cliente [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] debe tener acceso a los objetos JSON generados por un servicio o cliente que está fuera del control del desarrollador. Ya que cada vez hay más servicios Web que exponen públicamente las API de JSON, se puede volver muy poco práctico para el desarrollador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] construir los tipos locales definidos por el usuario en los que deserializar los objetos JSON arbitrarios. Este ejemplo proporciona un mecanismo que permite a los desarrolladores de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trabajar con objetos JSON deserializados y arbitrarios sin crear tipos definidos por el usuario. Esto se conoce como *serialización débilmente tipada* de objetos JSON, porque no se conoce el tipo en el que un objeto JSON se deserializa en el momento de la compilación.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Por ejemplo, una API pública de servicio Web devuelve el siguiente objeto JSON, que describe información sobre un usuario del servicio.  
  
```json  
{"personal": {"name": "Paul", "age": 23, "height": 1.7, "isSingle": true, "luckyNumbers": [5,17,21]}, "favoriteBands": ["Band ABC", "Band XYZ"]}  
```  
  
 Para deserializar este objeto, un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] debe implementar los tipos siguientes definidos por el usuario.  
  
```  
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
  
 El tipo `JsonObject` proporcionado por este ejemplo presenta una representación débilmente tipada del objeto JSON deserializado. `JsonObject` confía en la asignación natural entre los objetos JSON y diccionarios [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , y la asignación entre las matrices JSON y matrices de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . En el código siguiente se muestra el tipo `JsonObject` :  
  
```  
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
>  La clase `JsonObject` solo se proporciona como un ejemplo. No se ha probado en profundidad y no debería usarse en entornos de producción. Una implicación obvia de serialización de JSON débilmente tipada es la falta de seguridad de tipos al trabajar con `JsonObject`.  
  
 Para utilizar el tipo `JsonObject` , el contrato de operación del cliente debe utilizar <xref:System.ServiceModel.Channels.Message> como su tipo de valor devuelto.  
  
```  
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
  
```  
// Code to instantiate IClientSideProfileService channel omitted…  
  
// Make a request to the service and obtain the Json response  
XmlDictionaryReader reader = channel.GetMemberProfile().GetReaderAtBodyContents();  
  
// Go through the Json as though it is a dictionary. There is no need to map it to a .NET CLR type.  
JsonObject json = new JsonObject(reader);  
```  
  
 El constructor `JsonObject` toma un <xref:System.Xml.XmlDictionaryReader>, que se obtiene a través del método <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> . El lector contiene una representación XML del mensaje de JSON recibida por el cliente. Para obtener más información, vea el tema [asignación entre JSON y XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).  
  
 El programa produce el siguiente resultado:  
  
```  
Service listening at http://localhost:8000/.  
To view the JSON output from the sample, navigate to http://localhost:8000/GetMemberProfile  
This is Paul's page. I am 23 years old and I am 1.7 meters tall.  
I am single.  
My lucky numbers are 5, 17, and 21.  
My favorite bands are Band ABC and Band XYZ.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compile la solución WeaklyTypedJson.sln tal y como se describe en [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Ajax\WeaklyTypedJson`  
  
## <a name="see-also"></a>Vea también
