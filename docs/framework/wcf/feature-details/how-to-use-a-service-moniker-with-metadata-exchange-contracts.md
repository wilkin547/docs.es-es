---
title: Procedimiento para usar un moniker de servicio con contratos de intercambio de metadatos
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 04a940a6e8f010e5cd851684c5fc62bab2a1a034
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601171"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Procedimiento para usar un moniker de servicio con contratos de intercambio de metadatos
Después de desarrollar algunos servicios WCF nuevos, puede decidir que desea poder llamar a estos servicios desde un script o una aplicación Visual Basic 6,0. Un método sería generar un ensamblado de cliente de WCF, registrar el ensamblado con COM, instalar el ensamblado en la GAC y, a continuación, hacer referencia a los tipos COM desde el código de Visual Basic. Al distribuir la aplicación, tendrá que distribuir también el ensamblado de cliente de WCF. El usuario tendrá que registrar, a continuación, el ensamblado de cliente de WCF con COM y colocarlo en la GAC. La interoperabilidad COM de WCF también permite realizar las mismas llamadas de servicio sin depender de un ensamblado de cliente de WCF. El moniker de WCF le permite llamar a cualquier servicio de WCF desde cualquier lenguaje compatible con COM (Visual Basic, VBScript, Visual Basic para Aplicaciones (VBA), etc.) especificando un URI de extremo de intercambio de metadatos (MEX) que el moniker de servicio utiliza para extraer información de tipo sobre el servicio. En este tema se describe cómo llamar al ejemplo de Introducción WCF mediante un moniker de WCF que especifica un extremo de Mex.  
  
> [!NOTE]
> Nunca se crean instancias de los tipos definidos por el ensamblado de cliente de WCF. El ensamblado solo se utiliza para los metadatos.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Utilizar el moniker de servicio con una dirección de Mex  
  
1. Compile el ejemplo Introducción y use Internet Explorer para ir a su dirección URL ( `http://localhost/ServiceModelSamples/Service.svc` ) para asegurarse de que el servicio está funcionando.  
  
2. Crear un script Visual Basic o aplicación Visual Basic que contiene el código siguiente:  
  
    ```vb
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. Ejecute la aplicación Visual Basic o script.  
  
    > [!NOTE]
    > El servicio al que está llamando debe exponer un extremo de Mex para que el moniker pueda leer los metadatos del servicio. Para obtener más información, consulte [Cómo: publicar metadatos para un servicio mediante un archivo de configuración](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
    > [!NOTE]
    > Si el moniker es incorrecto o si el servicio no está disponible, la llamada a `GetObject` devolverá un error que dirá "Sintaxis no válida."  Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para usar el moniker de servicio de Windows Communication Foundation sin registrarse](use-the-wcf-service-moniker-without-registration.md)
- [Procedimiento para usar un moniker de servicio con contratos WSDL](how-to-use-a-service-moniker-with-wsdl-contracts.md)
