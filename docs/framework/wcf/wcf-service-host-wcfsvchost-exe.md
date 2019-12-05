---
title: Host de servicio WCF (WcfSvcHost.exe)
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: c855fe7cc804fac14348990b7a6f5f84a0956b0c
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802414"
---
# <a name="wcf-service-host-wcfsvchostexe"></a>Host de servicio WCF (WcfSvcHost.exe)

El host de servicio de Windows Communication Foundation (WCF) (WcfSvcHost. exe) permite iniciar el depurador de Visual Studio (F5) para hospedar y probar automáticamente un servicio implementado. Después, puede probar el servicio mediante el cliente de prueba de WCF (WcfTestClient. exe) o su propio cliente, para buscar y corregir los posibles errores.

## <a name="wcf-service-host"></a>Host de servicio de WCF

El host de servicio WCF enumera los servicios de un proyecto de servicio WCF, carga la configuración del proyecto y crea una instancia de un host para cada servicio que encuentra. La herramienta se integra en Visual Studio a través de la plantilla de servicio de WCF y se invoca cuando se inicia la depuración del proyecto.

Mediante el host de servicio WCF, puede hospedar un servicio WCF (en un proyecto de biblioteca de servicios WCF) sin escribir código adicional ni confirmar a un host concreto durante el desarrollo.

> [!NOTE]
> El host de servicio WCF no admite la confianza parcial. Si desea usar un servicio WCF en confianza parcial, no use la plantilla de proyecto Biblioteca de servicios WCF de Visual Studio para compilar el servicio. En su lugar, cree un nuevo sitio web en Visual Studio; para ello, elija la plantilla sitio web del servicio WCF, que puede hospedar el servicio en un servidor Web en el que se admita la confianza parcial de WCF.

## <a name="project-types-hosted-by-wcf-service-host"></a>Tipos de proyecto hospedados por el host de servicio de WCF

El host de servicio WCF puede hospedar los siguientes tipos de proyecto de biblioteca de servicios WCF: biblioteca de servicios WCF, biblioteca de servicio de flujo de trabajo secuencial, biblioteca de servicio de flujo de trabajo de equipo de estado y biblioteca de servicios de distribución. El host de servicio WCF también puede hospedar los servicios que se pueden agregar a un proyecto de biblioteca de servicios mediante la funcionalidad **Agregar elemento** . Esto incluye el servicio WCF, el servicio de máquina de Estados de WF, el servicio secuencial de WF, el servicio de máquina de Estados de WF XAML y el servicio secuencial de WF XAML.

Debería tener en cuenta, sin embargo, que la herramienta no le ayudará a configurar un host. Para esta tarea debe modificar manualmente el archivo App.config. La herramienta tampoco valida los archivos de configuración definidos por el usuario.

> [!CAUTION]
> No debe utilizar el host de servicio WCF para hospedar servicios en un entorno de producción, ya que no se ha diseñado para este fin.  El host de servicio WCF no es compatible con los requisitos de confiabilidad, seguridad y capacidad de administración de este tipo de entorno. En su lugar, utilice IIS porque que proporciona confiabilidad y características de supervisión superiores, y es la solución preferida para hospedar servicios. Una vez completado el desarrollo de los servicios, debe migrar los servicios del host de servicio WCF a IIS.

## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Escenarios para usar el host de servicio de WCF dentro de Visual Studio

En la tabla siguiente se enumeran todos los parámetros del cuadro de diálogo argumentos de la **línea de comandos** , que se pueden encontrar al hacer clic con el botón derecho en el proyecto en el **Explorador de soluciones** en Visual Studio, seleccionar **propiedades**, seleccionar la pestaña **depurar** y hacer clic en **iniciar proyecto**. Estos parámetros son útiles para configurar el host de servicio WCF.

|Parámetro|Significado|
|---------------|-------------|
|`/client`|Un parámetro opcional que especifica la ruta de acceso a un ejecutable que se ejecutará una vez hospedados los servicios. Esto inicia el cliente de prueba de WCF después del hospedaje.|
|`/clientArg`|Especifique una cadena como un argumento que se pasa a la aplicación cliente personalizada.|
|`/?`|Muestra el texto de ayuda.|

#### <a name="using-wcf-test-client"></a>Utilizar el cliente de prueba de WCF

Después de crear un nuevo proyecto de servicio WCF y presionar F5 para iniciar el depurador, el host de servicio WCF comienza a hospedar todos los servicios que encuentra en el proyecto. El cliente de prueba de WCF se abre automáticamente y muestra una lista de los puntos de conexión de servicio definidos en el archivo de configuración. Desde la ventana principal puede probar los parámetros e invocar el servicio.

Para asegurarse de que se usa el cliente de prueba WCF, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** en Visual Studio, seleccione **propiedades**y, a continuación, seleccione la pestaña **depurar** . Haga clic en **iniciar proyecto** y asegúrese de que aparece lo siguiente en el cuadro de diálogo argumentos de la **línea de comandos** .

`/client:WcfTestClient.exe`

