---
title: Cómo utilizar el moniker de servicio de Windows Communication Foundation sin registrarse
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: fd61528770b16b13430be3691aef19c1cc743e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a>Cómo utilizar el moniker de servicio de Windows Communication Foundation sin registrarse
Para conectarse y comunicarse con un servicio de Windows Communication Foundation (WCF), una aplicación de cliente WCF debe disponer de los detalles de la dirección de servicio, la configuración de enlace y el contrato de servicio.  
  
 El moniker de servicio WCF normalmente obtiene el contrato necesario a través del registro previo de los tipos de atributo necesario, pero podría haber casos en que esto no es posible. En lugar del registro, el moniker puede obtener la definición del contrato en forma de documento de lenguaje de descripción de servicios Web (WSDL), mediante el uso del parámetro `wsdl` o a través de Metadatos Exchange, utilizando el parámetro `mexAddress`.  
  
 Esto habilita escenarios como la distribución de una hoja de cálculo de Excel en la que algunos de los valores de celda se calculan mediante las interacciones del servicio Web. En este escenario, puede no ser posible registrar el ensamblado de contrato de servicios en todos los clientes que podrían abrir el documento. El parámetro `wsdl` o el parámetro `mexAddress` habilitan una solución autónoma.  
  
> [!NOTE]
>  La autenticación mutua debe utilizarse como protección frente a la manipulación o suplantación de solicitudes o respuestas. Más concretamente, es importante para los clientes estar seguros de que el extremo del intercambio de metadatos es la parte de confianza interesada.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra el uso del moniker de servicio con un contrato MEX (Metadata Exchange). Un servicio con el siguiente contrato se expone con wsHttpBinding.  
  
```  
using System.ServiceModel;  
  
...  
  
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
  
 Puede usarse construir a un cliente WCF para el servicio remoto el siguiente ejemplo de cadena de moniker.  
  
```  
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 Durante la ejecución de la aplicación cliente, el cliente realiza `WS-MetadataExchange` con la `mexAddress` proporcionada. Esto podría devolver los detalles de la dirección, el enlace y el contrato de varios servicios. Los parámetros `address`, `contract`, `contractNamespace`, `binding` y `bindingNamespace` se utilizan para identificar el servicio deseado. Una vez que han coincidido esos parámetros, el moniker construye a un cliente WCF con la definición del contrato adecuada y, a continuación, se pueden realizar llamadas con el cliente WCF, al igual que con el contrato con tipo.  
  
> [!NOTE]
>  Si el moniker es incorrecto o el servicio no está disponible, la llamada a `GetObject` devuelve un error informando de que la sintaxis no es válida. Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.  
  
## <a name="see-also"></a>Vea también  
 [Registro y configuración de un moniker de servicio](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
