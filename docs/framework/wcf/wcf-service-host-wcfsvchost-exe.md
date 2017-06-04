---
title: "Host de servicio WCF (WcfSvcHost.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
caps.latest.revision: 27
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 27
---
# Host de servicio WCF (WcfSvcHost.exe)
El host de servicio \(WcfSvcHost.exe\) [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] permite iniciar el depurador \(F5\) [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para hospedar y probar automáticamente un servicio implementado.Puede probar el servicio mediante el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(WcfTestClient.exe\) o su propio cliente, para buscar y corregir cualquier error potencial.  
  
## Host de servicio de WCF  
 El host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] enumera los servicios de un proyecto de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], carga la configuración del proyecto y crea una instancia de host por cada servicio que busca.La herramienta está integrada en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] a través de la plantilla Servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y se invoca al empezar a depurar el proyecto.  
  
 Al usar el host de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], puede hospedar un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(en un proyecto de biblioteca de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\) sin escribir código adicional ni confirmar a un host concreto durante el desarrollo.  
  
> [!NOTE]
>  El host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] no admite la confianza parcial.Si desea utilizar un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en confianza parcial, no utilice la plantilla del proyecto de biblioteca de servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para crear su servicio.En su lugar, cree un nuevo sitio web en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] eligiendo la plantilla de sitio web de servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], que puede hospedar el servicio en un WebServer en el que se admita la confianza parcial de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
## Tipos de proyecto hospedados por el host de servicio de WCF  
 El host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] puede hospedar los tipos de proyecto de biblioteca de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] siguientes: biblioteca de servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], biblioteca de servicio de flujo de trabajo secuencial, biblioteca de servicio de flujo de trabajo de equipo de estado y biblioteca de servicio de sindicación.El host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] también puede hospedar los servicios que se pueden agregar a un proyecto de biblioteca de servicio utilizando la funcionalidad **Agregar elemento**.Esto incluye servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], servicio de flujo de trabajo de equipo de estado, servicio de flujo de trabajo secuencial, servicio de flujo de trabajo de equipo de estado XAML y servicio de flujo de trabajo secuencial XAML.  
  
 Debería tener en cuenta, sin embargo, que la herramienta no le ayudará a configurar un host.Para esta tarea debe modificar manualmente el archivo App.config.La herramienta tampoco valida los archivos de configuración definidos por el usuario.  
  
> [!CAUTION]
>  No debería utilizar el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para hospedar los servicios en un entorno de producción, ya que no fue diseñado para este fin.El host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] no es compatible con la confiabilidad, seguridad y requisitos de capacidad de administración de este tipo de entorno.En su lugar, utilice IIS porque que proporciona confiabilidad y características de supervisión superiores, y es la solución preferida para hospedar servicios.Cuando el desarrollo de sus servicios haya finalizado, debería migrar los servicios del host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a IIS.  
  
## Escenarios para usar el host de servicio de WCF dentro de Visual Studio  
 La tabla siguiente ofrece una lista de todos los parámetros en el cuadro de diálogo **Argumentos de la línea de comandos**, que se puede buscar haciendo clic con el botón secundario en su proyecto en el **Explorador de soluciones**, en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], seleccionando **Propiedades**, seleccionando a continuación la pestaña **Depurar** y haciendo clic en **Iniciar proyecto**.Estos parámetros son útiles para configurar el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
|Parámetro|Significado|  
|---------------|-----------------|  
|`/client`|Un parámetro opcional que especifica la ruta de acceso a un ejecutable que se ejecutará una vez hospedados los servicios.Esto inicia el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] después del hospedaje.|  
|`/clientArg`|Especifique una cadena como un argumento que se pasa a la aplicación cliente personalizada.|  
|`/?`|Muestra el texto de ayuda.|  
  
#### Utilizar el cliente de prueba de WCF  
 Después de crear un nuevo proyecto de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y presionar F5 para iniciar el depurador, el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] inicia el hospedaje todos los servicios que encuentra en su proyecto.El cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se abre automáticamente y muestra una lista de extremos de servicio definidos en el archivo de configuración.Desde la ventana principal puede probar los parámetros e invocar el servicio.  
  
 Para asegurarse de que se utiliza ese cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], haga clic con el botón secundario en su proyecto en **Explorador de soluciones**, en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], seleccione **Propiedades** y, a continuación, seleccione la pestaña **Depurar**.Haga clic en **Iniciar proyecto** y asegúrese de que lo siguiente aparece en el cuadro de diálogo **Argumentos de la línea de comandos**.  
  
 `/client:WcfTestClient.exe`  
  
