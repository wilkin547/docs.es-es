---
title: Host de servicio WCF (WcfSvcHost.exe)
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: e1e258015adc34edd4a109f3bc5a32b4bf6f0296
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="wcf-service-host-wcfsvchostexe"></a>Host de servicio WCF (WcfSvcHost.exe)
Host de servicio de Windows Communication Foundation (WCF) (WcfSvcHost.exe) permite iniciar al depurador de Visual Studio (F5) para hospedar y probar un servicio implementado automáticamente. A continuación, puede probar el servicio mediante el cliente de prueba de WCF (WcfTestClient.exe) o su propio cliente, para buscar y corregir cualquier error potencial.  
  
## <a name="wcf-service-host"></a>Host de servicio de WCF  
 Host de servicio WCF enumera los servicios de un proyecto de servicio WCF, carga la configuración del proyecto y crea una instancia de un host para cada servicio que busca. La herramienta está integrada en Visual Studio a través de la plantilla de servicio de WCF y se invoca cuando empiece a depurar el proyecto.  
  
 Mediante el uso de Host de servicio WCF, puede hospedar un servicio WCF (en un proyecto de biblioteca de servicio WCF) sin escribir código adicional ni confirmar a un host concreto durante el desarrollo.  
  
> [!NOTE]
>  Host de servicio WCF no admite la confianza parcial. Si desea utilizar un servicio de WCF en confianza parcial, no utilice la plantilla de proyecto de biblioteca de servicio WCF en Visual Studio para generar su servicio. En su lugar, cree un nuevo sitio Web en Visual Studio seleccionando la plantilla del sitio Web de servicios de WCF, que puede hospedar el servicio en un servidor Web en el que se admita la confianza parcial de WCF.  
  
## <a name="project-types-hosted-by-wcf-service-host"></a>Tipos de proyecto hospedados por el host de servicio de WCF  
 Host de servicio WCF puede hospedar los siguientes tipos de proyecto de biblioteca de servicio WCF: biblioteca de servicios WCF, biblioteca de servicio de flujo de trabajo secuencial, biblioteca de servicio de flujo de trabajo de equipo de estado y biblioteca de servicio de distribución. Host de servicio WCF también puede hospedar los servicios que se pueden agregar a un proyecto de biblioteca de servicio utilizando el **Agregar elemento** funcionalidad. Esto incluye el servicio de WCF, servicio de máquina de estado de WF, servicio de WF secuencial, servicio de máquina de estado de WF de XAML y servicio de WF secuencial de XAML.  
  
 Debería tener en cuenta, sin embargo, que la herramienta no le ayudará a configurar un host. Para esta tarea debe modificar manualmente el archivo App.config. La herramienta tampoco valida los archivos de configuración definidos por el usuario.  
  
> [!CAUTION]
>  No debe usar el Host de servicio WCF para hospedar los servicios en un entorno de producción, ya que no fue diseñado para este propósito.  Host de servicio WCF no es compatible con la confiabilidad, seguridad y requisitos de capacidad de administración de un entorno de este tipo. En su lugar, utilice IIS porque que proporciona confiabilidad y características de supervisión superiores, y es la solución preferida para hospedar servicios. Una vez completado el desarrollo de sus servicios, debería migrar los servicios de Host de servicio WCF en IIS.  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Escenarios para usar el host de servicio de WCF dentro de Visual Studio  
 En la tabla siguiente se enumera todos los parámetros en la **argumentos de línea de comandos** cuadro de diálogo que puede encontrar haciendo clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **Propiedades**, a continuación, seleccione la **depurar** ficha y haga clic en **Iniciar proyecto**. Estos parámetros son útiles para configurar el Host de servicio WCF.  
  
|Parámetro|Significado|  
|---------------|-------------|  
|`/client`|Un parámetro opcional que especifica la ruta de acceso a un ejecutable que se ejecutará una vez hospedados los servicios. Esto inicia el cliente de prueba WCF después del hospedaje.|  
|`/clientArg`|Especifique una cadena como un argumento que se pasa a la aplicación cliente personalizada.|  
|`/?`|Muestra el texto de ayuda.|  
  
