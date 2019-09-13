---
title: Solución de problemas de introducción a los tutoriales de Windows Communication Foundation
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 10a2f8f718d802a7aab067b882f0d5cf3dc28dca
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928576"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>Solución de problemas de introducción a los tutoriales de Windows Communication Foundation

En este artículo se proporcionan soluciones para los problemas y errores más comunes que pueden surgir al seguir los pasos [del tutorial: Introducción a las aplicaciones](getting-started-tutorial.md)Windows Communication Foundation. 
  
## <a name="common-problems"></a>Problemas habituales

**No encuentro los archivos del proyecto en el disco duro.**

 Visual Studio guarda los archivos de proyecto en *\\C:\Users&gt;&lt;nombre de usuario \source\repos*.  

**No encuentro el archivo *app. config* generado por *SvcUtil. exe*.**

 En Visual Studio, la ventana **Agregar elemento existente** solo muestra de forma predeterminada los archivos con las siguientes extensiones: 

- *.cs* 
- *.resx* 
- *.settings*
- *.xsd* 
- *.wsdl*

Para mostrar todos los tipos de archivo, seleccione **todos\*los\*archivos (.)** en la lista desplegable de la esquina inferior derecha de la ventana **Agregar elemento existente** .  
  
## <a name="common-errors"></a>Errores comunes

### <a name="compile-the-service-application"></a>Compilar la aplicación de servicio 

**No se encontró el error BC30420 ' Sub Main ' en ' GettingStartedHost. Module1 '.**

El punto de entrada no es correcto para la aplicación Visual Basic. Realice el cambio siguiente:

   1. En la ventana **Explorador de soluciones** , seleccione la carpeta **GettingStartedHost** y, a continuación, seleccione **propiedades** en el menú contextual.
    a. En la ventana **GettingStartedHost** , en **objeto de inicio**, seleccione **Service. Program** (o el punto de entrada de su aplicación en particular) en la lista. 
    b. En el menú principal, seleccione **archivo** > **guardar todo**.

### <a name="run-the-service-application"></a>Ejecutar la aplicación de servicio 

**Http no pudo registrar la dirección URL '\/http:/+: 8000/gettingstarted/CalculatorService '. Su proceso no tiene los derechos de acceso a este espacio de nombres.** 

 Para obtener un acceso adecuado, inicie el proceso que hospeda el servicio Windows Communication Foundation (WCF) con privilegios administrativos:

- Para Visual Studio: Seleccione el programa de Visual Studio en el menú **Inicio** y, a continuación, seleccione **más** > **Ejecutar como administrador** en el menú contextual.
- Para una ventana de consola: Seleccione **símbolo del sistema** en el menú **Inicio** y, a continuación, seleccione **más** > **Ejecutar como administrador** en el menú contextual.
- En el explorador de Windows: Seleccione el archivo ejecutable y, a continuación, seleccione **Ejecutar como administrador** en el menú contextual.

### <a name="compile-the-client-application"></a>Compilar la aplicación cliente

**' CalculatorClient ' no contiene una definición para '\<nombre de método > ' y no se encontró ningún método de extensión '\<nombre de método > ' que acepte un primer argumento de tipo ' CalculatorClient ' (¿falta una directiva using o una referencia de ensamblado?)**  

Solo los métodos marcados con el `ServiceOperationAttribute` atributo se exponen públicamente. Si omite el `ServiceOperationAttribute` atributo de un método en la `ICalculator` interfaz, recibirá este mensaje de error durante la compilación.  

**No se pudo encontrar el tipo o el nombre de espacio de nombres ' CalculatorClient ' (¿falta una directiva using o una referencia de ensamblado?)**

 Recibirá este error si no agrega el archivo *generatedProxy.CS* (o *generatedProxy. VB*) al proyecto de cliente cuando lo generó con la herramienta *SvcUtil. exe* .  

### <a name="run-the-client-application"></a>Ejecutar la aplicación cliente

**Excepción no controlada: System.ServiceModel.EndpointNotFoundException: No se pudo conectar a ' http\/:/localhost: 8000/gettingstarted/CalculatorService '. Código de error de TCP 10061: No se pudo establecer ninguna conexión porque el equipo de destino la rechazó activamente.**

Este error se produce si se ejecuta la aplicación cliente sin iniciar primero el servicio. En primer lugar, ejecute la aplicación host para iniciar el servicio y, a continuación, ejecute la aplicación cliente.

### <a name="use-the-svcutilexe-tool"></a>Usar la herramienta SvcUtil. exe
   
**' SvcUtil ' no se reconoce como un comando interno o externo, un programa ejecutable o un archivo por lotes.**

 *SvcUtil. exe* debe estar en la ruta de acceso del sistema. La solución más sencilla es usar el símbolo del sistema de Visual Studio. En el menú **Inicio** , seleccione la **versión de \<Visual Studio >** directorio y, a continuación, seleccione **símbolo del sistema para desarrolladores para la versión \<de VS >** . Este símbolo del sistema establece la ruta de acceso del sistema a las ubicaciones correctas de todas las herramientas que se incluyen como parte de Visual Studio.  
  
### <a name="run-the-service-and-client-applications"></a>Ejecutar el servicio y las aplicaciones cliente

**System.ServiceModel.Security.SecurityNegotiationException: Error de negociación de seguridad SOAP con\/' http:/localhost: 8000/gettingstarted/CalculatorService ' para el\/destino ' http:/localhost: 8000/gettingstarted/CalculatorService '**  

Este error se produce en un equipo unido a un dominio que no tiene conectividad de red. Conecte el equipo a la red o desactive la seguridad para el servicio y el cliente. 

Para desactivar la seguridad:

- En el caso del servicio, reemplace el código que `WSHttpBinding` crea con el código siguiente:  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- En el caso del cliente, en el archivo de configuración  **\<** , actualice el elemento de  **\<** > de seguridad en el elemento de > de enlace como se indica a continuación:  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones WCF](getting-started-tutorial.md)  
 [Guía de inicio rápido de solución de problemas de WCF](wcf-troubleshooting-quickstart.md)  
 [Solucionar problemas de instalación](troubleshooting-setup-issues.md)
