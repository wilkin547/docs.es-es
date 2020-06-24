---
title: Herramienta del editor de configuración (SvcConfigEditor.exe)
description: Obtenga información sobre cómo administrar la configuración de enlaces, comportamientos, servicios y diagnósticos de WCF mediante el editor de configuración de servicio de WCF.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files, creating
- configuration files
- Configuration file
- configuration file schema
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
ms.openlocfilehash: 258437ff616b969d40feabbfff364ad2cc6b25bc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247654"
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
> El editor no puede purgar un elemento de configuración a partir del archivo de configuración cuando ha modificado el elemento. Por ejemplo, si utiliza el editor para establecer el nombre de punto de conexión en una cadena que no esté vacía y guardarlo, el archivo de configuración tendrá el contenido del ejemplo siguiente.
>
> `<endpoint binding="basicHttpBinding" name="somename" />`
>
> Si intenta quitar el nombre estableciéndolo en una cadena vacía y guardar el archivo, el archivo de configuración todavía contendrá el atributo `name`, como se muestra en el ejemplo siguiente.
>
> `<endpoint binding="basicHttpBinding" name="" />`
>
> Para purgar el atributo, debe modificar manualmente el elemento mediante otro editor de texto.
>
> Debería tener mucho cuidado con este problema al utilizar el elemento `issueToken` del comportamiento de extremo `clientCredential`. Específicamente, el atributo `address` de su subelemento `localIssuer` no debe ser una cadena vacía. Si ha modificado el atributo `address` mediante el editor de configuración y desea quitarlo completamente, debería hacerlo utilizando una herramienta diferente del editor. De lo contrario, el atributo contiene una cadena vacía y su aplicación inicia una excepción.

## <a name="using-the-configuration-editor"></a>Utilización del editor de configuración

El Editor de configuración de servicio se puede encontrar en la siguiente ubicación de instalación de Windows SDK:

C:\Archivos de Programa\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe

Después de iniciar el editor de configuración de servicio, puede usar el menú **archivo/abrir** para buscar el servicio o ensamblado que desea administrar. Puede abrir directamente los archivos de configuración, busque WCF/servicios COM + y abra los archivos de configuración para servicios hospedados en web.

La interfaz de usuario del editor de configuración de servicio está dividida en las áreas siguientes:

- Panel Ver árbol, que muestra los elementos de configuración en una estructura de árbol a la izquierda. Puede realizar operaciones en el árbol haciendo clic con el botón secundario en los nodos.

- Panel de tareas, que muestra las tareas comunes para los elementos vigentes en la parte inferior izquierda de la ventana.

- Panel de detalles, que muestra valores detallados del nodo de configuración seleccionado en Ver árbol a la derecha.

### <a name="opening-a-configuration-file"></a>Abrir un archivo de configuración

1. Inicie el editor de configuración de servicio mediante una ventana de comandos para navegar a la ubicación de instalación de WCF y, a continuación, escriba `SvcConfigEditor.exe` .

2. En el menú **archivo** , seleccione **abrir** y haga clic en el tipo de archivo que desea administrar.

3. En el cuadro de diálogo **abrir** , navegue hasta el archivo específico que desea administrar y haga doble clic en él.

El visor sigue automáticamente la ruta de acceso de fusión mediante combinación de configuración y crea una vista de la configuración combinada. Por ejemplo, la configuración real de un servicio no hospedado es una combinación de Machine.config y App.config. Cualquier cambio se aplica al archivo activo en SvcConfigEditor. Si desea modificar un archivo concreto en la ruta de acceso de fusión mediante combinación de configuración, debería abrirlo directamente.

> [!NOTE]
> El editor de configuración recarga el archivo de configuración abierto actualmente cuando éste se ha modificado fuera del editor. Cuando esto pasa, se pierden todos los cambios que no están guardados dentro del Editor de forma duradera. Si la recarga sucede constantemente, la causa más probable es un servicio que tiene acceso al archivo de configuración continuamente, por ejemplo un software antivirus que se ejecuta en segundo plano. Para resolver esto, asegúrese de que el editor de configuración es el único proceso que puede tener acceso al archivo cuando se abre.

### <a name="services"></a>Servicios

El nodo **servicios** muestra todos los servicios asignados actualmente en el archivo de configuración. Cada subnodo del árbol corresponde a un subelemento del `services` elemento <> del archivo de configuración.

