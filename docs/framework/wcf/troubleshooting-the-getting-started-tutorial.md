---
title: "Soluci&#243;n de problemas con el tutorial de introducci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Soluci&#243;n de problemas con el tutorial de introducci&#243;n
En este tema se enumeran los problemas más comunes que se producen al desarrollar el Tutorial de introducción y se explica cómo resolverlos.  
  
1.  [Los archivos del proyecto no se encuentran en el disco duro.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q1)  
  
2.  [Se intentó ejecutar la aplicación de servicio: HTTP no pudo registrar la dirección URL http://+:8000/ServiceModelSamples/Service/.Su proceso no tiene los derechos de acceso a este espacio de nombres.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q2)  
  
3.  [Se intentó usar la herramienta Svcutil.exe: 'svcutil' no se reconoce como un comando interno o externo, programa o archivo por lotes ejecutable.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q3)  
  
4.  [No se encuentra el archivo App.config generado por Svcutil.exe.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q4)  
  
5.  [Compilación de la aplicación cliente: 'CalculatorClient' no contiene una definición de '&lt;nombre de método&gt;' ni se encontró ningún método de extensión '&lt;nombre de método&gt;' que acepte un primer argumento de tipo 'CalculatorClient' (¿falta una directiva using o una referencia de ensamblado?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q5)  
  
6.  [Compilación de la aplicación cliente: no se puede encontrar el tipo o el nombre de espacio de nombres 'CalculatorClient' (¿falta una directiva using o una referencia de ensamblado?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q6)  
  
7.  [Ejecución del cliente: excepción no controlada: System.ServiceModel.EndpointNotFoundException: no se puede establecer conexión con http://localhost:8000/ServiceModelSamples/Service/CalculatorService.Código de error TCP 10061: no se estableció ninguna conexión porque el equipo de destino la rechazó.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q7)  
  
<a name="BKMK_q1"></a>   
## Los archivos del proyecto no se encuentran en el disco duro.  
 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] guarda los archivos de proyecto en c:\\users\\\<nombre de usuario\\Documents\\\<versión de Visual Studio\>\\Projects en [!INCLUDE[wv](../../../includes/wv-md.md)] y en [!INCLUDE[win7_client_secondref](../../../includes/win7-client-secondref-md.md)], y en c:\\Documents and Settings\\\<nombre de usuario\>\\My Documents\\\<versión de Visual Studio\>\\Projects en versiones anteriores de Windows.  
  
<a name="BKMK_q2"></a>   
## Se intentó ejecutar la aplicación de servicio: HTTP no pudo registrar la dirección URL http:\/\/\+:8000\/ServiceModelSamples\/Service\/.Su proceso no tiene los derechos de acceso a este espacio de nombres.  
 El proceso que hospeda un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se debe ejecutar con privilegios administrativos.Si está ejecutando el servicio desde [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], debe ejecutar [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] como administrador.Para ello, haga clic en **Inicio**, haga clic con el botón secundario en [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] y seleccione **Ejecutar como administrador**.Si está ejecutando el servicio desde el símbolo de la línea de comandos, debe iniciar el símbolo del sistema como administrador de una forma similar.Haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.  
  
<a name="BKMK_q3"></a>   
## Se intentó usar la herramienta Svcutil.exe: 'svcutil' no se reconoce como un comando interno o externo, programa o archivo por lotes ejecutable.  
 Svcutil.exe debe estar en la ruta de acceso del sistema.La solución más fácil es usar el símbolo del sistema.Haga clic en **Inicio**, seleccione **Todos los programas**, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], **Visual Studio Tools** y [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] **Símbolo del sistema**.Este símbolo del sistema establece la ruta de acceso del sistema en las ubicaciones correctas para todas las herramientas distribuidas como parte de [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
<a name="BKMK_q4"></a>   
## No se encuentra el archivo App.config generado por Svcutil.exe.  
 El cuadro de diálogo **Agregar elemento existente** sólo muestra de forma predeterminada los archivos con las extensiones siguientes: .cs, .resx, .settings, .xsd, .wsdl.Puede especificar que desea ver todos los tipos de archivos seleccionando **Todos los archivos \(\*.\*\)** en el cuadro de lista desplegable situado en la esquina inferior derecha del cuadro de diálogo **Agregar elemento existente**.  
  
<a name="BKMK_q5"></a>   
## Compilación de la aplicación cliente: 'CalculatorClient' no contiene una definición de '\<nombre de método\>' ni se encontró ningún método de extensión '\<nombre de método\>' que acepte un primer argumento de tipo 'CalculatorClient' \(¿falta una directiva using o una referencia de ensamblado?\)  
 Sólo los métodos que se marcan con `ServiceOperationAttribute` se exponen al exterior.Si omitió el atributo `ServiceOperationAttribute` en uno de los métodos de la interfaz `ICalculator`, aparece este mensaje de error al compilar una aplicación cliente que realice una llamada a la operación que no tiene el atributo.  
  
<a name="BKMK_q6"></a>   
## Compilación de la aplicación cliente: no se puede encontrar el tipo o el nombre de espacio de nombres 'CalculatorClient' \(¿falta una directiva using o una referencia de ensamblado?\)  
 Este error se produce si no se agrega el archivo Proxy.cs o Proxy.vb a su proyecto de cliente.  
  
<a name="BKMK_q7"></a>   
## Ejecución del cliente: excepción no controlada: System.ServiceModel.EndpointNotFoundException: no se puede establecer conexión con http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService.Código de error TCP 10061: no se estableció ninguna conexión porque el equipo de destino la rechazó.  
 Este error se produce si se ejecuta la aplicación cliente sin ejecutar el servicio.  
  
<a name="BKMK_q8"></a>   
## Excepción no controlada: System.ServiceModel.Security.SecurityNegotiationException: error de negociación de seguridad SOAP con 'http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService' para el destino 'http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService'  
 Este error se produce en un equipo unido a un dominio que no dispone de conectividad de red.Conecte el equipo a la red o desactive la seguridad para el cliente y el servicio.En el servicio, modifique el código que crea el WSHttpBinding de la manera siguiente.  
  
```  
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
  
```  
  
 En el cliente, cambie el elemento **\<security\>** debajo del elemento **\<binding\>** de la manera siguiente:  
  
```  
<security mode="Node" />  
```  
  
## Vea también  
 [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md)   
 [Inicio rápido de solución de problemas de WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)   
 [Solución de problemas de instalación](../../../docs/framework/wcf/troubleshooting-setup-issues.md)