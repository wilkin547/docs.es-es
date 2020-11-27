---
title: Procedimiento para usar el moniker de servicio de Windows Communication Foundation sin registrarse
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: 41761313fae68a1a348a73f104e21dc19e07eb65
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293512"
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a>Procedimiento para usar el moniker de servicio de Windows Communication Foundation sin registrarse

Para conectarse y comunicarse con un servicio de Windows Communication Foundation (WCF), una aplicación cliente de WCF debe tener los detalles de la dirección del servicio, la configuración del enlace y el contrato de servicio.  
  
 Normalmente, el moniker de servicio de WCF obtiene el contrato necesario a través del registro anterior de los tipos de atributo necesarios, pero puede haber casos en los que esto no sea factible. En lugar del registro, el moniker puede obtener la definición del contrato en forma de documento de lenguaje de descripción de servicios Web (WSDL), mediante el uso del parámetro `wsdl` o a través de Metadatos Exchange, utilizando el parámetro `mexAddress`.  
  
 Esto habilita escenarios como la distribución de una hoja de cálculo de Excel en la que algunos de los valores de celda se calculan mediante las interacciones del servicio Web. En este escenario, puede no ser posible registrar el ensamblado de contrato de servicios en todos los clientes que podrían abrir el documento. El parámetro `wsdl` o el parámetro `mexAddress` habilitan una solución autónoma.  
  
> [!NOTE]
> La autenticación mutua debe utilizarse como protección frente a la manipulación o suplantación de solicitudes o respuestas. Más concretamente, es importante para los clientes estar seguros de que el punto de conexión del intercambio de metadatos es la parte de confianza interesada.  
  
## <a name="example"></a>Ejemplo  

 Este ejemplo muestra el uso del moniker de servicio con un contrato MEX (Metadata Exchange). Un servicio con el siguiente contrato se expone con wsHttpBinding.  
  
```csharp
using System.ServiceModel;  
  
// ...
  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Demo")]  
public interface IAffiliate  
{  
    [OperationContract]  
    bool NewAffiliate(string ID, string company, string fullname, string accountsCode);  
    [OperationContract]  
    bool RemoveAffiliate(string ID);  
    [OperationContract]  
    double RevenueCheckMonthly(ref string ID);  
    [OperationContract]  
    double RevenueCheckTotal(ref string ID);  
}  
```  
  
 Para construir un cliente WCF para el servicio remoto, se puede usar la cadena de moniker de ejemplo siguiente.  
  
```
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 Durante la ejecución de la aplicación cliente, el cliente realiza `WS-MetadataExchange` con la `mexAddress` proporcionada. Esto podría devolver los detalles de la dirección, el enlace y el contrato de varios servicios. Los parámetros `address`, `contract`, `contractNamespace`, `binding` y `bindingNamespace` se utilizan para identificar el servicio deseado. Una vez que se han encontrado los parámetros, el moniker crea un cliente de WCF con la definición de contrato adecuada y, a continuación, se puede realizar llamadas mediante el cliente WCF, como con el contrato con tipo.  
  
> [!NOTE]
> Si el moniker es incorrecto o el servicio no está disponible, la llamada a `GetObject` devuelve un error informando de que la sintaxis no es válida. Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para registrar y configurar un moniker de servicio](how-to-register-and-configure-a-service-moniker.md)