Al hacer clic en el nodo **servicios** , puede ver o realizar tareas en la página Resumen del servicio en el panel de **detalles** .

#### <a name="creating-a-new-service-configuration"></a>Crear una nueva configuración de servicio

Puede crear una nueva configuración de servicio de las maneras siguientes:

- Mediante un asistente: haga clic en el vínculo **crear un nuevo servicio...** en el panel de tareas o en la página de resumen para iniciar el asistente. También puede hacerlo en el menú **archivo** -> **Agregar nuevo elemento**.

- Crear manualmente: puede hacer clic con el botón secundario en el nodo **servicios** y elegir **nuevo servicio**.

#### <a name="creating-a-new-service-endpoint-configuration"></a>Crear una nueva configuración de extremo de servicio

Puede crear una nueva configuración de punto de conexión de servicio de las maneras siguientes:

- Crear mediante un asistente: haga clic en el vínculo **crear un nuevo punto de conexión de servicio..** . en el panel de tareas o en la página de resumen para iniciar el asistente. También puede hacerlo en el menú **archivo** -> **Agregar nuevo elemento**.

- Crear manualmente: una vez creado un servicio, puede hacer clic con el botón secundario en el nodo **extremos** y elegir "**nuevo punto de conexión de servicio**".

#### <a name="editing-a-service-configuration"></a>Editar una configuración de servicio

1. Haga clic en un nodo de **servicio** .

2. Edite la configuración en la cuadrícula de propiedades.

#### <a name="editing-a-service-endpoint-configuration"></a>Editar una configuración de punto de conexión de servicio

1. Haga clic en un nodo de **punto de conexión de servicio** .

2. Edite la configuración en la cuadrícula de propiedades.

#### <a name="adding-a-base-address"></a>Agregar una dirección base

1. Haga clic en el nodo **host** .

2. Haga clic en el botón **Nuevo...** en la sección **direcciones base** .

3. Escriba el URI de la dirección base en el cuadro de diálogo.

4. Haga clic en **OK**.

> [!NOTE]
> No se puede editar el valor de [\<baseAddressPrefixFilters>](../configure-apps/file-schema/wcf/baseaddressprefixfilters.md) dentro de esta herramienta. Para agregar o modificar este elemento, debe utilizar un editor de texto o Visual Studio.

### <a name="client"></a>Cliente

El nodo **cliente** muestra todos los puntos de conexión de cliente en el archivo de configuración. Cada subnodo del árbol corresponde a un subelemento del `client` elemento <> del archivo de configuración.

Al hacer clic en el nodo **cliente** , puede ver o realizar tareas en la **Página de Resumen** del cliente en el **Panel de detalles**.

#### <a name="creating-a-new-client-endpoint-configuration"></a>Crear una nueva configuración de punto de conexión de cliente

Puede crear una nueva configuración de extremo de cliente de las maneras siguientes:

- Crear por asistente: haga clic en el vínculo **crear un nuevo cliente...** en el **Panel de tareas** de la parte inferior izquierda de la ventana o en la **Página de Resumen** para iniciar el asistente. También puede hacerlo en el menú **archivo** -> **Agregar nuevo elemento**. El asistente le pedirá que indique la ubicación de la configuración de servicio, a partir de la cual se genera la configuración del cliente. A continuación podrá elegir el punto de conexión de servicio con el que conectarse.

- Crear manualmente: haga clic con el botón secundario en el nodo **extremos** , en **cliente**, y elija **nuevo punto de conexión de cliente**.

#### <a name="editing-a-client-endpoint-configuration"></a>Editar una configuración de punto de conexión de cliente

1. Haga clic en un nodo de **punto de conexión de cliente** .

2. Edite la configuración en la cuadrícula de propiedades.

### <a name="standard-endpoint"></a>punto de conexión estándar

Los puntos de conexión estándar son puntos de conexión especializados que tienen uno o más aspectos de la dirección, contrato y enlace definidos en los valores predeterminados.

Estos valores de configuración se almacenan en el nodo de **punto de conexión estándar** . El nodo **punto de conexión estándar** muestra todos los valores de punto de conexión estándar en el archivo de configuración. Cada subnodo del árbol corresponde a un subelemento del `<standardEndpoints>` elemento en el archivo de configuración.

Al hacer clic en el nodo **extremo estándar** , puede ver o realizar tareas en la **página Resumen** de punto de conexión estándar en el **Panel de detalles**.

