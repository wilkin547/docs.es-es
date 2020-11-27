---
title: Cliente de prueba de WCF (WcfTestClient.exe)
description: Obtenga información sobre el cliente de prueba de WCF, que proporciona pruebas de servicio sin problemas cuando se combina con el host de servicio WCF. Enviar valores de prueba del cliente y ver las respuestas del servicio.
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: f583d20edf7eeea87ae1dbf63a3cadef05912833
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264132"
---
# <a name="wcf-test-client-wcftestclientexe"></a>Cliente de prueba de WCF (WcfTestClient.exe)

El cliente de prueba de Windows Communication Foundation (WCF) (WcfTestClient.exe) es una herramienta de interfaz gráfica de usuario que permite a los usuarios introducir parámetros de prueba, enviar esa entrada al servicio y ver la respuesta que devuelve el servicio. Proporciona una experiencia de pruebas de servicio sin problemas cuando se combina con el host de servicio de WCF.

Normalmente, puede encontrar el cliente de prueba de WCF (WcfTestClient.exe) en la siguiente ubicación: `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` -Community puede ser "Enterprise", "Professional" o "Community" en función del nivel de Visual Studio instalado.

## <a name="scenarios-for-using-test-client"></a>Escenarios para utilizar el cliente de prueba

En las secciones siguientes se describen los escenarios más comunes en los que puede usar el cliente de prueba de WCF para simplificar el proceso de desarrollo.

### <a name="inside-visual-studio"></a>Descripción general de Visual Studio

#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>El host de servicio de WCF inicia el cliente de prueba de WCF con un servicio único

Después de crear un nuevo proyecto de servicio WCF y presionar F5 para iniciar el depurador, el host de servicio WCF comienza a hospedar el servicio en el proyecto. Después, el cliente de prueba de WCF se abre y muestra una lista de puntos de conexión de servicio definidos en el archivo de configuración. Puede probar los parámetros e invocar el servicio y repetir este proceso para probar y validar su servicio de forma continuada.

#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>El host de servicio de WCF inicia el cliente de prueba de WCF con varios servicios

También puede usar el cliente de prueba de WCF para ayudar a depurar un proyecto de servicio que contiene varios servicios. Cuando se abre el cliente de prueba de WCF, se itera automáticamente en la lista de servicios del proyecto y se abren para realizar pruebas.

### <a name="outside-visual-studio"></a>Fuera de Visual Studio

También puede invocar el cliente de prueba de WCF (WcfTestClient.exe) fuera de Visual Studio para probar un servicio arbitrario en Internet. Para encontrar la herramienta, vaya a la ubicación siguiente:

`C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` (donde Community puede ser "Enterprise", "Professional" o "Community", según el nivel de Visual Studio instalado en el equipo)

Para usar la herramienta, haga doble clic en el nombre de archivo para abrirlo desde esta ubicación o iníciela desde una línea de comandos.

El cliente de prueba de WCF toma un número arbitrario de URI como argumentos de la línea de comandos.  Se trata de los URI de los servicios que se pueden probar.

`wcfTestClient.exe URI1 URI2 …`

Una vez abierta la ventana del cliente de prueba WCF, haga clic en **archivo** -> **Agregar servicio** y escriba la dirección del extremo del servicio que desea abrir.

## <a name="wcf-test-client-user-interface"></a>Interfaz de usuario del cliente de prueba de WCF

Puede usar el cliente de prueba de WCF con un solo servicio o con varios servicios.

### <a name="service-operations"></a>Operaciones de servicio

En el panel izquierdo de la ventana principal del cliente de prueba de WCF se enumeran todos los servicios disponibles, junto con sus respectivos extremos y operaciones.

Al hacer doble clic en una operación, puede ver su contenido en el panel derecho dentro de una nueva pestaña con el nombre de la operación.

El panel izquierdo también hace una lista de los archivos de configuración del cliente. Haga doble clic en cualquiera de los elementos para mostrar el contenido del archivo en una nueva ventana con pestañas en el panel derecho.

### <a name="entering-test-parameters"></a>Introducir parámetros de prueba

Para ver los parámetros de prueba, haga doble clic en una operación para abrirla en el panel derecho. De forma predeterminada, los parámetros se muestran en la vista **con formato** y se pueden especificar valores arbitrarios para los parámetros con el fin de probar el servicio.

Para ver el XML del mensaje, haga clic en **XML**. Para enviarlos al servicio, haga clic en **invocar**.

Para un parámetro de conjunto de parámetros, haga clic en **...** situado junto a **Editar...** para editarlo en una nueva ventana que muestra el control DataGrid. Observe la apariencia de los botones **copiar conjunto** de DataSet y **pegar conjunto** de los mismos. Si el esquema del objeto DataSet no se conoce al editarlo por primera vez, el DataGrid está vacío. Debe pegar un objeto DataSet con el mismo esquema en el objeto actual del DataGrid. (Tenga en cuenta que debe copiar el esquema de otra parte antes de la operación de pegado). También puede copiar un objeto de conjunto de objetos para su uso futuro haciendo clic en el botón **copiar conjunto de copia** de los mismos.

