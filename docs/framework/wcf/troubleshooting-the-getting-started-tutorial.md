---
title: Solución de problemas de los tutoriales Introducción a Windows Communication Foundation
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 73aa0f5784784cb788a7532f8e22cbe925429c41
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249622"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Solución de problemas de los tutoriales Introducción a Windows Communication Foundation

En este artículo se proporcionan soluciones para los problemas y errores más comunes a los que puede enfrentarse al seguir los pasos descritos en el [Tutorial: Introducción a](getting-started-tutorial.md)las aplicaciones de Windows Communication Foundation.
  
## <a name="common-problems"></a>Problemas comunes

**No puedo encontrar los archivos del proyecto en mi disco duro.**

 Visual Studio guarda los archivos de proyecto en *C:-Nombre de usuario de los\\&lt;usuarios&gt;.*  

**No puedo encontrar el archivo *App.config* generado por *Svcutil.exe*.**

 En Visual Studio, la ventana **Agregar elemento existente** solo muestra archivos con las siguientes extensiones de forma predeterminada:

- *.cs*
- *.resx*
- *.settings*
- *.xsd*
- *.wsdl*

Para mostrar todos los tipos de archivo, seleccione **Todos los archivos\*( .\*)** en la lista desplegable en la esquina inferior derecha de la ventana Agregar elemento **existente.**  
  
## <a name="common-errors"></a>Errores comunes

### <a name="compile-the-service-application"></a>Compile la aplicación de servicio

**El error BC30420 'Sub Main' no se encontró en 'GettingStartedHost.Module1'.**

El punto de entrada es incorrecto para la aplicación de Visual Basic. Realice el siguiente cambio:

   1. En la ventana Explorador de **soluciones,** seleccione la carpeta **GettingStartedHost** y, a continuación, seleccione **Propiedades** en el menú contextual.
    a. En la ventana **GettingStartedHost,** para **el objeto Startup**, seleccione **Service.Program** (o el punto de entrada de la aplicación concreta) en la lista.
    b. En el menú principal, seleccione **Guardar** > **archivo todo**.

### <a name="run-the-service-application"></a>Ejecute la aplicación de servicio

**HTTP no pudo registrar\/la DIRECCIÓN URL 'http: /+:8000/GettingStarted/CalculatorService'. El proceso no tiene derechos de acceso a este espacio de nombres.**

 Para un acceso adecuado, inicie el proceso que hospeda el servicio de Windows Communication Foundation (WCF) con privilegios administrativos:

- Para Visual Studio: seleccione el programa de Visual Studio en el menú **Inicio** y, a continuación, seleccione **Más** > **ejecución como administrador** en el menú contextual.
- Para una ventana de consola: seleccione **Símbolo del sistema** en el menú **Inicio** y, a continuación, seleccione **Más** > **administrador de ejecución** en el menú contextual.
- Para el Explorador de Windows: seleccione el archivo ejecutable y, a continuación, seleccione **Ejecutar como administrador** en el menú contextual.

### <a name="compile-the-client-application"></a>Compile la aplicación cliente

**'CalculatorClient', no contiene una\<definición para ' nombre\<de método>' y ningún método de extensión ' nombre de método>' aceptar un primer argumento de tipo 'CalculatorClient' podría encontrarse (¿le falta una directiva using o una referencia de ensamblado?)**  

Solo los métodos que `ServiceOperationAttribute` marque con el atributo se exponen públicamente. Si omite `ServiceOperationAttribute` el atributo de `ICalculator` un método en la interfaz, recibirá este mensaje de error durante la compilación.  

**No se pudo encontrar el nombre de tipo o espacio de nombres 'CalculatorClient' (¿le falta una directiva using o una referencia de ensamblado?)**

 Recibirá este error si no agrega el archivo *generatedProxy.cs* (o *generatedProxy.vb*) al proyecto de cliente cuando los generó con la herramienta *Svcutil.exe.*  

### <a name="run-the-client-application"></a>Ejecute la aplicación cliente

**Excepción no controlada: System.ServiceModel.EndpointNotFoundException: No se\/pudo conectar a 'http: /localhost:8000/GettingStarted/CalculatorService'. Código de error TCP 10061: No se pudo realizar ninguna conexión porque la máquina de destino la rechazó activamente.**

Este error se produce si ejecuta la aplicación cliente sin iniciar primero el servicio. En primer lugar, ejecute la aplicación host para iniciar el servicio y, a continuación, ejecute la aplicación cliente.

### <a name="use-the-svcutilexe-tool"></a>Utilice la herramienta Svcutil.exe

**'Svcutil' no se reconoce como un comando interno o externo, un programa operable o un archivo por lotes.**

 *Svcutil.exe* debe estar en la ruta de acceso del sistema. La solución más fácil es usar el símbolo del sistema de Visual Studio. En el menú **Inicio,** seleccione la **versión de \<Visual Studio>** directorio y, a continuación, seleccione Símbolo del sistema para **desarrolladores para la versión de VS \<>**. Este símbolo del sistema establece la ruta de acceso del sistema a las ubicaciones correctas para todas las herramientas incluidas como parte de Visual Studio.  
  
### <a name="run-the-service-and-client-applications"></a>Ejecute las aplicaciones de servicio y cliente

**System.ServiceModel.Security.SecurityNegotiationException: Error en la\/negociación de seguridad SOAP con 'http: /localhost:8000/GettingStarted/CalculatorService' para el destino 'http:\//localhost:8000/GettingStarted/CalculatorService'**  

Este error se produce en un equipo unido a un dominio que no tiene conectividad de red. Conecte el equipo a la red o desactive la seguridad tanto para el servicio como para el cliente.

Para desactivar la seguridad:

- Para el servicio, reemplace el `WSHttpBinding` código que crea el código siguiente:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- Para el cliente, en el ** \<** archivo de configuración, actualice el elemento de>de seguridad en el ** \<elemento de enlace>** de la siguiente manera:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator">
      <security mode="None" />
    </binding
    ```  

## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones WCF](getting-started-tutorial.md)  
 [Inicio rápido de solución de problemas de WCF](wcf-troubleshooting-quickstart.md)  
 [Solución de problemas de configuración](troubleshooting-setup-issues.md)
