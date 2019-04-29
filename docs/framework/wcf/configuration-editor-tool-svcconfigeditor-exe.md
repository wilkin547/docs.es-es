---
title: Herramienta del editor de configuración (SvcConfigEditor.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files, creating
- configuration files
- Configuration file
- configuration file schema
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
ms.openlocfilehash: e4b54026c71e18e4011661c5cad2ca95dfcb733e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608858"
---
# <a name="configuration-editor-tool-svcconfigeditorexe"></a>Herramienta del editor de configuración (SvcConfigEditor.exe)
El editor de configuración de servicios de Windows Communication Foundation (SvcConfigEditor.exe) permite a los administradores y programadores crear y modificar la configuración para los servicios WCF mediante una interfaz gráfica de usuario. Con esta herramienta puede administrar los valores para los enlaces, comportamientos, servicios y diagnósticos de WCF sin tener que editar directamente los archivos de configuración XML.  
  
 El Editor de configuración de servicio se puede encontrar en la carpeta C:\Archivos de programa\Microsoft SDKs\Windows\v6.0\Bin.  
  
## <a name="the-wcf-configuration-editor"></a>El editor de configuración de WCF  
 El editor de configuración de servicio viene con un asistente que lo guía a través de todos los pasos para configurar un servicio o cliente de WCF. Se le aconseja encarecidamente que utilice directamente el asistente en lugar del editor.  
  
 Si ya tiene algunos archivos de configuración que obedecen al esquema estándar de System.Configuration, puede administrar valores concretos para enlaces, comportamiento, servicios y diagnósticos mediante la interfaz de usuario. El editor de configuración de servicio le permite administrar los valores para los archivos de configuración de WCF existentes, así como archivos ejecutables, servicios de COM+ y servicios hospedados en web. Cuando se abre un servicio hospedado en web con el Editor de configuración de servicios, se muestran las secciones de configuraciones heredadas de los nodos de nivel superior y la propia configuración del servicio.  
  
 Dado que la configuración de WCF se encuentra en la sección `<system.serviceModel>` del archivo de configuración, el editor actúa exclusivamente sobre el contenido de este elemento y no accede a otros elementos del mismo archivo. Puede navegar directamente a archivos de configuración existentes o puede seleccionar un ensamblado que contenga un servicio, un directorio virtual o un servicio de COM+. El editor carga el archivo de configuración para ese servicio particular y permite que el usuario agregue elementos nuevos o modifique elementos existentes anidados en la sección `<system.serviceModel>` del archivo de configuración.  
  
 El editor admite IntelliSense y exige la compatibilidad del esquema. Se garantiza que el resultado obtenido es compatible con el esquema del archivo de configuración y tiene valores de datos sintácticamente correctos. Sin embargo, el editor no garantiza que el archivo de configuración sea semánticamente válido. En otras palabras, el editor no garantiza que el archivo de configuración pueda funcionar con el servicio que configura.  
  
> [!CAUTION]
>  El editor no puede purgar un elemento de configuración a partir del archivo de configuración cuando ha modificado el elemento. Por ejemplo, si utiliza el editor para establecer el nombre de punto de conexión en una cadena que no esté vacía y guardarlo, el archivo de configuración tendrá el contenido del ejemplo siguiente.  
>   
>  `<endpoint binding="basicHttpBinding" name="somename" />`  
>   
>  Si intenta quitar el nombre estableciéndolo en una cadena vacía y guardar el archivo, el archivo de configuración todavía contendrá el atributo `name`, como se muestra en el ejemplo siguiente.  
>   
>  `<endpoint binding="basicHttpBinding" name="" />`  
>   
>  Para purgar el atributo, debe modificar manualmente el elemento mediante otro editor de texto.  
>   
>  Debería tener mucho cuidado con este problema al utilizar el elemento `issueToken` del comportamiento de extremo `clientCredential`. Específicamente, el atributo `address` de su subelemento `localIssuer` no debe ser una cadena vacía. Si ha modificado el atributo `address` mediante el editor de configuración y desea quitarlo completamente, debería hacerlo utilizando una herramienta diferente del editor. De lo contrario, el atributo contiene una cadena vacía y su aplicación inicia una excepción.  
  
## <a name="using-the-configuration-editor"></a>Utilización del editor de configuración  
 El Editor de configuración de servicio se puede encontrar en la siguiente ubicación de instalación de Windows SDK:  
  
 C:\Archivos de Programa\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe  
  
 Después de iniciar el Editor de configuración de servicio, puede usar el **archivo/abrir** menú para buscar el servicio o el ensamblado que desea administrar. Puede abrir directamente los archivos de configuración, busque WCF/servicios COM + y abra los archivos de configuración para servicios hospedados en web.  
  
 La interfaz de usuario del editor de configuración de servicio está dividida en las áreas siguientes:  
  
- Panel Ver árbol, que muestra los elementos de configuración en una estructura de árbol a la izquierda. Puede realizar operaciones en el árbol haciendo clic con el botón secundario en los nodos.  
  
- Panel de tareas, que muestra las tareas comunes para los elementos vigentes en la parte inferior izquierda de la ventana.  
  
- Panel de detalles, que muestra valores detallados del nodo de configuración seleccionado en Ver árbol a la derecha.  
  
### <a name="opening-a-configuration-file"></a>Abrir un archivo de configuración  
  
1. Inicie el Editor de configuración de servicio mediante el uso de una ventana de comandos para navegar a la ubicación de instalación de WCF y, a continuación, escriba `SvcConfigEditor.exe`.  
  
2. Desde el **archivo** menú, seleccione **abierto** y haga clic en el tipo de archivo que desea administrar.  
  
3. En el **abierto** cuadro de diálogo, navegue hasta el archivo específico que desea administrar y haga doble clic en él.  
  
 El visor sigue automáticamente la ruta de acceso de fusión mediante combinación de configuración y crea una vista de la configuración combinada. Por ejemplo, la configuración real de un servicio no hospedado es una combinación de Machine.config y App.config. Cualquier cambio se aplica al archivo activo en SvcConfigEditor. Si desea modificar un archivo concreto en la ruta de acceso de fusión mediante combinación de configuración, debería abrirlo directamente.  
  
> [!NOTE]
>  El editor de configuración recarga el archivo de configuración abierto actualmente cuando éste se ha modificado fuera del editor. Cuando esto pasa, se pierden todos los cambios que no están guardados dentro del Editor de forma duradera. Si la recarga sucede constantemente, la causa más probable es un servicio que tiene acceso al archivo de configuración continuamente, por ejemplo un software antivirus que se ejecuta en segundo plano. Para resolver esto, asegúrese de que el editor de configuración es el único proceso que puede tener acceso al archivo cuando se abre.  
  
### <a name="services"></a>Servicios  
 El **servicios** nodo muestra todos los servicios asignados actualmente en el archivo de configuración. Cada subnodo en el árbol corresponde a un subelemento de la <`services`> elemento en el archivo de configuración.  
  
 Al hacer clic en el **servicios** nodo, puede ver o realizar tareas en el servicio de la página de resumen en la **detalle** panel.  
  
#### <a name="creating-a-new-service-configuration"></a>Crear una nueva configuración de servicio  
 Puede crear una nueva configuración de servicio de las maneras siguientes:  
  
- Mediante un asistente: Haga clic en el vínculo **crear un nuevo servicio...** en el panel de tareas o la página de resumen para iniciar al asistente. También puede hacer en el **archivo** -> menú **Agregar nuevo elemento**.  
  
- Crear manualmente: Puede hacer clic en el **servicios** nodo y elija **nuevo servicio**.  
  
#### <a name="creating-a-new-service-endpoint-configuration"></a>Crear una nueva configuración de extremo de servicio  
 Puede crear una nueva configuración de punto de conexión de servicio de las maneras siguientes:  
  
- Crear mediante un asistente: haga clic en el vínculo **crear un nuevo extremo de servicio...** en el panel de tareas o la página de resumen para iniciar al asistente. También puede hacer en el **archivo** -> menú **Agregar nuevo elemento**.  
  
- Crear manualmente: Una vez creado un servicio, haga clic en el **extremos** nodo y elija "**nuevo extremo de servicio**".  
  
#### <a name="editing-a-service-configuration"></a>Editar una configuración de servicio  
  
1. Haga clic en un **servicio** nodo.  
  
2. Edite la configuración en la cuadrícula de propiedades.  
  
#### <a name="editing-a-service-endpoint-configuration"></a>Editar una configuración de punto de conexión de servicio  
  
1. Haga clic en un **punto de conexión de servicio** nodo.  
  
2. Edite la configuración en la cuadrícula de propiedades.  
  
#### <a name="adding-a-base-address"></a>Agregar una dirección base  
  
1. Haga clic en el **Host** nodo.  
  
2. Haga clic en el **nuevo...** botón en el **direcciones Base** sección.  
  
3. Escriba el URI de la dirección base en el cuadro de diálogo.  
  
4. Haga clic en **Aceptar**.  
  
> [!NOTE]
>  No se puede editar el valor de [ \<baseAddressPrefixFilters >](../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) dentro de esta herramienta. Para agregar o modificar este elemento, debe utilizar un editor de texto o Visual Studio.  
  
### <a name="client"></a>Cliente  
 El **cliente** nodo muestra todos los extremos de cliente en el archivo de configuración. Cada subnodo en el árbol corresponde a un subelemento de la <`client`> elemento en el archivo de configuración.  
  
 Al hacer clic en el **cliente** nodo, puede ver o realizar tareas en el cliente **página resumen** en el **panel detalle**.  
  
#### <a name="creating-a-new-client-endpoint-configuration"></a>Crear una nueva configuración de punto de conexión de cliente  
 Puede crear una nueva configuración de extremo de cliente de las maneras siguientes:  
  
- Asistente para crear: Haga clic en el vínculo **crear un nuevo cliente...** en el **panel de tareas** a la izquierda inferior de la ventana, o **página resumen** para iniciar el asistente. También puede hacer en el **archivo** -> menú **Agregar nuevo elemento**. El asistente le pedirá que indique la ubicación de la configuración de servicio, a partir de la cual se genera la configuración del cliente. A continuación podrá elegir el punto de conexión de servicio con el que conectarse.  
  
- Crear manualmente: Haga clic en el **extremos** nodo bajo **cliente**y elija **nuevo punto de conexión de cliente**.  
  
#### <a name="editing-a-client-endpoint-configuration"></a>Editar una configuración de punto de conexión de cliente  
  
1. Haga clic en un **punto de conexión de cliente** nodo.  
  
2. Edite la configuración en la cuadrícula de propiedades.  
  
### <a name="standard-endpoint"></a>punto de conexión estándar  
 Los puntos de conexión estándar son puntos de conexión especializados que tienen uno o más aspectos de la dirección, contrato y enlace definidos en los valores predeterminados.  
  
 Esas configuraciones se almacenan en el **punto de conexión estándar** nodo. El **punto de conexión estándar** nodo muestra todos los valores de punto de conexión estándar en el archivo de configuración. Cada subnodo en el árbol corresponde a un subelemento en el `<standardEndpoints>` elemento en el archivo de configuración.  
  
 Al hacer clic en el **punto de conexión estándar** nodo, puede ver o realizar tareas en el punto de conexión estándar **página resumen** en el **panel detalle**.  
  
#### <a name="creating-a-new-standard-endpoint-configuration"></a>Crear una nueva configuración de punto de conexión estándar  
 Puede crear una nueva configuración de punto de conexión estándar de las maneras siguientes:  
  
- Haga clic en el **punto de conexión estándar** nodo y seleccione **nueva configuración de extremo estándar...** Seleccione el tipo de enlace en el cuadro de diálogo y haga clic en **Aceptar**.  
  
- Seleccione el **punto de conexión estándar** nodo y haga clic en **nueva configuración de extremo estándar...** en el **panel de tareas** en la parte izquierda inferior de la ventana.  
  
 El **crear un nuevo extremo estándar** cuadro de diálogo muestra y enumera todos los tipos de punto de conexión estándar.  
  
#### <a name="viewing-and-editing-a-standard-endpoint-configuration"></a>Ver y editar una configuración de punto de conexión estándar  
 Puede abrir una configuración de extremo estándar para verla y editarla de las siguientes maneras:  
  
- Haga clic para expandir el **punto de conexión estándar** nodo y haga clic en el subnodo del extremo respectivo.  
  
- Haga clic en el **punto de conexión estándar** nodo y haga clic en el punto de conexión respectivo en el panel de detalles.  
  
 Los atributos para el punto de conexión se muestran en el panel derecho para edición.  
  
#### <a name="deleting-a-standard-endpoint-configuration"></a>Eliminar una configuración de punto de conexión estándar  
 Puede eliminar una configuración de punto de conexión estándar de las maneras siguientes:  
  
- Haga clic para expandir el **punto de conexión estándar** con el botón secundario en el subnodo del extremo respectivo y nodo. Use el comando contextual **eliminar la configuración de punto de conexión estándar** para eliminar el punto de conexión.  
  
- Haga clic en el **punto de conexión estándar** nodo. En el **tarea** panel, haga clic en **eliminar la configuración de punto de conexión estándar**.  
  
 Si el punto de conexión estándar se está usando, se muestra un mensaje de advertencia al intentar eliminarlo: **El punto de conexión estándar está en uso. Si lo elimina ahora, asegúrese de eliminar todas sus referencias en otras partes de la configuración (por ejemplo, en el punto de conexión de servicio o punto de conexión del cliente). De lo contrario, la configuración no será válida y no se puede abrir la próxima vez. ¿Está seguro de que desea eliminar el punto de conexión estándar? "**  
  
### <a name="binding"></a>Enlaces  
 Las configuraciones de enlace se usan para configurar enlaces en extremos. Esas configuraciones se almacenan en el **enlace** nodo. Los puntos de conexión hacen referencia a las configuraciones de enlace por nombre y varios puntos de conexión pueden hacer referencia a una configuración de enlace única.  
  
 El **enlaces** nodo muestra todas las configuraciones de enlace en el archivo de configuración. Cada subnodo en el árbol corresponde a un subelemento en el <`bindings`> elemento en el archivo de configuración.  
  
 Al hacer clic en el **enlaces** nodo, puede ver o realizar tareas en el enlace **página resumen** en el **panel detalle**.  
  
#### <a name="creating-a-new-binding-configuration"></a>Crear una nueva configuración de enlace  
 Puede crear una nueva configuración de enlace de las maneras siguientes.  
  
- Haga clic en el **enlaces** nodo y seleccione **nueva configuración de enlace**... Seleccione el tipo de enlace en el cuadro de diálogo y haga clic en **Aceptar**.  
  
- Seleccione el **enlaces** nodo y haga clic en **nueva configuración de enlace**... en el **panel de tareas** en la parte izquierda inferior de la ventana.  
  
- En la página Resumen de servicio o cliente, haga clic en **haga clic en crear** en el **configuración de enlace** campo para crear una configuración de enlace para el extremo correspondiente.  
  
#### <a name="adding-binding-element-extensions-to-a-custom-binding"></a>Agregar extensiones de elemento de enlace a un enlace personalizado  
  
1. Seleccione el enlace al que desea agregar un elemento de extensión.  
  
2. Haga clic en **Agregar**.  
  
3. De la lista de extensiones disponibles, seleccione la extensión de elemento de enlace que desea agregar. Para seleccionar varios elementos, presione simultáneamente la tecla CTRL.  
  
4. Haga clic en **Agregar**.  
  
#### <a name="adjusting-the-extension-position-in-a-custom-binding"></a>Ajustar la posición de la extensión en un enlace personalizado  
 Un enlace personalizado es una colección de elementos de enlace que forman una pila. Cada elemento de enlace en la pila tiene su propia configuración. El orden de las extensiones de elemento de enlace en un enlace personalizado indica sus posiciones en la pila. Se aplican primero los elementos de la parte superior de la pila. Para cambiar el orden:  
  
1. Seleccione el nodo de enlace personalizado.  
  
2. Seleccione un elemento de extensión de enlace en el **posición de extensión de elemento de enlace** sección.  
  
3. Use la **seguridad** o **abajo** botón en el lado izquierdo de la lista para cambiar la posición del elemento seleccionado.  
  
#### <a name="editing-the-configuration-of-binding-element-extensions-in-a-custom-binding"></a>Editar la configuración de extensiones de elemento de enlace en un enlace personalizado  
  
1. Seleccione el nodo de enlace en el árbol.  
  
2. Seleccione el enlace personalizado que contiene el elemento que desea editar.  
  
3. Seleccione la extensión de elemento de enlace que desea editar. La configuración del elemento aparece en el panel derecho, donde se puede editar.  
  
### <a name="diagnostics"></a>Diagnóstico  
 El **diagnósticos** nodo muestra toda la configuración de diagnóstico en el archivo de configuración. Permite activar y desactivar los contadores de rendimiento, habilitar o deshabilitar Windows Management Instrumentation (WMI), configurar el seguimiento de WCF y configurar el registro de mensajes WCF. La configuración de la **diagnósticos** nodo corresponde a la <`system.diagnostics`> sección, y `<diagnostics>` sección `<system.serviceModel>` en el archivo de configuración.  
  
 Al hacer clic en el **diagnósticos** nodo, puede ver o realizar tareas en los diagnósticos **página resumen** en el **panel detalle**.  
  
#### <a name="configuring-performance-counters-and-wmi"></a>Configurar contadores de rendimiento y WMI  
  
1. Haga clic en el **diagnósticos** nodo.  
  
2. Haga clic en **alternar contadores de rendimiento**. El contador de rendimiento tiene tres estados: OFF (valor predeterminado), ServiceOnly y todos. Al hacer clic en el vínculo, se alterna el valor entre estos tres estados.  
  
#### <a name="configuring-wmi-provider"></a>Configurar proveedor de WMI  
  
1. Haga clic en el **diagnósticos** nodo.  
  
2. Para habilitar el proveedor WMI, haga clic en el **habilitar proveedor de WMI** vínculo.  
  
#### <a name="enabling-wcf-tracing"></a>Habilitar la traza WCF  
 Puede crear un archivo de seguimiento de WCF con propiedades estándar o configurar un archivo de seguimiento personalizado.  
  
1. Haga clic en el **diagnósticos** nodo.  
  
2. Haga clic en **habilitar el seguimiento**.  
  
3. Haga clic en el **nivel de seguimiento** vínculo para ajustar el nivel de seguimiento. Hay seis niveles de seguimiento: Desactivado, crítico, Error, advertencia, información y detallado. El **seguimiento de la actividad** y **propagar actividad** opción le permiten usar la característica de seguimiento de actividad WCF.  
  
4. Haga clic en el nombre del agente de escucha de traza para especificar el archivo y las opciones de seguimiento.  
  
#### <a name="enabling-wcf-logging"></a>Habilitar el registro del WCF  
 Puede crear un archivo de seguimiento de WCF con propiedades estándar o configurar un archivo de seguimiento personalizado.  
  
1. Haga clic en el **diagnósticos** nodo.  
  
2. Haga clic en **Habilitar registro de mensajes**.  
  
3. Haga clic en el **nivel de registro** vínculo para ajustar el nivel de registro. Hay tres niveles de registro: Tiene un formato incorrecto, servicio y transporte.  
  
4. Haga clic en el nombre de agente de escucha para especificar el archivo y las opciones de registro.  
  
> [!NOTE]
>  Si desea que los registros de seguimiento y mensajes para vaciar automáticamente cuando se cierra la aplicación, habilite la **vaciado automático** opción.  
  
 El **diagnósticos** **página resumen** le permite realizar las tareas más comunes de configuración de diagnósticos. Sin embargo, si desea editar manualmente la configuración de orígenes y los agentes de escucha, deberá expandir la **diagnósticos** nodo y editar la configuración en **registro de mensajes**, **los agentes de escucha** y **Orígenes** nodo.  
  
#### <a name="enabling-wcf-custom-tracing-or-message-logging"></a>Habilitar traza personalizada o registro de mensajes de WCF  
  
1. Haga clic en el **diagnósticos** nodo y expándalo.  
  
2. Haga clic en el **los agentes de escucha** nodo y seleccione **nuevo agente de escucha**.  
  
3. Escriba el nombre de archivo de seguimiento en el **InitData** campo. Puede hacer clic en el "botón..." botón para ir a una ruta de acceso.  
  
4. Al hacer clic en el **TypeName** línea muestra un "..." botón. Haga clic en este botón para abrir el **Explorador de tipos de agente de escucha de seguimiento**, que puede usar para buscar los agentes de escucha de seguimiento preconfiguradas que ya están instalados.  
  
5. Tenga en cuenta la **origen** sección. Haga clic en **agregar** en esta sección para abrir un cuadro de diálogo con un menú desplegable, que enumera los orígenes de traza disponibles. Seleccione un origen de traza y haga clic en **Aceptar**.  
  
6. Para editar la configuración de registro de mensajes, haga clic en el **registro de mensajes** nodo. Puede editar los valores en la cuadrícula de propiedad.  
  
### <a name="advanced"></a>Avanzadas  
  
#### <a name="behaviors"></a>comportamientos  
 El **comportamientos** nodo muestra los comportamientos que están definidos actualmente en el archivo de configuración.  
  
 Las configuraciones de comportamiento se utilizan para configurar comportamientos de puntos de conexión y servicios. Esas configuraciones se almacenan en el **avanzadas** nodo bajo **los comportamientos de servicio** y **comportamientos de extremo**. Los servicios utilizan comportamientos de servicios; pero los puntos de conexión utilizan comportamientos de punto de conexión.  
  
 Los comportamientos son una colección de elementos de extensión que forman una pila. Se aplica primero el elemento en la parte superior de la pila. Cada elemento de extensión puede tener su propia configuración.  
  
##### <a name="creating-a-new-behavior-configuration"></a>Crear una nueva configuración de comportamiento  
 Puede crear una nueva configuración de comportamiento de dos maneras:  
  
- Haga clic en uno de los nodos de comportamiento y seleccione "**... la nueva configuración de comportamiento**  
  
- Seleccione uno de los nodos de comportamiento y haga clic en el **nueva configuración de comportamiento**... en el **panel de tareas** en la parte izquierda inferior de la ventana.  
  
##### <a name="adding-behavior-element-extensions-to-a-behavior"></a>Agregar las extensiones de elemento de comportamiento a un comportamiento  
  
1. Seleccione uno de los nodos de comportamiento.  
  
2. Seleccione el comportamiento que desee editar.  
  
3. Haga clic en **Agregar**.  
  
4. De la lista de extensiones disponibles, seleccione la extensión de elemento de comportamiento que desea agregar.  
  
5. Haga clic en **Agregar**.  
  
##### <a name="adjusting-the-extension-position-in-a-behavior"></a>Ajustar la posición de la extensión en un comportamiento  
 Los comportamientos son colecciones de elementos que forman una pila. Cada elemento de la pila tiene su propia configuración. El orden de las extensiones de elemento de comportamiento en un comportamiento indica sus posiciones en la pila. Se aplican primero los elementos de la parte superior de la pila. Para cambiar el orden:  
  
1. Seleccione uno de los nodos de comportamiento.  
  
2. Seleccione el comportamiento que desee editar.  
  
3. Seleccione un elemento de extensión de comportamiento en el **posición de extensión de elemento de comportamiento** sección.  
  
4. Use la **seguridad** o **abajo** botón en el lado izquierdo de la lista para cambiar la posición del elemento seleccionado.  
  
##### <a name="editing-the-configuration-of-behavior-element-extensions"></a>Editar la configuración de extensiones de elemento de comportamiento  
  
1. Seleccione uno de los nodos de comportamiento del árbol.  
  
2. Seleccione el comportamiento que contiene el elemento que desea editar.  
  
3. Seleccione la extensión de elemento de comportamiento que desea editar. La configuración del elemento aparece en el panel derecho, donde se puede editar.  
  
#### <a name="protocolmapping"></a>ProtocolMapping  
 Esta sección permite establecer los tipos de enlaces predeterminados para los distintos protocolos como http, tcp, MSMQ o net.pipe mediante la asignación entre los esquemas de direcciones de protocolo y los posibles enlaces. También puede agregar nuevas asignaciones a otros protocolos.  
  
#### <a name="extensions"></a>Extensiones  
 Nuevas extensiones de enlace, extensiones de elemento de enlace, extensiones de punto de conexión estándar y extensiones de comportamiento se pueden registrar para su uso en la configuración de WCF. Las extensiones son pares de nombre/tipo. El nombre define el nombre de la extensión en la configuración, mientras que el tipo implementa la extensión. Hay cuatro tipos de extensiones:  
  
- Las extensiones de enlace definen un tipo entero de enlace. Ejemplo: `basicHttpBinding`.  
  
- Las extensiones de elemento de enlace definen un elemento de un enlace. Ejemplo: `textMessageEncoding`.  
  
- Las extensiones de extremo estándar definen un extremo estándar completo. Ejemplo: `discoveryEndpoint`.  
  
- Las extensiones de elemento de comportamiento definen un elemento de un comportamiento. Ejemplo: `clientVia`.  
  
 Las extensiones registradas en configuración se pueden utilizar como cualquier otro componente WCF del mismo tipo.  
  
##### <a name="adding-a-new-extension"></a>Agregar una nueva extensión  
 Seleccione uno de los nodos de extensión en los nodos avanzados:  
  
1. Haga clic en **nuevo**.  
  
2. Escriba un nombre y tipo.  
  
3. Haga clic en **Aceptar**.  
  
4. La extensión aparece ahora en el lugar adecuado en el editor. Por ejemplo, si agrega una extensión de elemento de comportamiento, aparece en la lista de extensiones disponibles.  
  
#### <a name="hosting-environment"></a>Entorno de hospedaje  
 Esta sección permite definir la configuración de creación de instancias para el entorno de hospedaje de servicio.  
  
### <a name="creating-a-configuration-file-using-the-wizard"></a>Crear un archivo de configuración mediante el asistente  
 Una forma de crear un archivo de configuración nuevo es utilizar el Asistente para nuevo elemento de servicio. El asistente busca los tipos de servicio instalados y otros elementos compatibles con WCF en el equipo, incluidos COM + y directorios virtuales hospedados en Web y los carga para que la creación de la configuración mucho más simple.  
  
#### <a name="creating-a-configuration-file"></a>Crear un archivo de configuración  
  
1. Inicie el Editor de configuración de servicio mediante el uso de una ventana de comandos para navegar a la ubicación de instalación de WCF y, a continuación, escriba `SvcConfigEditor.exe`.  
  
2. Desde el **archivo** menú, seleccione **abierto** y haga clic en **ejecutable**, **COM + Service**, o **WebHosted Service**, según el tipo de archivo de configuración que desea crear.  
  
3. En el **abierto** cuadro de diálogo, navegue hasta el archivo específico que desea crear un archivo de configuración y haga doble clic en él.  
  
4. En el **archivo** menú, elija **Agregar nuevo elemento** y haga clic en **servicio**. Se abre el Asistente para nuevo elemento de servicio.  
  
5. Siga los pasos en el asistente para crear el nuevo servicio.  
  
> [!NOTE]
>  Si desea utilizar NetPeerTcpBinding del archivo de configuración generado por el asistente, tiene que agregar manualmente un elemento de configuración de enlace y modificar el atributo `mode` de su elemento `security` a "Ninguno".  
  
## <a name="configuring-com"></a>Configurar COM+  
 El editor de configuración de servicio le permite crear un nuevo archivo de configuración para una aplicación COM+ existente o editar una configuración COM+ existente. El **contrato COM** nodo solo está visible cuando el <`comContract`> sección existe en el archivo de configuración.  
  
### <a name="creating-a-new-com-configuration"></a>Crear una nueva configuración de COM+  
 Antes de crear una nueva configuración de COM+, asegúrese de que su aplicación COM+ esté instalada en servicios de componente y registrada en la caché global de ensamblados (GAC).  
  
1. Seleccione **archivo** -> menú **integrar** -> **aplicación COM +.** Esta operación cierra el archivo abierto actual. Si hay datos no guardados en el archivo actual, aparece el cuadro de diálogo Guardar. El **Asistente para la integración de COM +** , a continuación, se inicia.  
  
2. En la primera página, seleccione la aplicación COM+ del árbol. Si no encuentra su aplicación COM+ en el árbol, compruebe que está instalada en los servicios de componente y registrada en la caché global de ensamblados (GAC).  
  
3. En la página siguiente, seleccione qué método(s) quiere exponer como servicios WCF. Todos los métodos compatibles en la aplicación COM+ se muestran y se seleccionan de forma predeterminada.  
  
4. Elija un método de hospedaje.  
  
5. Configure otros valores según las guías en el Asistente.  
  
6. El editor de configuración de servicio utiliza en segundo plano ComSvcConfig.exe para generar un archivo de configuración. Después de este paso, puede ver un resumen y salir del Asistente. Se abre el archivo de configuración generado para que pueda editarlo directamente.  
  
### <a name="editing-an-existing-com-configuration"></a>Editar una configuración COM+ existente  
  
1. Seleccione **archivo** -> menú **abierto** -> **COM + Service**...  
  
2. Seleccione el servicio COM+ que desee editar en la lista.  
  
3. Editar opciones de configuración en el **contratos COM** nodo.  
  
    > [!NOTE]
    >  También puede abrir directamente un archivo de configuración que contenga contratos COM+ y modificarlo.  
  
## <a name="security"></a>Seguridad  
 No se garantiza que un archivo de configuración de servicio generado por el editor de configuración sea seguro. Consulte la [seguridad](../../../docs/framework/wcf/feature-details/security.md) documentación para averiguar cómo proteger los servicios WCF.  
  
 Además, el editor de configuración solo se puede utilizar para leer y escribir elementos de configuración de WCF válidos. La herramienta omite los elementos conformes a esquema definidos por el usuario. Tampoco intenta quitar estos elementos del archivo de configuración o determinar sus efectos sobre los elementos de WCF conocidos. Es la responsabilidad del usuario determinar si estos elementos suponen una amenaza para la aplicación o el sistema.
