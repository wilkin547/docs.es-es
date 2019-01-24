---
title: Solución de problemas con el tutorial de introducción
ms.date: 03/30/2017
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 5b8cd04ef4d98e522e255e1b7529e848351b2e0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695665"
---
# <a name="troubleshooting-the-getting-started-tutorial"></a>Solución de problemas con el tutorial de introducción
En este tema se enumeran los problemas más comunes que se producen al desarrollar el Tutorial de introducción y se explica cómo resolverlos.  
  
**No puedo encontrar los archivos de proyecto en el disco duro.**

 Visual Studio guarda los archivos de proyecto en c:\users\\<user name>\Documents\\< versión de Visual Studio\>\Projects.  
  
**Intentar ejecutar la aplicación de servicio: HTTP no pudo registrar la dirección URL `http://+:8000/ServiceModelSamples/Service/`.** 
 **Su proceso no tiene derechos de acceso a este espacio de nombres.** 

 El proceso que hospeda un servicio WCF se debe ejecutar con privilegios administrativos. Si está ejecutando el servicio desde dentro de Visual Studio, debe ejecutar Visual Studio como administrador. Para ello, haga clic **iniciar**, haga clic en **Visual Studio \< *versión* >**  y seleccione **ejecutar como administrador**. Si está ejecutando el servicio desde un símbolo del sistema de línea de comandos en una ventana de consola, debe iniciar la ventana de consola como un administrador de una manera similar. Haga clic en **iniciar**, haga clic en **símbolo** y seleccione **ejecutar como administrador**.  
  
**Al intentar utilizar la herramienta Svcutil.exe: 'svcutil' no se reconoce como un comando interno o externo, programa operable o archivo por lotes.**

 Svcutil.exe debe estar en la ruta de acceso del sistema. La solución más fácil es usar el símbolo del sistema. Haga clic en **iniciar**, seleccione **todos los programas**, **Visual Studio \< *versión*>**,  **Herramientas de Visual Studio**, y **símbolo del sistema para desarrolladores de Visual Studio**. Este símbolo se establece la ruta de acceso del sistema en las ubicaciones correctas para todas las herramientas que se incluye como parte de Visual Studio.  

**No se encuentra el archivo App.config generado por Svcutil.exe.**

 El **Agregar elemento existente** cuadro de diálogo solo muestra los archivos con las siguientes extensiones de forma predeterminada:. cs, .resx, .settings, .xsd,. WSDL. Puede especificar que desea ver todos los tipos de archivo seleccionando **todos los archivos (\*.\*)**  en el cuadro de lista desplegable situada en la esquina inferior derecha de la **Agregar elemento existente** cuadro de diálogo.  


**Compilar la aplicación cliente: 'CalculatorClient' no contiene una definición para '\<nombre del método >' y no hay ningún método de extensión '\<nombre del método >' acepte un primer argumento de tipo 'CalculatorClient' se encontró (¿falta un uso de la directiva o un referencia de ensamblado?)**  

Sólo los métodos que se marcan con `ServiceOperationAttribute` se exponen al exterior. Si omite el `ServiceOperationAttribute` atributo desde uno de los métodos de la `ICalculator` interfaz, obtendrá este mensaje de error al compilar una aplicación cliente que realiza una llamada a la operación no tiene el atributo.  

**Compilar la aplicación cliente: El nombre de tipo o espacio de nombres 'CalculatorClient' no se encontró (¿falta un uso de la directiva o una referencia de ensamblado?)**

 Este error se produce si no se agrega el archivo Proxy.cs o Proxy.vb a su proyecto de cliente.  

**Ejecuta al cliente: Excepción no controlada: System.ServiceModel.EndpointNotFoundException: No se pudo conectar a `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`. Código de error TCP 10061: Se realizará ninguna conexión porque el equipo de destino rechazó.**

Este error se produce si se ejecuta la aplicación cliente sin ejecutar el servicio.  
  
**Excepción no controlada: System.ServiceModel.Security.SecurityNegotiationException: Negociación de seguridad SOAP con `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` para destino `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` error**  

Este error se produce en un equipo unido a un dominio que no dispone de conectividad de red. Conecte el equipo a la red o desactive la seguridad para el cliente y el servicio. En el servicio, modifique el código que crea el WSHttpBinding de la manera siguiente.  
  
```csharp
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```

Para el cliente, cambie el  **\<seguridad >** elemento bajo el  **\<enlace >** elemento a lo siguiente:  
  
```xml
<security mode="Node" />  
```  

## <a name="see-also"></a>Vea también
- [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md)
- [Inicio rápido de solución de problemas de WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)
- [Solución de problemas de instalación](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
