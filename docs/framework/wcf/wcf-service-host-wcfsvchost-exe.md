---
title: Host de servicio WCF (WcfSvcHost.exe)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1da8d7a08e7887e8ba3fd50a8f809e2ff551a7fd
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="wcf-service-host-wcfsvchostexe"></a>Host de servicio WCF (WcfSvcHost.exe)
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Host de servicio (WcfSvcHost.exe) permite iniciar al depurador de Visual Studio (F5) para hospedar y probar un servicio implementado automáticamente. Puede probar el servicio mediante el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) o su propio cliente, para buscar y corregir cualquier error potencial.  
  
## <a name="wcf-service-host"></a>Host de servicio de WCF  
 El host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] enumera los servicios de un proyecto de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], carga la configuración del proyecto y crea una instancia de host por cada servicio que busca. La herramienta está integrada en Visual Studio mediante el [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] plantilla de servicio y se invoca cuando empiece a depurar el proyecto.  
  
 Al usar el host de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], puede hospedar un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (en un proyecto de biblioteca de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]) sin escribir código adicional ni confirmar a un host concreto durante el desarrollo.  
  
> [!NOTE]
>  El host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] no admite la confianza parcial. Si desea usar un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio en confianza parcial, no utilice la [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] plantilla de proyecto de biblioteca de servicio en Visual Studio para compilar su servicio. En su lugar, cree un nuevo sitio Web en Visual Studio eligiendo el [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] plantilla de sitio Web del servicio, que puede hospedar el servicio en un servidor Web en el que [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se admita la confianza parcial.  
  
## <a name="project-types-hosted-by-wcf-service-host"></a>Tipos de proyecto hospedados por el host de servicio de WCF  
 El host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] puede hospedar los tipos de proyecto de biblioteca de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] siguientes: biblioteca de servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], biblioteca de servicio de flujo de trabajo secuencial, biblioteca de servicio de flujo de trabajo de equipo de estado y biblioteca de servicio de sindicación. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host de servicio también puede hospedar los servicios que se pueden agregar a un proyecto de biblioteca de servicio utilizando el **Agregar elemento** funcionalidad. Esto incluye servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], servicio de flujo de trabajo de equipo de estado, servicio de flujo de trabajo secuencial, servicio de flujo de trabajo de equipo de estado XAML y servicio de flujo de trabajo secuencial XAML.  
  
 Debería tener en cuenta, sin embargo, que la herramienta no le ayudará a configurar un host. Para esta tarea debe modificar manualmente el archivo App.config. La herramienta tampoco valida los archivos de configuración definidos por el usuario.  
  
> [!CAUTION]
>  No debería utilizar el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para hospedar los servicios en un entorno de producción, ya que no fue diseñado para este fin.  El host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] no es compatible con la confiabilidad, seguridad y requisitos de capacidad de administración de este tipo de entorno. En su lugar, utilice IIS porque que proporciona confiabilidad y características de supervisión superiores, y es la solución preferida para hospedar servicios. Cuando el desarrollo de sus servicios haya finalizado, debería migrar los servicios del host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a IIS.  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Escenarios para usar el host de servicio de WCF dentro de Visual Studio  
 En la tabla siguiente se enumera todos los parámetros en la **argumentos de línea de comandos** cuadro de diálogo que puede encontrar haciendo clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **Propiedades**, a continuación, seleccione la **depurar** ficha y haga clic en **Iniciar proyecto**. Estos parámetros son útiles para configurar el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
|Parámetro|Significado|  
|---------------|-------------|  
|`/client`|Un parámetro opcional que especifica la ruta de acceso a un ejecutable que se ejecutará una vez hospedados los servicios. Esto inicia el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] después del hospedaje.|  
|`/clientArg`|Especifique una cadena como un argumento que se pasa a la aplicación cliente personalizada.|  
|`/?`|Muestra el texto de ayuda.|  
  