#### <a name="creating-a-new-standard-endpoint-configuration"></a>Crear una nueva configuración de punto de conexión estándar

Puede crear una nueva configuración de punto de conexión estándar de las maneras siguientes:

- Haga clic con el botón secundario en el nodo **punto de conexión estándar** y seleccione **nueva configuración de extremo estándar...** Seleccione el tipo de enlace en el cuadro de diálogo y haga clic en **Aceptar**.

- Seleccione el nodo **punto de conexión estándar** y haga clic en **nueva configuración de extremo estándar...** en el **Panel de tareas** de la parte inferior izquierda de la ventana.

En el cuadro de diálogo **crear un nuevo extremo estándar** se muestra y se enumeran todos los tipos de punto de conexión estándar registrados.

#### <a name="viewing-and-editing-a-standard-endpoint-configuration"></a>Ver y editar una configuración de punto de conexión estándar

Puede abrir una configuración de extremo estándar para verla y editarla de las siguientes maneras:

- Haga clic para expandir el nodo **punto de conexión estándar** y haga clic en el subnodo del extremo respectivo.

- Haga clic en el nodo **extremo estándar** y haga clic en el punto de conexión respectivo en el panel de detalles.

Los atributos para el punto de conexión se muestran en el panel derecho para edición.

#### <a name="deleting-a-standard-endpoint-configuration"></a>Eliminar una configuración de punto de conexión estándar

Puede eliminar una configuración de punto de conexión estándar de las maneras siguientes:

- Haga clic para expandir el nodo **punto de conexión estándar** y haga clic con el botón secundario en el subnodo del extremo respectivo. Use el comando de contexto **Eliminar configuración de extremo estándar** para eliminar el punto de conexión.

- Haga clic en el nodo **punto de conexión estándar** . En el panel de **tareas** , haga clic en **Eliminar configuración de extremo estándar**.

Si el extremo estándar está en uso, se muestra un mensaje de advertencia al intentar eliminarlo: **el extremo estándar está en uso. Si lo elimina ahora, asegúrese de eliminar todas sus referencias en otras partes de la configuración (por ejemplo, en el punto de conexión de servicio o punto de conexión de cliente). De lo contrario, la configuración no será válida y no se podrá abrir la próxima vez. ¿Está seguro de que desea eliminar el extremo estándar? "**

### <a name="binding"></a>Enlace

Las configuraciones de enlace se usan para configurar enlaces en extremos. Estos valores de configuración se almacenan en el nodo de **enlace** . Los puntos de conexión hacen referencia a las configuraciones de enlace por nombre y varios puntos de conexión pueden hacer referencia a una configuración de enlace única.

El nodo **enlaces** muestra todos los valores de enlace en el archivo de configuración. Cada subnodo del árbol corresponde a un subelemento del `bindings` elemento <> del archivo de configuración.

Al hacer clic en el nodo **enlaces** , puede ver o realizar tareas en la **página Resumen** de enlace en el **Panel de detalles**.

#### <a name="creating-a-new-binding-configuration"></a>Crear una nueva configuración de enlace

Puede crear una nueva configuración de enlace de las maneras siguientes.

- Haga clic con el botón secundario en el nodo **enlaces** y seleccione **nueva configuración de enlace**... Seleccione el tipo de enlace en el cuadro de diálogo y haga clic en **Aceptar**.

- Seleccione el nodo **enlaces** y haga clic en **nueva configuración de enlace**... en el **Panel de tareas** de la parte inferior izquierda de la ventana.

- En la página Resumen de servicio o cliente, haga clic **en haga clic para crear** en el campo **configuración de enlace** para crear una configuración de enlace para el punto de conexión correspondiente.

#### <a name="adding-binding-element-extensions-to-a-custom-binding"></a>Agregar extensiones de elemento de enlace a un enlace personalizado

1. Seleccione el enlace al que desea agregar un elemento de extensión.

2. Haga clic en **Agregar**.

3. De la lista de extensiones disponibles, seleccione la extensión de elemento de enlace que desea agregar. Para seleccionar varios elementos, presione simultáneamente la tecla CTRL.

4. Haga clic en **Agregar**.

#### <a name="adjusting-the-extension-position-in-a-custom-binding"></a>Ajustar la posición de la extensión en un enlace personalizado

