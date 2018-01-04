---
title: "Solución de problemas con el tutorial de introducción"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55288074b35bcb00d6c6b453f1320ad40d26a5f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-the-getting-started-tutorial"></a>Solución de problemas con el tutorial de introducción
En este tema se enumeran los problemas más comunes que se producen al desarrollar el Tutorial de introducción y se explica cómo resolverlos.  
  
1.  [No puedo encontrar los archivos de proyecto en el disco duro.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q1)  
  
2.  [Se intentó ejecutar la aplicación de servicio: HTTP no pudo registrar la dirección URL http://+:8000/ServiceModelSamples/Service/. Su proceso no tiene los derechos de acceso a este espacio de nombres.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q2)  
  
3.  [Cualquier intento de usar la herramienta Svcutil.exe: 'svcutil' no se reconoce como un comando interno o externo, programa operable o archivo por lotes.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q3)  
  
4.  [No se encuentra el archivo App.config generado por Svcutil.exe.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q4)  
  
5.  [Compilar la aplicación cliente: 'CalculatorClient' no contiene una definición para '&lt;nombre del método&gt;'y no hay ningún método de extensión'&lt;nombre del método&gt;' acepte un primer argumento de tipo 'CalculatorClient' se encontró (¿falta un uso de la directiva o una referencia de ensamblado?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q5)  
  
6.  [Compilar la aplicación cliente: el nombre de tipo o espacio de nombres 'CalculatorClient' no se encontró (¿falta un uso de la directiva o una referencia de ensamblado?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q6)  
  
7.  [Ejecuta el cliente: excepción no controlada: System.ServiceModel.EndpointNotFoundException: no se pudo conectar a http://localhost: 8000/ServiceModelSamples/Service/CalculatorService. Código de error TCP 10061: no se estableció ninguna conexión porque el equipo de destino rechazó.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q7)  
  
<a name="BKMK_q1"></a>   
## <a name="i-am-unable-to-find-the-project-files-on-my-hard-drive"></a>Los archivos del proyecto no se encuentran en el disco duro.  
 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]Guardar archivos de proyecto en c:\users\\< usuario usuario\Documents\\< versión de Visual Studio\>\Projects en [!INCLUDE[wv](../../../includes/wv-md.md)] y [!INCLUDE[win7_client_secondref](../../../includes/win7-client-secondref-md.md)]y c:\Documents and Settings\\< nombre de usuario\>Documentos \My\\< versión de Visual Studio\>\Projects en versiones anteriores de Windows.  
  
<a name="BKMK_q2"></a>   
## <a name="attempting-to-run-the-service-application-http-could-not-register-url-http8000servicemodelsamplesservice-your-process-does-not-have-access-rights-to-this-namespace"></a>Se intentó ejecutar la aplicación de servicio: HTTP no pudo registrar la dirección URL http://+:8000/ServiceModelSamples/Service/. Su proceso no tiene los derechos de acceso a este espacio de nombres.  
 El proceso que hospeda un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se debe ejecutar con privilegios administrativos. Si está ejecutando el servicio desde [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], debe ejecutar [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] como administrador. Para ello, haga clic **iniciar**, haga clic en [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] y seleccione **ejecutar como administrador**. Si está ejecutando el servicio desde el símbolo de la línea de comandos, debe iniciar el símbolo del sistema como administrador de una forma similar. Haga clic en **iniciar**, haga clic en **símbolo** y seleccione **ejecutar como administrador**.  
  
<a name="BKMK_q3"></a>   
## <a name="attempting-to-use-the-svcutilexe-tool-svcutil-is-not-recognized-as-an-internal-or-external-command-operable-program-or-batch-file"></a>Se intentó usar la herramienta Svcutil.exe: 'svcutil' no se reconoce como un comando interno o externo, programa o archivo por lotes ejecutable.  
 Svcutil.exe debe estar en la ruta de acceso del sistema. La solución más fácil es usar el símbolo del sistema. Haga clic en **iniciar**, seleccione **todos los programas**, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], **Visual Studio Tools**, y [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] **símbolo**. Este símbolo del sistema establece la ruta de acceso del sistema en las ubicaciones correctas para todas las herramientas distribuidas como parte de [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
<a name="BKMK_q4"></a>   
## <a name="unable-to-find-the-appconfig-file-generated-by-svcutilexe"></a>No se encuentra el archivo App.config generado por Svcutil.exe.  
 El **Agregar elemento existente** cuadro de diálogo muestra únicamente archivos con las siguientes extensiones de forma predeterminada:. cs, .resx, .settings, .xsd, .wsdl. Puede especificar que desea ver todos los tipos de archivo seleccionando **todos los archivos (\*.\*)**  en la lista desplegable del cuadro de lista en la esquina inferior derecha de la **Agregar elemento existente** cuadro de diálogo.  
  
<a name="BKMK_q5"></a>   
## <a name="compiling-the-client-application-calculatorclient-does-not-contain-a-definition-for-method-name-and-no-extension-method-method-name-accepting-a-first-argument-of-type-calculatorclient-could-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>Compilar la aplicación cliente: 'CalculatorClient' no contiene una definición para '\<nombre de método >' y no hay ningún método de extensión '\<nombre de método >' acepte un primer argumento de tipo 'CalculatorClient' se encontró (¿ Falta el uso de una directiva o una referencia de ensamblado?)  
 Sólo los métodos que se marcan con `ServiceOperationAttribute` se exponen al exterior. Si omitió el atributo `ServiceOperationAttribute` en uno de los métodos de la interfaz `ICalculator`, aparece este mensaje de error al compilar una aplicación cliente que realice una llamada a la operación que no tiene el atributo.  
  
<a name="BKMK_q6"></a>   
## <a name="compiling-the-client-application-the-type-or-namespace-name-calculatorclient-could-not-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>Compilación de la aplicación cliente: no se puede encontrar el tipo o el nombre de espacio de nombres 'CalculatorClient' (¿falta una directiva using o una referencia de ensamblado?)  
 Este error se produce si no se agrega el archivo Proxy.cs o Proxy.vb a su proyecto de cliente.  
  
<a name="BKMK_q7"></a>   
## <a name="running-the-client-unhandled-exception-systemservicemodelendpointnotfoundexception-could-not-connect-to-httplocalhost8000servicemodelsamplesservicecalculatorservice-tcp-error-code-10061-no-connection-could-be-made-because-the-target-machine-actively-refused-it"></a>Ejecución del cliente: excepción no controlada: System.ServiceModel.EndpointNotFoundException: no se puede establecer conexión con http://localhost:8000/ServiceModelSamples/Service/CalculatorService. Código de error TCP 10061: no se estableció ninguna conexión porque el equipo de destino la rechazó.  
 Este error se produce si se ejecuta la aplicación cliente sin ejecutar el servicio.  
  
<a name="BKMK_q8"></a>   
## <a name="unhandled-exception-systemservicemodelsecuritysecuritynegotiationexception-soap-security-negotiation-with-httplocalhost8000servicemodelsamplesservicecalculatorservice-for-target-httplocalhost8000servicemodelsamplesservicecalculatorservice-failed"></a>Excepción no controlada: System.ServiceModel.Security.SecurityNegotiationException: error de negociación de seguridad SOAP con 'http://localhost:8000/ServiceModelSamples/Service/CalculatorService' para el destino 'http://localhost:8000/ServiceModelSamples/Service/CalculatorService'  
 Este error se produce en un equipo unido a un dominio que no dispone de conectividad de red. Conecte el equipo a la red o desactive la seguridad para el cliente y el servicio. En el servicio, modifique el código que crea el WSHttpBinding de la manera siguiente.  
  
```  
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```  
  
 En el cliente, cambie el  **\<seguridad >** elemento bajo el  **\<enlace >** elemento de la manera siguiente:  
  
```xml  
<security mode="Node" />  
```  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Inicio rápido de solución de problemas de WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 [Solución de problemas de instalación](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