#### <a name="using-wcf-test-client"></a>Utilizar el cliente de prueba de WCF  
 Después de crear un nuevo proyecto de servicio WCF y presione F5 para iniciar al depurador, el Host del servicio de WCF inicia el hospedaje todos los servicios que encuentra en su proyecto. Cliente de prueba WCF automáticamente se abre y muestra una lista de extremos de servicio definidos en el archivo de configuración. Desde la ventana principal puede probar los parámetros e invocar el servicio.  
  
 Para asegurarse de que se usa el cliente de prueba WCF, haga clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **propiedades**, a continuación, seleccione la **depurar** ficha. Haga clic en **Iniciar proyecto** y asegúrese de que el siguiente aparece en el **argumentos de línea de comandos** cuadro de diálogo.  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a>Utilizar un cliente personalizado  
 Para utilizar un cliente personalizado, haga clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **propiedades**, a continuación, seleccione la **depurar** ficha. Haga clic en **Iniciar proyecto** y editar la `/client` parámetro en el **argumentos de línea de comandos** cuadro de diálogo para que apunte a su cliente personalizado, como se indica en el ejemplo siguiente.  
  
 `/client:"path/CustomClient.exe"`  
  
 Cuando se presiona F5 para iniciar el servicio nuevo, Host de servicio WCF se inicia automáticamente su cliente personalizado al iniciar el depurador.  
  
 También puede utilizar el parámetro `/clientArg:` para especificar una cadena como argumento que se pasa a la aplicación cliente personalizada, como se indica en el ejemplo siguiente.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 Por ejemplo, si está usando la plantilla de la Biblioteca de servicios de distribución, puede usar los argumentos de línea de comandos siguientes:  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a>Especificación de ningún cliente  
 Para especificar que no se utilizará ningún cliente después de hospedaje de servicios WCF, haga clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **propiedades**, a continuación, seleccione la **depurar** ficha. Haga clic en **Iniciar proyecto** y dejar el **argumentos de línea de comandos** cuadro de diálogo en blanco.  
  
#### <a name="using-a-custom-host"></a>Utilizar un host personalizado  
 Para usar un host personalizado, haga clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **propiedades**, a continuación, seleccione la **depurar** ficha. Haga clic en **programa externo de inicio** y escriba la ruta de acceso completa para el host personalizado. También puede usar el **argumentos de línea de comandos** cuadro de diálogo para especificar los argumentos que se pasarán al host.  
  
## <a name="wcf-service-host-user-interface"></a>Interfaz de usuario del host de servicio de WCF  
 Al invocar inicialmente el Host del servicio de WCF (presionando F5 dentro de Visual Studio), el **Host de servicio WCF** ventana se abre automáticamente. Cuando se ejecuta el Host de servicio WCF, el icono del programa aparece en el área de notificación. Haga doble clic en el icono para abrir el **Host de servicio WCF** ventana  
  
 Cuando se producen errores durante el hospedaje de servicio, se abrirá el cuadro de diálogo de Host de servicio WCF para mostrar la información pertinente.  
  
 El **Host de servicio WCF** ventana principal contiene dos menús:  
  
-   **Archivo**: contiene la **cerrar** y **Exit** comandos. Al hacer clic en **cerrar**, **Host de servicio WCF** cuadro de diálogo se cierra, pero los servicios siguen estando hospedados. Al hacer clic en **Exit**, también se apaga el Host de servicio WCF. Esto también detiene todos los servicios hospedados.  
  
-   **Ayudar a**: contiene la **sobre** comando que contiene información de versión. También contiene el **ayuda** comandos que pueden abrir un archivo de ayuda.  
  
 El método main **Host de servicio WCF** ventana contiene dos áreas:  
  
-   La primera área es **servicio**. Contiene una lista que muestra información básica de todos los servicios. La información incluye:  
  
    -   **Servicio**: muestra todos los servicios.  
  
    -   **Estado**: muestra el estado del servicio. Los valores válidos son "Iniciado", "Stopped" y "Error".  
  
    -   **Dirección de metadatos**: muestra la dirección de metadatos de los servicios.  
  
-   La segunda área es **información adicional**. Muestra una explicación detallada del estado del servicio cuando se selecciona la línea del servicio concreta en el **servicio** área. Si el estado es Error, puede ver el mensaje de error completo en la pantalla.  
  
## <a name="stopping-wcf-service-host"></a>Detener el host de servicio de WCF  
 Puede apagar el Host de servicio WCF en las cuatro maneras siguientes:  
  
-   Detener la sesión de depuración en Visual Studio.  
  
-   Seleccione **Exit** desde el **archivo** menú en el **Host de servicio WCF** ventana.  
  
-   Seleccione **Exit** desde el menú contextual del icono de bandeja del Host de servicio WCF en el área de notificación del sistema.  
  
-   Salga de cliente de prueba WCF si está en uso.  
  
## <a name="using-service-host-without-administrator-privilege"></a>Uso del host de servicio sin privilegios de administrador  
 Para permitir que usuarios sin privilegios de administrador desarrollar servicios WCF, se crea una ACL (lista de Control de acceso) para el espacio de nombres "http://+:8731/Design_Time_Addresses" durante la instalación de Visual Studio. La ACL se establece en la interfaz de usuario (UI), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo. Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite a los usuarios utilizar al Host de servicio WCF (wcfSvcHost.exe) sin concederles privilegios de administrador.  
  
 Puede modificar el acceso mediante la herramienta netsh.exe en [!INCLUDE[wv](../../../includes/wv-md.md)], en la cuenta de administrador elevada. El siguiente ejemplo muestra la utilización de netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Para obtener más información sobre netsh.exe, consulte "[cómo usar la herramienta Netsh.exe y los modificadores de línea de comandos](http://go.microsoft.com/fwlink/?LinkId=97877)".  
  
## <a name="see-also"></a>Vea también  
 [Cliente de prueba de WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