#### <a name="using-a-custom-client"></a>Utilizar un cliente personalizado

Para usar un cliente personalizado, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** en Visual Studio, seleccione **propiedades**y, a continuación, seleccione la pestaña **depurar** . Haga clic en **iniciar proyecto** y modifique el parámetro `/client` en el cuadro de diálogo argumentos de la **línea de comandos** para que apunte al cliente personalizado, como se indica en el ejemplo siguiente.

`/client:"path/CustomClient.exe"`

Al presionar F5 para volver a iniciar el servicio, el host de servicio WCF inicia automáticamente el cliente personalizado cuando se inicia el depurador.

También puede utilizar el parámetro `/clientArg:` para especificar una cadena como argumento que se pasa a la aplicación cliente personalizada, como se indica en el ejemplo siguiente.

`/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`

Por ejemplo, si está usando la plantilla de la Biblioteca de servicios de distribución, puede usar los argumentos de línea de comandos siguientes:

`/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`

#### <a name="specifying-no-client"></a>Especificación de ningún cliente

Para especificar que no se usará ningún cliente después de hospedar el servicio WCF, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** en Visual Studio, seleccione **propiedades**y, a continuación, seleccione la pestaña **depurar** . Haga clic en **iniciar proyecto** y deje en blanco el cuadro de diálogo argumentos de la **línea de comandos** .

#### <a name="using-a-custom-host"></a>Utilizar un host personalizado

Para usar un host personalizado, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** en Visual Studio, seleccione **propiedades**y, a continuación, seleccione la pestaña **depurar** . Haga clic en **iniciar programa externo** y escriba la ruta de acceso completa al host personalizado. También puede usar el cuadro de diálogo argumentos de la **línea de comandos** para especificar los argumentos que se pasarán al host.

## <a name="wcf-service-host-user-interface"></a>Interfaz de usuario del host de servicio de WCF

Al invocar inicialmente el host de servicio WCF (presionando F5 dentro de Visual Studio), se abre automáticamente la ventana **host de servicio WCF** . Cuando se está ejecutando el host de servicio WCF, el icono del programa aparece en el área de notificación. Haga doble clic en el icono para abrir la ventana **host de servicio WCF** .

Cuando se produzcan errores durante el hospedaje del servicio, se abrirá el cuadro de diálogo host del servicio WCF para mostrar la información pertinente.

La ventana principal del **host de servicio WCF** contiene dos menús:

- **Archivo**: contiene los comandos **cerrar** y **salir** . Al hacer clic en **cerrar**, se cierra el cuadro de diálogo **host del servicio WCF** , pero se siguen hospedando los servicios. Al hacer clic en **salir**, también se cierra el host de servicio WCF. Esto también detiene todos los servicios hospedados.

- **Ayuda**: contiene el comando **About** que contiene información de versión. También contiene el comando **ayuda** que puede abrir un archivo de ayuda.

La ventana principal del **host de servicio WCF** contiene dos áreas:

- La primera área es **Service**. Contiene una lista que muestra información básica de todos los servicios. La información incluye:

  - **Servicio**: enumera todos los servicios.

  - **Estado**: muestra el estado del servicio. Los valores válidos son "Started", "Stopped" y "error".

  - **Dirección de metadatos**: muestra la dirección de los metadatos de los servicios.

- La segunda área es **información adicional**. Muestra una explicación detallada del estado del servicio cuando se selecciona la línea de servicio específica en el área de **servicio** . Si el estado es Error, puede ver el mensaje de error completo en la pantalla.

## <a name="stopping-wcf-service-host"></a>Detener el host de servicio de WCF

Puede cerrar el host de servicio WCF de las cuatro maneras siguientes:

- Detenga la sesión de depuración en Visual Studio.

- Seleccione **salir** en el menú **archivo** de la ventana **host de servicio WCF** .

- Seleccione **salir** en el menú contextual del icono de la bandeja del host del servicio WCF en el área de notificación del sistema.

- Salga del cliente de prueba de WCF si se está utilizando.

## <a name="using-service-host-without-administrator-privilege"></a>Uso del host de servicio sin privilegios de administrador

Para permitir que los usuarios sin privilegios de administrador desarrollen servicios WCF, se crea una ACL (lista de Access Control) para el espacio de nombres "http://+:8731/Design_Time_Addresses" durante la instalación de Visual Studio. La ACL se establece en la interfaz de usuario (UI), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo. Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite a los usuarios utilizar el host automático del servicio WCF (wcfSvcHost. exe) sin concederles privilegios de administrador.

Puede modificar el acceso mediante la herramienta netsh.exe en [!INCLUDE[wv](../../../includes/wv-md.md)], en la cuenta de administrador elevada. El siguiente ejemplo muestra la utilización de netsh.exe.

```console
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>
```

Para obtener más información acerca de Netsh. exe, vea el tema sobre[Cómo utilizar la herramienta netsh. exe y los modificadores de la línea de comandos](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).

## <a name="see-also"></a>Vea también

- [Cliente de prueba de WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