#### Utilizar un cliente personalizado  
 Para utilizar un cliente personalizado, haga clic con el botón secundario en su proyecto en **Explorador de soluciones** en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], seleccione **Propiedades** y, a continuación, seleccione la pestaña **Depurar**.Haga clic en **Iniciar proyecto** y modifique el parámetro `/client` en el cuadro de diálogo **Argumentos de la línea de comandos** para indicar su cliente personalizado, como se indica en el ejemplo siguiente.  
  
 `/client:"path/CustomClient.exe"`  
  
 Al presionar F5 para iniciar de nuevo el servicio, el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] inicia automáticamente su cliente personalizado al iniciar el depurador.  
  
 También puede utilizar el parámetro `/clientArg:` para especificar una cadena como argumento que se pasa a la aplicación cliente personalizada, como se indica en el ejemplo siguiente.  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 Por ejemplo, si está usando la plantilla de la biblioteca de servicio de distribución, puede usar los argumentos de línea de comandos siguientes:  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### Especificación de ningún cliente  
 Para especificar que no se utilizará ningún cliente después del alojamiento del servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], haga clic con el botón secundario en su proyecto en **Explorador de soluciones**, en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], seleccione **Propiedades**y, a continuación, seleccione la pestaña **Depurar**.Haga clic en **Iniciar proyecto** y deje en blanco el cuadro de diálogo **Argumentos de la línea de comandos**.  
  
#### Utilizar un host personalizado  
 Para utilizar un host personalizado, haga clic con el botón secundario en su proyecto en **Explorador de soluciones** en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], seleccione **Propiedades** y, a continuación, seleccione la pestaña **Depurar**.Haga clic en **Iniciar programa externo** y escriba la ruta de acceso completa al host personalizado.También puede utilizar el cuadro de diálogo **Argumentos de la línea de comandos** para especificar argumentos que se van a pasar al host.  
  
## Interfaz de usuario del host de servicio de WCF  
 Al invocar inicialmente el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(presionando F5 dentro de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]\), la ventana **Host de servicio de WCF** se abre automáticamente.Cuando se está ejecutando el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], el icono del programa aparece en el área de notificación.Haga doble clic en el icono para abrir la ventana **Host de servicio de WCF**  
  
 Cuando se producen errores durante el hospedaje de servicio, el cuadro de diálogo del host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se abrirá para mostrar la información pertinente.  
  
 La ventana principal del **Host de servicio de WCF** contiene dos menús:  
  
-   **Archivo**: contiene los comandos **Cerrar** y **Salir**.Al hacer clic en **Cerrar**, el cuadro de diálogo **Host de servicio de WCF** se cierra, pero se siguen hospedando los servicios.Al hacer clic en **Salir**, también se apaga el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Esto también detiene todos los servicios hospedados.  
  
-   **Ayuda**: contiene el comando **Acerca de** que contiene información de versión.También contiene el comando **Ayuda**, que puede abrir un archivo de ayuda.  
  
 La ventana principal del **Host de servicio de WCF** contiene dos áreas:  
  
-   La primera área es **Servicio**.Contiene una lista que muestra información básica de todos los servicios.La información incluye:  
  
    -   **Servicio**: muestra una lista de todos los servicios.  
  
    -   **Estado**: muestra el estado del servicio.Los valores válidos son “Iniciado”, “Detenido” y “Error”.  
  
    -   **Dirección de metadatos**: muestra la dirección de los metadatos de los servicios.  
  
-   La segunda área es **Información adicional**.Muestra una explicación detallada del estado del servicio cuando la línea del servicio concreta está seleccionada en el área **Servicio**.Si el estado es Error, puede ver el mensaje de error completo en la pantalla.  
  
## Detener el host de servicio de WCF  
 Puede cerrar el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] de las cuatro maneras siguientes:  
  
-   Detenga la sesión de depuración en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
-   Seleccione **Salir** en el menú **Archivo** en la ventana **Host de servicio de WCF**.  
  
-   Seleccione **Salir** en el menú contextual del icono de la bandeja del host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en el área de notificación de sistema.  
  
-   Salga del cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] si lo está utilizando.  
  
## Uso del host de servicio sin privilegios de administrador  
 Para permitir que los usuarios sin el privilegio de administrador desarrollen servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], se crea una ACL \(Lista de control de acceso\) para el espacio de nombres "http:\/\/\+:8731\/Design\_Time\_Addresses" durante la instalación de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].La ACL se establece en la interfaz de usuario \(UI\), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo.Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite a los usuarios utilizar el host automático de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(wcfSvcHost.exe\) sin concederles privilegios de administrador.  
  
 Puede modificar el acceso mediante la herramienta netsh.exe en [!INCLUDE[wv](../../../includes/wv-md.md)], en la cuenta de administrador elevada.El siguiente ejemplo muestra la utilización de netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Para obtener más información sobre netsh.exe, consulte "[How to Use the Netsh.exe Tool and Command\-Line Switches](http://go.microsoft.com/fwlink/?LinkId=97877)".  
  
## Vea también  
 [Cliente de prueba de WCF \(WcfTestClient.exe\)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)