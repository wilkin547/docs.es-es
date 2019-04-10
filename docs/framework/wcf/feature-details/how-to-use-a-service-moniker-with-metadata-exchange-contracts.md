---
title: Filtrar para usar un moniker de servicio con contratos de intercambio de metadatos
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 367cbd4a2bfbde3d4ab0a74eeeaf5d5f5662ec27
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319838"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Filtrar para usar un moniker de servicio con contratos de intercambio de metadatos
Después de desarrollar algunos servicios de WCF nueva, puede decidir que desea llamar a estos servicios desde un script o una aplicación de Visual Basic 6.0. Un método sería generar un ensamblado de cliente WCF, registrar el ensamblado con COM, instale al ensamblado en la GAC y, a continuación, hacer referencia a los tipos COM desde código de Visual Basic. Cuando se distribuye la aplicación, tendrá que distribuir también el ensamblado de cliente de WCF. El usuario tendrá que registrar, a continuación, el ensamblado de cliente de WCF con COM y colocarlo en la GAC. Interoperabilidad de COM de WCF también permite realizar las mismas llamadas de servicio sin tener que depender de un ensamblado de cliente WCF. El moniker WCF le permite llamar a cualquier servicio WCF en cualquier lenguaje compatible con COM (Visual Basic, VBScript, Visual Basic para aplicaciones (VBA) etc.) mediante la especificación de un extremo de intercambio (Mex) identificador URI que utiliza el moniker de servicio para extraer el tipo de metadatos información sobre el servicio. Este tema describe cómo llamar al ejemplo de WCF Introducción utilizando un moniker WCF que especifica un punto de conexión Mex.  
  
> [!NOTE]
>  Realmente nunca se crean instancias de los tipos definidos por el ensamblado de cliente WCF. El ensamblado solo se utiliza para los metadatos.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Utilizar el moniker de servicio con una dirección de Mex  
  
1. Compile el ejemplo de introducción y utilice Internet Explorer para ir a su dirección URL (http://localhost/ServiceModelSamples/Service.svc) para asegurarse de que el servicio está funcionando.  
  
2. Crear un script Visual Basic o aplicación Visual Basic que contiene el código siguiente:  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. Ejecute la aplicación Visual Basic o script.  
  
    > [!NOTE]
    >  El servicio al que está llamando debe exponer un extremo de Mex para que el moniker pueda leer los metadatos del servicio. Para obtener más información, vea [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
    > [!NOTE]
    >  Si el moniker es incorrecto o si el servicio no está disponible, la llamada a `GetObject` devolverá un error que dirá "Sintaxis no válida."  Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.  
  
## <a name="see-also"></a>Vea también

- [Filtrar para usar el moniker de servicio de Windows Communication Foundation sin registrarse](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [Filtrar para usar un moniker de servicio con contratos WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
