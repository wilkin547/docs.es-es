---
title: "Cómo: Utilizar un moniker de servicio con contratos de intercambio de metadatos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed6ce9b87a5e2d8945a57110c02cce8024439f14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Cómo: Utilizar un moniker de servicio con contratos de intercambio de metadatos
Después de desarrollar algunos servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nuevos, puede decidir que quiere poder llamar a estos servicios desde un script o una aplicación de Visual Basic 6.0. Un método sería generar un ensamblado de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], registre el ensamblado con COM, instale el ensamblado en la GAC y, a continuación, haga referencia a los tipos COM de su código de Visual Basic. Al distribuir la aplicación, tendrá que distribuir también el ensamblado de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. El usuario tendrá que registrar, a continuación, el ensamblado de cliente de WCF con COM y colocarlo en la GAC. Interoperabilidad COM [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también le permite realizar las mismas llamadas de servicio sin confiar en un ensamblado de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. El moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le permite llamar a cualquier servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] desde cualquier lenguaje COM compatible (Visual Basic, VBScript, Visual Basic para Aplicaciones (VBA), etc.) especificando un extremo URI de intercambio de metadatos (Mex) que el moniker de servicio utiliza para extraer información de tipo sobre el servicio. En este tema se describe cómo llamar al ejemplo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de la Introducción mediante un moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que especifica un extremo de Mex.  
  
> [!NOTE]
>  No se crean instancias realmente de los tipos definidos por el ensamblado de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. El ensamblado solo se utiliza para los metadatos.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Utilizar el moniker de servicio con una dirección de Mex  
  
1.  Compile el ejemplo de Introducción y utilice Internet Explorer para ir a su dirección URL (http://localhost/ServiceModelSamples/Service.svc) con el fin de asegurarse que el servicio está funcionando.  
  
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
 [Cómo: utilizar el Moniker de servicio de Windows Communication Foundation sin registro](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [Cómo: utilizar un Moniker de servicio con contratos WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