La respuesta del servicio aparece debajo de los parámetros de pruebas.

> [!NOTE]
> Si el valor de devolución esperado es una cadena, el resultado se mostrará como cadena entrecomillada aunque la entrada proporcionada no estuviera entre comillas.

Si especificó una operación determinada como unidireccional cuando creó el contrato para el servicio, no se mostrará ninguna respuesta del servicio. En cuanto el mensaje se ponga en la cola para la entrega, se abrirá un cuadro de diálogo para notificarle que el mensaje se envió correctamente.

### <a name="session-support"></a>Compatibilidad de sesión

La casilla **iniciar un nuevo proxy** en la pestaña de una operación de servicio permite alternar la compatibilidad de la sesión. Este cuadro está desactivado de forma predeterminada.

Al escribir parámetros de prueba para una operación específica (u otra operación en el mismo extremo de servicio) y hacer clic varias veces en **invocar** con la casilla desactivada, estas operaciones comparten un proxy y el estado del servicio se conserva entre varias operaciones.

Si la casilla **iniciar un nuevo proxy** está activada, se inicia un nuevo proxy para cada **invocación**, se finaliza el escenario de la sesión anterior y se restablece el estado del servicio.

### <a name="editing-client-configuration"></a>Edición de la configuración del cliente

En el panel izquierdo de la ventana principal del cliente de prueba de WCF se muestran los archivos de configuración del cliente. Haga doble clic en cualquiera de los elementos para mostrar el contenido del archivo en el panel derecho.

#### <a name="edit-with-service-configuration-editor"></a>Edición con el Editor de configuración de servicios

Haga clic con el botón derecho en **archivo de configuración** en el panel izquierdo y seleccione el menú contextual **editar con SvcConfigEditor**. El Editor de configuración de servicios se inicia con el contenido de la configuración del cliente. Puede editar la configuración y guardarla dentro de la herramienta.

Después de guardar el archivo en el editor de configuración de servicio, el cliente de prueba de WCF muestra un mensaje de advertencia para informarle de que el archivo se ha modificado fuera de y le pregunta si desea recargarlo.

Si selecciona **sí**, el contenido de configuración de la pestaña "Client.dll.config" refleja los cambios realizados en el editor.

Si selecciona **no**, el contenido de configuración de la pestaña "Client.dll.config" permanece sin cambios y el contenido modificado se guarda automáticamente en el archivo de código fuente.

#### <a name="restore-to-default-configuration"></a>Restauración de la configuración predeterminada

Si desea cancelar todos los cambios y restaurar la configuración de cliente predeterminada, haga clic con el botón secundario en **archivo de configuración** en el panel izquierdo y seleccione el menú contextual **restaurar en configuración predeterminada**. Se carga el valor de configuración predeterminado y se restaura el contenido en la pestaña "Client.dll.config".

#### <a name="validate-changes"></a>Validación de los cambios

Cuando se cargan los cambios guardados en el cliente de prueba de WCF, se comprueba la validez de la configuración en relación con el esquema de WCF. Si se detectan errores, aparece un cuadro de diálogo con los detalles del error.

Durante la generación de proxy, la compilación binaria o la invocación de servicios, los elementos de menú que admiten la edición (es decir, "Edit...", "restore...", etc.) están deshabilitados. La invocación del servicio también está deshabilitada al cargar la configuración actualizada en el cliente de prueba de WCF.

#### <a name="persist-client-configuration"></a>Conservación de la configuración del cliente

La **Tools** -> **Options** -> pestaña Configuración del **cliente** opciones de herramientas contiene una opción volver a generar siempre la configuración **al iniciar servicios** , que está habilitada de forma predeterminada. Esta opción especifica que cada vez que el cliente de prueba de WCF carga un servicio, regenera un archivo de configuración basado en el contrato de servicio y los archivos de App.config de servicio más recientes.

Si ha editado la configuración de cliente para el servicio WCF y desea usar siempre este archivo actualizado para depurar el servicio, puede desactivar la opción **regenerar** . Al hacerlo, incluso cuando se actualiza el servicio y se vuelve a abrir el cliente de prueba de WCF, el archivo Client.dll.config es el que se actualizó anteriormente en lugar de volver a generarlo en función del servicio actualizado.

Sin embargo, es posible que necesite modificar el archivo de configuración para que sea coherente con el proxy regenerado. Si el proxy regenerado y el archivo de configuración no coinciden porque se ha actualizado un servicio, se producirán errores cuando se invoque el servicio.

> [!CAUTION]
> Si modificó el archivo de configuración del cliente y seleccionó su reutilización en el futuro, puede encontrar el archivo en la ubicación siguiente:
>
> \Documents and Settings \\ [cuenta de usuario] \Mis Documentos\test Client Projects.
>
> La Lista de control de acceso (ACL) de esta carpeta protege cualquier información de credenciales actualizada almacenada en el archivo de configuración del cliente.

