---
title: 'Cómo: Utilizar un moniker de servicio con contratos de intercambio de metadatos'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 6265860c2e1efb2f74a0243157a223a33889629a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Cómo: Utilizar un moniker de servicio con contratos de intercambio de metadatos
Después de desarrollar algunos servicios WCF nueva, puede decidir que desea que se pueda llamar a estos servicios desde una secuencia de comandos o una aplicación de Visual Basic 6.0. Un método sería generar un ensamblado de cliente WCF, registre el ensamblado con COM, instale al ensamblado en la GAC y, a continuación, hacer referencia a los tipos COM desde el código de Visual Basic. Cuando se distribuye la aplicación, tendrá que distribuir también el ensamblado de cliente de WCF. El usuario tendrá que registrar, a continuación, el ensamblado de cliente de WCF con COM y colocarlo en la GAC. Interoperabilidad de COM de WCF también permite realizar las mismas llamadas de servicio sin confiar en un ensamblado de cliente WCF. El moniker WCF permite llamar a cualquier servicio WCF desde cualquier lenguaje compatible con COM (Visual Basic, VBScript, Visual Basic para aplicaciones (VBA) y así sucesivamente) mediante la especificación de un punto de conexión de intercambio (Mex) URI usado por el moniker de servicio para extraer el tipo de metadatos información sobre el servicio. En este tema se describe cómo llamar al ejemplo de WCF Introducción utilizando un moniker WCF que especifica un extremo Mex.  
  
> [!NOTE]
>  Realmente nunca se crean instancias de los tipos definidos por el ensamblado de cliente WCF. El ensamblado solo se utiliza para los metadatos.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Utilizar el moniker de servicio con una dirección de Mex  
  
1.  Compile el ejemplo de introducción y utilice Internet Explorer para ir a su dirección URL (http://localhost/ServiceModelSamples/Service.svc) para asegurarse de que el servicio está funcionando.  
  
2.  Crear un script Visual Basic o aplicación Visual Basic que contiene el código siguiente:  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  Ejecute la aplicación Visual Basic o script.  
  
    > [!NOTE]
    >  El servicio al que está llamando debe exponer un punto de conexión de Mex para que el moniker pueda leer los metadatos del servicio. Para obtener más información, consulte [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
    > [!NOTE]
    >  Si el moniker es incorrecto o si el servicio no está disponible, la llamada a `GetObject` devolverá un error que dirá "Sintaxis no válida."  Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.  
  
## <a name="see-also"></a>Vea también  
 [Uso del moniker de servicio de Windows Communication Foundation sin registrarse](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [Uso de un moniker de servicio con contratos WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