Un enlace personalizado es una colección de elementos de enlace que forman una pila. Cada elemento de enlace en la pila tiene su propia configuración. El orden de las extensiones de elemento de enlace en un enlace personalizado indica sus posiciones en la pila. Se aplican primero los elementos de la parte superior de la pila. Para cambiar el orden:

1. Seleccione el nodo de enlace personalizado.

2. Seleccione un elemento de extensión de enlace en la sección **posición de extensión de elemento de enlace** .

3. Use el botón **arriba** o **abajo** situado en el lado izquierdo de la lista para cambiar la posición del elemento seleccionado.

#### <a name="editing-the-configuration-of-binding-element-extensions-in-a-custom-binding"></a>Editar la configuración de extensiones de elemento de enlace en un enlace personalizado

1. Seleccione el nodo de enlace en el árbol.

2. Seleccione el enlace personalizado que contiene el elemento que desea editar.

3. Seleccione la extensión de elemento de enlace que desea editar. La configuración del elemento aparece en el panel derecho, donde se puede editar.

### <a name="diagnostics"></a>Diagnóstico

El nodo **diagnósticos** muestra toda la configuración de diagnóstico en el archivo de configuración. Permite activar o desactivar los contadores de rendimiento, habilitar o deshabilitar Instrumental de administración de Windows (WMI), configurar el seguimiento de WCF y configurar el registro de mensajes de WCF. La configuración del nodo **diagnósticos** corresponde a la `system.diagnostics` sección <> y `<diagnostics>` en `<system.serviceModel>` el archivo de configuración.

Al hacer clic en el nodo **diagnósticos** , puede ver o realizar tareas en la **página Resumen** de diagnósticos en el **Panel de detalles**.

#### <a name="configuring-performance-counters-and-wmi"></a>Configurar contadores de rendimiento y WMI

1. Haga clic en el nodo **diagnósticos** .

2. Haga clic en **alternar contadores de rendimiento**. El contador de rendimiento tiene tres estados: Apagado (valor predeterminado), ServiceOnly y todos. Al hacer clic en el vínculo, se alterna el valor entre estos tres estados.

#### <a name="configuring-wmi-provider"></a>Configurar proveedor de WMI

1. Haga clic en el nodo **diagnósticos** .

2. Para habilitar el proveedor de WMI, haga clic en el vínculo **Habilitar proveedor WMI** .

#### <a name="enabling-wcf-tracing"></a>Habilitar la traza WCF

Puede crear un archivo de seguimiento de WCF con propiedades estándar o configurar un archivo de seguimiento personalizado.

1. Haga clic en el nodo **diagnósticos** .

2. Haga clic en **Habilitar seguimiento**.

3. Haga clic en el vínculo **nivel de seguimiento** para ajustar el nivel de seguimiento. Hay seis niveles de seguimiento: apagado, crítico, error, advertencia, información y detallado. La opción **seguimiento de actividad** y **propagar actividad** le permiten usar la característica de seguimiento de la actividad WCF.

4. Haga clic en el nombre del agente de escucha de traza para especificar el archivo y las opciones de seguimiento.

#### <a name="enabling-wcf-logging"></a>Habilitar el registro del WCF

Puede crear un archivo de seguimiento de WCF con propiedades estándar o configurar un archivo de seguimiento personalizado.

1. Haga clic en el nodo **diagnósticos** .

2. Haga clic en **Habilitar registro de mensajes**.

3. Haga clic en el vínculo **nivel de registro** para ajustar el nivel de registro. Hay tres niveles de registro: incorrecto, servicio y transporte.

4. Haga clic en el nombre de agente de escucha para especificar el archivo y las opciones de registro.

> [!NOTE]
> Si desea que los registros de seguimiento y de mensajes se vacíen automáticamente cuando se cierre la aplicación, habilite la opción **vaciado automático** .

La **Página de Resumen** de **diagnósticos** le permite realizar las tareas más comunes en la configuración de diagnósticos. Sin embargo, si desea modificar manualmente la configuración de los agentes de escucha y los orígenes, debe expandir el nodo **diagnósticos** y editar la configuración en el nodo **registro de mensajes**, **agentes de escucha** y **orígenes** .

#### <a name="enabling-wcf-custom-tracing-or-message-logging"></a>Habilitar traza personalizada o registro de mensajes de WCF

1. Haga clic en el nodo **diagnósticos** y expándalo.

2. Haga clic con el botón secundario en el nodo **agentes de escucha** y seleccione **nuevo agente de escucha**.

