---
title: "Cómo utilizar el moniker de servicio de Windows Communication Foundation sin registrarse"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 18f575e9bae37b66526d7b61a641374266ba627b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a>Cómo utilizar el moniker de servicio de Windows Communication Foundation sin registrarse
Para conectarse y comunicarse con un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], la aplicación cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] debe disponer de los detalles de la dirección de servicio, la configuración del enlace y el contrato de servicios.  
  
 Normalmente, el moniker de servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] obtiene el contrato necesario a través del registro previo a los tipos de atributo requeridos, aunque podría haber casos en los que esto no es posible. En lugar del registro, el moniker puede obtener la definición del contrato en forma de documento de lenguaje de descripción de servicios Web (WSDL), mediante el uso del parámetro `wsdl` o a través de Metadatos Exchange, utilizando el parámetro `mexAddress`.  
  
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
  
 Si desea construir un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para el servicio remoto puede utilizar la cadena de moniker del ejemplo siguiente.  
  
```  
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 Durante la ejecución de la aplicación cliente, el cliente realiza `WS-MetadataExchange` con la `mexAddress` proporcionada. Esto podría devolver los detalles de la dirección, el enlace y el contrato de varios servicios. Los parámetros `address`, `contract`, `contractNamespace`, `binding` y `bindingNamespace` se utilizan para identificar el servicio deseado. Una vez identificadas las coincidencias de esos parámetros, el moniker construye un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con la definición del contrato adecuada y, a continuación, pueden realizarse las llamadas utilizando el cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], como con el contrato con tipos.  
  
> [!NOTE]
>  Si el moniker es incorrecto o el servicio no está disponible, la llamada a `GetObject` devuelve un error informando de que la sintaxis no es válida. Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.  
  
## <a name="see-also"></a>Vea también  
 [Registro y configuración de un moniker de servicio](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
