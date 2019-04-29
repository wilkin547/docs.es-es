---
title: Solución de problemas de la operación Get a trabajar con los tutoriales de Windows Communication Foundation
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 8089e0fee262d07be591069982b1aacfbeae2521
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791474"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Solución de problemas de la operación Get a trabajar con los tutoriales de Windows Communication Foundation

En este artículo proporciona soluciones para los problemas más comunes y los errores que puede enfrentarse al seguir los pasos descritos en la [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md). 
  
## <a name="common-problems"></a>Problemas habituales

**No se encuentra los archivos del proyecto en el disco duro.**

 Visual Studio guarda los archivos del proyecto *C:\Users\\&lt;nombre de usuario&gt;\source\repos*.  

**No se puede encontrar el *App.config* archivo generado por *Svcutil.exe*.**

 En Visual Studio, el **Agregar elemento existente** ventana solo muestra los archivos con las siguientes extensiones de forma predeterminada: 
- *.cs* 
- *.resx* 
- *.settings*
- *.xsd* 
- *.wsdl*

Para mostrar todos los tipos de archivo, seleccione **todos los archivos (\*.\*)**  en la lista desplegable en la esquina inferior derecha de la **Agregar elemento existente** ventana.  
  
## <a name="common-errors"></a>Errores comunes

### <a name="compile-the-service-application"></a>Compile la aplicación de servicio 

**Error BC30420 no se encontró 'Sub Main' en 'GettingStartedHost.Module1'.**

El punto de entrada no es correcto para la aplicación Visual Basic. Realice el cambio siguiente:

   1. En el **el Explorador de soluciones** ventana, seleccione el **GettingStartedHost** carpeta y, a continuación, seleccione **propiedades** en el menú contextual.
    a. En el **GettingStartedHost** ventana, para **objeto Startup**, seleccione **Service.Program** (o el punto de entrada para su aplicación particular) en la lista. 
    b. En el menú principal, seleccione **archivo** > **guardar todo**.

### <a name="run-the-service-application"></a>Ejecute la aplicación de servicio 

**HTTP no pudo registrar la dirección URL ' http:\// +: 8000/GettingStarted/CalculatorService '. Su proceso no tiene los derechos de acceso a este espacio de nombres.** 

 Para el acceso correcto, inicie el proceso que hospeda el servicio de Windows Communication Foundation (WCF) con privilegios administrativos:
- Para Visual Studio: Seleccione el programa de Visual Studio en el **iniciar** menú y, a continuación, seleccione **más** > **ejecutar como administrador** en el menú contextual.
- Para una ventana de consola: Seleccione **símbolo** en el **iniciar** menú y, a continuación, seleccione **más** > **ejecutar como administrador** desde el acceso directo menú.
- Explorador de Windows: Seleccione el archivo ejecutable y, a continuación, seleccione **ejecutar como administrador** en el menú contextual.

### <a name="compile-the-client-application"></a>Compile la aplicación cliente

**'CalculatorClient', no contiene una definición para '\<nombre del método >' y no hay ningún método de extensión '\<nombre del método >' acepte un primer argumento de tipo 'CalculatorClient' se encontró (¿falta un uso de la directiva o un referencia de ensamblado?)**  

Solo aquellos métodos que se marcan con el `ServiceOperationAttribute` atributo se exponen públicamente. Si se omite el `ServiceOperationAttribute` atributo desde un método en el `ICalculator` interfaz, recibirá este mensaje de error durante la compilación.  

**El nombre de tipo o espacio de nombres 'CalculatorClient' no se encontró (¿falta un uso de la directiva o una referencia de ensamblado?)**

 Recibirá este error si no agrega el *generatedProxy.cs* (o *generatedProxy.vb*) archivos a su proyecto de cliente cuando se generan con el *Svcutil.exe* herramienta .  

### <a name="run-the-client-application"></a>Ejecute la aplicación cliente

**Excepción no controlada: System.ServiceModel.EndpointNotFoundException: No se pudo conectar con ' http:\//localhost:8000/GettingStarted/CalculatorService '. Código de error TCP 10061: Se realizará ninguna conexión porque el equipo de destino rechazó.**

Este error se produce si ejecuta la aplicación cliente sin iniciar el servicio. En primer lugar, ejecute la aplicación host para iniciar el servicio y, a continuación, ejecute la aplicación cliente.

### <a name="use-the-svcutilexe-tool"></a>Use la herramienta Svcutil.exe
   
**'Svcutil' no se reconoce como un comando interno o externo, programa operable o archivo por lotes.**

 *Svcutil.exe* debe estar en la ruta de acceso del sistema. La solución más sencilla consiste en utilizar el símbolo del sistema de Visual Studio. Desde el **iniciar** menú, seleccione el **Visual Studio \<versión >** directorio, a continuación, seleccione **símbolo del sistema para desarrolladores para VS \<versión >**. Este símbolo se establece la ruta de acceso del sistema en las ubicaciones correctas para todas las herramientas que se incluye como parte de Visual Studio.  
  
### <a name="run-the-service-and-client-applications"></a>Ejecutar las aplicaciones cliente y servicio

**System.ServiceModel.Security.SecurityNegotiationException: Negociación de seguridad SOAP con ' http:\//localhost:8000/GettingStarted/CalculatorService ' para el destino ' http:\//localhost:8000/GettingStarted/CalculatorService ' no se pudo**  

Este error se produce en un equipo unido al dominio que no tiene conectividad de red. Conectar el equipo a la red o desactive la seguridad para el servicio y el cliente. 

Para desactivar la seguridad:

- Para el servicio, reemplace el código que crea el `WSHttpBinding` con el código siguiente:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- Para el cliente, en el archivo de configuración, actualice el  **\<seguridad >** elemento bajo el  **\<enlace >** elemento como sigue:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones de WCF](getting-started-tutorial.md)  
 [Inicio rápido de solución de problemas de WCF](wcf-troubleshooting-quickstart.md)  
 [Solucionar problemas de instalación](troubleshooting-setup-issues.md)