#### <a name="using-wcf-test-client"></a>Utilizar el cliente de prueba de WCF  
 Después de crear un nuevo proyecto de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y presionar F5 para iniciar el depurador, el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] inicia el hospedaje todos los servicios que encuentra en su proyecto. El cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se abre automáticamente y muestra una lista de extremos de servicio definidos en el archivo de configuración. Desde la ventana principal puede probar los parámetros e invocar el servicio.  
  
 Para asegurarse de que [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se utiliza el cliente de prueba, haga clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **propiedades**, a continuación, seleccione la **depurar**ficha. Haga clic en **Iniciar proyecto** y asegúrese de que el siguiente aparece en el **argumentos de línea de comandos** cuadro de diálogo.  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a>Utilizar un cliente personalizado  
 Para utilizar un cliente personalizado, haga clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **propiedades**, a continuación, seleccione la **depurar** ficha. Haga clic en **Iniciar proyecto** y editar la `/client` parámetro en el **argumentos de línea de comandos** cuadro de diálogo para que apunte a su cliente personalizado, como se indica en el ejemplo siguiente.  
  
 `/client:"path/CustomClient.exe"`  
  
 Al presionar F5 para iniciar de nuevo el servicio, el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] inicia automáticamente su cliente personalizado al iniciar el depurador.  
  
 También puede utilizar el parámetro `/clientArg:` para especificar una cadena como argumento que se pasa a la aplicación cliente personalizada, como se indica en el ejemplo siguiente.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 Por ejemplo, si está usando la plantilla de la Biblioteca de servicios de distribución, puede usar los argumentos de línea de comandos siguientes:  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a>Especificación de ningún cliente  
 Para especificar que no se utilizará ningún cliente después de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] alojamiento del servicio, haga clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **propiedades**, a continuación, seleccione la  **Depurar** ficha. Haga clic en **Iniciar proyecto** y dejar el **argumentos de línea de comandos** cuadro de diálogo en blanco.  
  
#### <a name="using-a-custom-host"></a>Utilizar un host personalizado  
 Para usar un host personalizado, haga clic en el proyecto en **el Explorador de soluciones** en Visual Studio, seleccione **propiedades**, a continuación, seleccione la **depurar** ficha. Haga clic en **programa externo de inicio** y escriba la ruta de acceso completa para el host personalizado. También puede usar el **argumentos de línea de comandos** cuadro de diálogo para especificar los argumentos que se pasarán al host.  
  
## <a name="wcf-service-host-user-interface"></a>Interfaz de usuario del host de servicio de WCF  
 Al invocar inicialmente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host de servicio (presionando F5 dentro de Visual Studio), el **Host de servicio WCF** ventana se abre automáticamente. Cuando se está ejecutando el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], el icono del programa aparece en el área de notificación. Haga doble clic en el icono para abrir el **Host de servicio WCF** ventana  
  
 Cuando se producen errores durante el hospedaje de servicio, el cuadro de diálogo del host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se abrirá para mostrar la información pertinente.  
  
 El **Host de servicio WCF** ventana principal contiene dos menús:  
  
-   **Archivo**: contiene la **cerrar** y **Exit** comandos. Al hacer clic en **cerrar**, **Host de servicio WCF** cuadro de diálogo se cierra, pero los servicios siguen estando hospedados. Al hacer clic en **Exit**, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] también se apaga el Host de servicio. Esto también detiene todos los servicios hospedados.  
  
-   **Ayudar a**: contiene la **sobre** comando que contiene información de versión. También contiene el **ayuda** comandos que pueden abrir un archivo de ayuda.  
  
 El método main **Host de servicio WCF** ventana contiene dos áreas:  
  
-   La primera área es **servicio**. Contiene una lista que muestra información básica de todos los servicios. La información incluye:  
  
    -   **Servicio**: muestra todos los servicios.  
  
    -   **Estado**: muestra el estado del servicio. Los valores válidos son "Iniciado", "Stopped" y "Error".  
  
    -   **Dirección de metadatos**: muestra la dirección de metadatos de los servicios.  
  
-   La segunda área es **información adicional**. Muestra una explicación detallada del estado del servicio cuando se selecciona la línea del servicio concreta en el **servicio** área. Si el estado es Error, puede ver el mensaje de error completo en la pantalla.  
  
## <a name="stopping-wcf-service-host"></a>Detener el host de servicio de WCF  
 Puede cerrar el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] de las cuatro maneras siguientes:  
  
-   Detener la sesión de depuración en Visual Studio.  
  
-   Seleccione **Exit** desde el **archivo** menú en el **Host de servicio WCF** ventana.  
  
-   Seleccione **Exit** desde el menú contextual de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] icono de bandeja del Host de servicio en el área de notificación del sistema.  
  
-   Salga del cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] si lo está utilizando.  
  
## <a name="using-service-host-without-administrator-privilege"></a>Uso del host de servicio sin privilegios de administrador  
 Permitir a los usuarios sin privilegios de administrador para desarrollar [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, se crea una ACL (lista de Control de acceso) para el espacio de nombres "http://+:8731/Design_Time_Addresses" durante la instalación de Visual Studio. La ACL se establece en la interfaz de usuario (UI), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo. Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite a los usuarios utilizar el host automático de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfSvcHost.exe) sin concederles privilegios de administrador.  
  
 Puede modificar el acceso mediante la herramienta netsh.exe en [!INCLUDE[wv](../../../includes/wv-md.md)], en la cuenta de administrador elevada. El siguiente ejemplo muestra la utilización de netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Para obtener más información sobre netsh.exe, consulte "[cómo usar la herramienta Netsh.exe y los modificadores de línea de comandos](http://go.microsoft.com/fwlink/?LinkId=97877)".  
  
## <a name="see-also"></a>Vea también  
 [Cliente de prueba de WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