3. Escriba el nombre del archivo de seguimiento en el campo **InitData** . Puede hacer clic en el para ir a una ruta de acceso.

4. Al hacer clic en la línea **TypeName** , se muestra una "..." botón. Haga clic en este botón para abrir el **Explorador de tipos de agente de escucha de seguimiento**, que puede usar para buscar agentes de escucha de seguimiento preconfigurados que ya están instalados.

5. Observe la sección **origen** . Haga clic en **Agregar** en esta sección para abrir un cuadro de diálogo con un menú desplegable que muestra los orígenes de seguimiento disponibles. Seleccione un origen de traza y haga clic en **Aceptar**.

6. Para editar la configuración del registro de mensajes, haga clic en el nodo **registro de mensajes** . Puede editar los valores en la cuadrícula de propiedad.

### <a name="advanced"></a>Avanzado

#### <a name="behaviors"></a>comportamientos

El nodo **comportamientos** muestra los comportamientos que se definen actualmente en el archivo de configuración.

Las configuraciones de comportamiento se utilizan para configurar comportamientos de puntos de conexión y servicios. Estos valores de configuración se almacenan en el nodo **avanzado** bajo **comportamientos de servicio** y **comportamientos de extremo**. Los servicios utilizan comportamientos de servicios; pero los puntos de conexión utilizan comportamientos de punto de conexión.

Los comportamientos son una colección de elementos de extensión que forman una pila. Se aplica primero el elemento en la parte superior de la pila. Cada elemento de extensión puede tener su propia configuración.

##### <a name="creating-a-new-behavior-configuration"></a>Crear una nueva configuración de comportamiento

Puede crear una nueva configuración de comportamiento de dos maneras:

- Haga clic con el botón secundario en uno de los nodos de comportamiento y seleccione "**nueva configuración de comportamiento.** ..

- Seleccione uno de los nodos de comportamiento y haga clic en la **nueva configuración de comportamiento**... en el **Panel de tareas** de la parte inferior izquierda de la ventana.

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

3. Seleccione un elemento de extensión de comportamiento en la sección **posición de extensión de elemento de comportamiento** .

4. Use el botón **arriba** o **abajo** situado en el lado izquierdo de la lista para cambiar la posición del elemento seleccionado.

##### <a name="editing-the-configuration-of-behavior-element-extensions"></a>Editar la configuración de extensiones de elemento de comportamiento

1. Seleccione uno de los nodos de comportamiento del árbol.

2. Seleccione el comportamiento que contiene el elemento que desea editar.

3. Seleccione la extensión de elemento de comportamiento que desea editar. La configuración del elemento aparece en el panel derecho, donde se puede editar.

#### <a name="protocolmapping"></a>ProtocolMapping

Esta sección permite establecer los tipos de enlaces predeterminados para los distintos protocolos como http, tcp, MSMQ o net.pipe mediante la asignación entre los esquemas de direcciones de protocolo y los posibles enlaces. También puede agregar nuevas asignaciones a otros protocolos.

#### <a name="extensions"></a>Extensiones

Las nuevas extensiones de enlace, extensiones de elemento de enlace, extensiones de punto de conexión estándar y extensiones de comportamiento se pueden registrar para su uso en la configuración de WCF. Las extensiones son pares de nombre/tipo. El nombre define el nombre de la extensión en la configuración, mientras que el tipo implementa la extensión. Hay cuatro tipos de extensiones:

- Las extensiones de enlace definen un tipo entero de enlace. Ejemplo: `basicHttpBinding`.

- Las extensiones de elemento de enlace definen un elemento de un enlace. Ejemplo: `textMessageEncoding`.

- Las extensiones de extremo estándar definen un extremo estándar completo. Ejemplo: `discoveryEndpoint`.

- Las extensiones de elemento de comportamiento definen un elemento de un comportamiento. Ejemplo: `clientVia`.

 Las extensiones registradas en configuración se pueden utilizar como cualquier otro componente WCF del mismo tipo.

##### <a name="adding-a-new-extension"></a>Agregar una nueva extensión

Seleccione uno de los nodos de extensión en los nodos avanzados:

1. Haga clic en **Nueva**.

2. Escriba un nombre y tipo.

3. Haga clic en **OK**.

4. La extensión aparece ahora en el lugar adecuado en el editor. Por ejemplo, si agrega una extensión de elemento de comportamiento, aparece en la lista de extensiones disponibles.