### <a name="adding-removing-and-refreshing-services"></a>Adición, eliminación y actualización de servicios

#### <a name="add-service"></a>Add Service (Agregar servicio)

Haga clic en **archivo** -> **Agregar servicio** para agregar un servicio al cliente de prueba de WCF. Después, debe escribir el URI (dirección del extremo) del servicio que se va a agregar. La dirección del servicio puede ser una dirección mex o WSDL.

También puede encontrar una lista de los 10 puntos de conexión de los servicios agregados recientemente en el submenú **servicios recientes** . Si selecciona uno de ellos, se agrega el servicio especificado al cliente de prueba de WCF.

También puede hacer clic con el botón secundario en la raíz del árbol de servicio **mis proyectos de servicio** y seleccionar **Agregar servicio** para lograr el mismo resultado.

Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten agregar un servicio están deshabilitados. La invocación de servicios también está deshabilitada.

#### <a name="remove-service"></a>Eliminación de servicios

Haga clic con el botón secundario en la raíz del servicio que se va a quitar y seleccione **quitar servicio** para quitar un servicio del cliente de prueba de WCF.

Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten quitar un servicio están deshabilitados. La invocación de servicios también está deshabilitada.

#### <a name="refresh-service"></a>Actualización de servicios

Si se realiza un cambio en el servicio mientras el cliente de prueba de WCF se está ejecutando y desea asegurarse de que la implementación del cliente de prueba de WCF para ese servicio está actualizada, haga clic con el botón secundario en la raíz del servicio y seleccione **Actualizar servicio**. Observe que, después de actualizar, se restablece el estado del servicio.

Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten actualizar un servicio están deshabilitados. La invocación de servicios también está deshabilitada.

## <a name="location-of-files-generated-by-the-test-client"></a>Ubicación de los archivos generados por el cliente de prueba

De forma predeterminada, el cliente de prueba de WCF almacena los archivos de configuración y el código de cliente generados en la carpeta "%appdata%\Local\temp\Test Client Projects". Esta carpeta se elimina una vez finalizado el cliente de prueba de WCF. Si se modifica un archivo de configuración en el cliente de prueba de WCF y la opción **volver a generar siempre la configuración cuando se inician servicios** está deshabilitada, el archivo modificado se copia en la carpeta "CachedConfig" en "My Documentos\test Client Projects" con un archivo XML de asignación (Metadata-Address-to-File-Name) como índice.

También puede iniciar el cliente de prueba de WCF en una línea de comandos, usar el `/ProjectPath` modificador para especificar una nueva ruta de acceso deseada para almacenar los archivos generados o usar el `/RestoreProjectPath` modificador para restaurar la ubicación predeterminada. La sintaxis es la siguiente:

`wcfTestClient.exe /ProjectPath [desired location]`

La ejecución de este comando no abre el cliente de prueba de WCF. Sólo cambia la ubicación de la carpeta. Puede ejecutar este comando si el cliente de prueba de WCF se está ejecutando o no. La nueva ubicación se aplica cuando se reinicia el cliente de prueba de WCF. La información de ubicación se puede guardar en el registro o en el archivo WcfTestClient.exe. Option en la carpeta "%appdata%\Local\temp\Test Client Projects".

## <a name="features-supported-by-wcf-test-client"></a>Características admitidas por WCF Test Client

A continuación se muestra una lista de las características admitidas por el cliente de prueba de WCF:

- Invocación de servicio: solicitud/respuesta y mensaje unidireccional.

- Enlaces: todos los enlaces admitidos por Svcutil.exe.

- Control de sesión.

- Contrato de mensaje.

- Serialización XML.

A continuación se muestra una lista de características no admitidas por el cliente de prueba de WCF:

- Tipos: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, tipos que implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable>, incluido el atributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> relacionado, y los tipos <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement>, así como el tipo <xref:System.Data.DataTable> de ADO.NET.

- Contrato dúplex.

- Transacción.

- Seguridad: CardSpace, certificado y nombre de usuario y contraseña.

- Enlaces: WSFederationbinding, cualquier enlace de contexto y enlace HTTPS, WebHttpbinding (compatibilidad con mensajes de respuesta JSON).

## <a name="closing-wcf-test-client"></a>Cerrar el cliente de prueba de WCF

Puede cerrar el cliente de prueba de WCF de las siguientes maneras:

- En el menú **Archivo** , haga clic en **Salir**. Como alternativa, en la ventana principal del cliente de prueba de WCF, haga clic en **cerrar**. Ambas acciones también apagan el host automático del servicio WCF y detienen el proceso de depuración de Visual Studio si Visual Studio inició el cliente de prueba WCF.

- Haga clic con el botón secundario en el icono **host del servicio WCF** en el área de notificación y, a continuación, haga clic en **salir.** Esto apaga el host automático del servicio WCF y el cliente de prueba de WCF, y detiene el proceso de depuración de Visual Studio.

## <a name="see-also"></a>Vea también

- [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