#### <a name="hosting-environment"></a>Entorno de hospedaje

Esta sección permite definir la configuración de creación de instancias para el entorno de hospedaje de servicio.

### <a name="creating-a-configuration-file-using-the-wizard"></a>Crear un archivo de configuración mediante el asistente

Una forma de crear un archivo de configuración nuevo es utilizar el Asistente para nuevo elemento de servicio. El asistente busca los tipos de servicio instalados y otros elementos compatibles con WCF en el equipo, incluidos los directorios virtuales hospedados en Web y COM+, y los carga para que la creación de la configuración sea mucho más sencilla.

#### <a name="creating-a-configuration-file"></a>Crear un archivo de configuración

1. Inicie el editor de configuración de servicio mediante una ventana de comandos para navegar a la ubicación de instalación de WCF y, a continuación, escriba `SvcConfigEditor.exe` .

2. En el menú **archivo** , seleccione **abrir** y haga clic en **ejecutable**, **servicio com+** o **servicio hospedado en host**, dependiendo del tipo de archivo de configuración que desee crear.

3. En el cuadro de diálogo **abrir** , navegue hasta el archivo específico para el que desea crear un archivo de configuración y haga doble clic en él.

4. En el menú **archivo** , seleccione **Agregar nuevo elemento** y haga clic en **servicio**. Se abre el Asistente para nuevo elemento de servicio.

5. Siga los pasos en el asistente para crear el nuevo servicio.

> [!NOTE]
> Si desea utilizar NetPeerTcpBinding del archivo de configuración generado por el asistente, tiene que agregar manualmente un elemento de configuración de enlace y modificar el atributo `mode` de su elemento `security` a "Ninguno".

## <a name="configuring-com"></a>Configurar COM+

El editor de configuración de servicio le permite crear un nuevo archivo de configuración para una aplicación COM+ existente o editar una configuración COM+ existente. El nodo de **contrato com** solo está visible cuando la `comContract` sección <> existe en el archivo de configuración.

### <a name="creating-a-new-com-configuration"></a>Crear una nueva configuración de COM+

Antes de crear una nueva configuración de COM+, asegúrese de que su aplicación COM+ esté instalada en servicios de componente y registrada en la caché global de ensamblados (GAC).

1. Menú **archivo** : > **integrar**la  ->  **aplicación com+.** Esta operación cierra el archivo abierto actual. Si hay datos no guardados en el archivo actual, aparece el cuadro de diálogo Guardar. A continuación, se inicia el **Asistente para la integración de com+** .

2. En la primera página, seleccione la aplicación COM+ del árbol. Si no encuentra su aplicación COM+ en el árbol, compruebe que está instalada en los servicios de componente y registrada en la caché global de ensamblados (GAC).

3. En la página siguiente, seleccione qué método(s) quiere exponer como servicios WCF. Todos los métodos compatibles en la aplicación COM+ se muestran y se seleccionan de forma predeterminada.

4. Elija un método de hospedaje.

5. Configure otros valores según las guías en el Asistente.

6. El editor de configuración de servicio utiliza en segundo plano ComSvcConfig.exe para generar un archivo de configuración. Después de este paso, puede ver un resumen y salir del Asistente. Se abre el archivo de configuración generado para que pueda editarlo directamente.

### <a name="editing-an-existing-com-configuration"></a>Editar una configuración COM+ existente

1. Seleccione el menú **archivo** -> **abrir**el  ->  **servicio com+**...

2. Seleccione el servicio COM+ que desee editar en la lista.

3. Edite la configuración en el nodo **contratos com** .

    > [!NOTE]
    > También puede abrir directamente un archivo de configuración que contenga contratos COM+ y modificarlo.

## <a name="security"></a>Seguridad

No se garantiza que un archivo de configuración de servicio generado por el editor de configuración sea seguro. Consulte la documentación de [seguridad](./feature-details/security.md) para averiguar cómo proteger los servicios WCF.

Además, el editor de configuración solo se puede utilizar para leer y escribir elementos de configuración de WCF válidos. La herramienta omite los elementos conformes a esquema definidos por el usuario. Tampoco intenta quitar estos elementos del archivo de configuración o determinar sus efectos sobre los elementos de WCF conocidos. Es la responsabilidad del usuario determinar si estos elementos suponen una amenaza para la aplicación o el sistema.
