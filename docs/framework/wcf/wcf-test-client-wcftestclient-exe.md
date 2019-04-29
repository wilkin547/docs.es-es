---
title: Cliente de prueba de WCF (WcfTestClient.exe)
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: cd6f0d7a98ca5bc5f6bee45ad296341a5b91b2a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791201"
---
# <a name="wcf-test-client-wcftestclientexe"></a>Cliente de prueba de WCF (WcfTestClient.exe)
Cliente de Windows Communication Foundation (WCF) prueba (WcfTestClient.exe) es una herramienta de GUI que permite a los usuarios introducir parámetros de prueba, enviar esa entrada al servicio y ver la respuesta que devuelve el servicio. Proporciona un servicio sin problemas las pruebas cuando se combina con el Host de servicio WCF.  
  
 Normalmente puede encontrar el cliente de prueba de WCF (WcfTestClient.exe) en la siguiente ubicación: `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` : Comunidad puede ser uno de "Enterprise", "Professional" o "Comunidad" dependiendo de qué nivel de Visual Studio está instalado.
  
## <a name="scenarios-for-using-test-client"></a>Escenarios para utilizar el cliente de prueba  
 Las secciones siguientes tratan los escenarios más comunes en los que puede usar el cliente de prueba WCF para simplificar el proceso de desarrollo.  
  
### <a name="inside-visual-studio"></a>Descripción general de Visual Studio  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>El host de servicio de WCF inicia el cliente de prueba de WCF con un servicio único  
 Después de crear un nuevo proyecto de servicio WCF y presione F5 para iniciar al depurador, el Host de servicio WCF empieza a hospedar el servicio en el proyecto. A continuación, el cliente de prueba WCF se abre y muestra una lista de extremos de servicio definidos en el archivo de configuración. Puede probar los parámetros e invocar el servicio y repetir este proceso para probar y validar su servicio de forma continuada.  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>El host de servicio de WCF inicia el cliente de prueba de WCF con varios servicios  
 También puede usar el cliente de prueba WCF para ayudar a depurar un proyecto de servicio que contiene varios servicios. Cuando se abre el cliente de prueba WCF, automáticamente recorre en iteración la lista de servicios en el proyecto y abre para probarlos.  
  
### <a name="outside-visual-studio"></a>Fuera de Visual Studio  
 También puede invocar al cliente de prueba de WCF (WcfTestClient.exe) fuera de Visual Studio para probar un servicio arbitrario en Internet. Para encontrar la herramienta, vaya a la ubicación siguiente:  
  
 `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` (donde Comunidad puede ser uno de "Enterprise", "Professional" o "Comunidad", dependiendo de qué nivel de Visual Studio está instalado en el equipo)
  
 Para usar la herramienta, haga doble clic en el nombre de archivo para abrirlo desde esta ubicación o iníciela desde una línea de comandos.  
  
 Cliente de prueba WCF toma un número arbitrario de URI como argumentos de línea de comandos.  Se trata de los URI de los servicios que se pueden probar.  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 Una vez abierta la ventana de cliente de prueba WCF, haga clic en **archivo**->**Agregar servicio**y escriba la dirección del extremo del servicio que desea abrir.  
  
## <a name="wcf-test-client-user-interface"></a>Interfaz de usuario del cliente de prueba de WCF  
 Puede usar el cliente de prueba WCF con un servicio único o varios servicios.  
  
### <a name="service-operations"></a>Operaciones de servicio  
 El panel izquierdo de la ventana principal del cliente de prueba WCF enumera todos los servicios disponibles, junto con sus operaciones y los puntos de conexión respectivos.  
  
 Al hacer doble clic en una operación, puede ver su contenido en el panel derecho dentro de una nueva pestaña con el nombre de la operación.  
  
 El panel izquierdo también hace una lista de los archivos de configuración del cliente. Haga doble clic en cualquiera de los elementos para mostrar el contenido del archivo en una nueva ventana con pestañas en el panel derecho.  
  
### <a name="entering-test-parameters"></a>Introducir parámetros de prueba  
 Para ver los parámetros de prueba, haga doble clic en una operación para abrirla en el panel derecho. Los parámetros se muestran en **con formato** vista de forma predeterminada, y puede escribir valores arbitrarios para los parámetros probar el servicio.  
  
 Para ver el XML del mensaje, haga clic en **XML**. Para enviarlos al servicio, haga clic en **Invoke**.  
  
 Para un parámetro de conjunto de datos, haga clic en el **...** situado junto a **editar...** Para editar en una nueva ventana que muestra el control DataGrid. Tenga en cuenta la apariencia de la **copiar DataSet** y **pegar DataSet** botones. Si el esquema del objeto DataSet no se conoce al editarlo por primera vez, el DataGrid está vacío. Debe pegar un objeto DataSet con el mismo esquema en el objeto actual del DataGrid. (Tenga en cuenta que debe copiar el esquema desde otro lugar antes de la operación de pegado.) También puede copiar un objeto de conjunto de datos en el futuro, haga clic en el **copiar DataSet** botón.  
  
 La respuesta del servicio aparece debajo de los parámetros de pruebas.  
  
> [!NOTE]
>  Si el valor de devolución esperado es una cadena, el resultado se mostrará como cadena entrecomillada aunque la entrada proporcionada no estuviera entre comillas.  
  
 Si especificó una operación determinada como unidireccional cuando creó el contrato para el servicio, no se mostrará ninguna respuesta del servicio. En cuanto el mensaje se ponga en la cola para la entrega, se abrirá un cuadro de diálogo para notificarle que el mensaje se envió correctamente.  
  
### <a name="session-support"></a>Compatibilidad de sesión  
 El **iniciar nuevo proxy** casilla de verificación en la pestaña de la operación de servicio le permite activar o desactivar la compatibilidad de la sesión. Este cuadro está desactivado de forma predeterminada.  
  
 Cuando se especifican los parámetros de prueba para una operación concreta (u otra operación en el mismo punto de conexión de servicio) y haga clic en **Invoke** varias veces con la casilla desactivada, estas operaciones comparten un proxy y el estado del servicio es se conserva entre varias operaciones.  
  
 Si el **iniciar nuevo proxy** está activada la casilla de verificación, se inicia un nuevo proxy para cada **Invoke**, el escenario de la sesión anterior finaliza y se restablece el estado del servicio.  
  
### <a name="editing-client-configuration"></a>Edición de la configuración del cliente  
 El panel izquierdo de la ventana principal del cliente de prueba WCF enumera los archivos de configuración de cliente. Haga doble clic en cualquiera de los elementos para mostrar el contenido del archivo en el panel derecho.  
  
#### <a name="edit-with-service-configuration-editor"></a>Edición con el Editor de configuración de servicios  
 Haga clic en **archivo de configuración** en el panel izquierdo y seleccione el menú contextual **editar con SvcConfigEditor**. El Editor de configuración de servicios se inicia con el contenido de la configuración del cliente. Puede editar la configuración y guardarla dentro de la herramienta.  
  
 Después de guardar el archivo en el Editor de configuración de servicio, el cliente de prueba WCF muestra un mensaje de advertencia para informarle de que el archivo se ha modificado fuera y preguntará si desea volver a cargarlo.  
  
 Si selecciona **Sí**, el contenido de la configuración en la pestaña "Client.dll.config" refleja los cambios realizados en el editor.  
  
 Si selecciona **No**, no cambia el contenido de la configuración en la pestaña "Client.dll.config" y el contenido modificado se guarda automáticamente en el archivo de origen.  
  
#### <a name="restore-to-default-configuration"></a>Restauración de la configuración predeterminada  
 Si desea cancelar todos los cambios y restaurar la configuración de cliente predeterminada, haga clic en **archivo de configuración** en el panel izquierdo y seleccione el menú contextual **Restablecer configuración predeterminada**. El valor de la configuración predeterminada se cargan y se restaura el contenido en la pestaña "Client.dll.config".  
  
#### <a name="validate-changes"></a>Validación de los cambios  
 Cuando se cargan los cambios guardados en el cliente de prueba WCF, la configuración se comprueba la validez con el esquema WCF. Si se detectan errores, aparece un cuadro de diálogo con los detalles del error.  
  
 Durante la generación de proxy, la compilación de binarios o invocar el servicio, se deshabilitan los elementos de menú que permiten la edición (es decir, "Editar …", "Restore …" y así sucesivamente). También se deshabilita la invocación del servicio al cargar la configuración actualizada para el cliente de prueba WCF.  
  
#### <a name="persist-client-configuration"></a>Conservación de la configuración del cliente  
 El **herramientas**->**opciones**->**configuración del cliente** pestaña contiene un **siempre regenerar la configuración al iniciar Servicios** opción, que está habilitado de forma predeterminada. Esta opción especifica que cada vez que el cliente de prueba de WCF se carga un servicio, vuelve a generar un archivo de configuración basado en los archivos App.config y el contrato de servicio más reciente.  
  
 Si ha editado la configuración del cliente para el servicio WCF y desea usar siempre este archivo actualizado para depurar el servicio, puede desactivar la **regenerar** opción. Al hacerlo, incluso cuando el servicio de actualización y vuelva a abrir el cliente de prueba WCF, el archivo Client.dll.config es el que se actualizó previamente en lugar de uno regenerado a uno basado en el servicio actualizado.  
  
 Sin embargo, es posible que necesite modificar el archivo de configuración para que sea coherente con el proxy regenerado. Si el proxy regenerado y el archivo de configuración no coinciden porque se ha actualizado un servicio, se producirán errores cuando se invoque el servicio.  
  
> [!CAUTION]
>  Si modificó el archivo de configuración del cliente y seleccionó su reutilización en el futuro, puede encontrar el archivo en la ubicación siguiente:  
>   
>  \Documents and Settings\\proyectos de cliente \My Documents\Test [cuenta de usuario].  
>   
>  La Lista de control de acceso (ACL) de esta carpeta protege cualquier información de credenciales actualizada almacenada en el archivo de configuración del cliente.  
  
### <a name="adding-removing-and-refreshing-services"></a>Adición, eliminación y actualización de servicios  
  
#### <a name="add-service"></a>Agregar servicio  
 Haga clic en **archivo**->**Agregar servicio** para agregar un servicio al cliente de prueba WCF. Después, debe escribir el URI (dirección del extremo) del servicio que se va a agregar. La dirección del servicio puede ser una dirección mex o WSDL.  
  
 También puede encontrar una lista de extremos de 10 Servicios agregados recientemente en el **servicios recientes** submenú. Si selecciona uno de ellos, se agrega el servicio especificado al cliente de prueba de WCF.  
  
 También puede haga clic en la raíz del árbol de servicios **Mis proyectos de servicios**y seleccione **Agregar servicio** para lograr el mismo resultado.  
  
 Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten agregar un servicio están deshabilitados. La invocación de servicios también está deshabilitada.  
  
#### <a name="remove-service"></a>Eliminación de servicios  
 Haga clic en la raíz del servicio del servicio que desea eliminar y seleccione **quitar servicio** para quitar un servicio de cliente de prueba WCF.  
  
 Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten quitar un servicio están deshabilitados. La invocación de servicios también está deshabilitada.  
  
#### <a name="refresh-service"></a>Actualización de servicios  
 Si se realiza un cambio en el servicio mientras se está ejecutando el cliente de prueba WCF y desea asegurarse de que la implementación de cliente de prueba WCF para que el servicio está actualizada, haga clic en la raíz del servicio del servicio y seleccione **Actualizar servicio**. Observe que, después de actualizar, se restablece el estado del servicio.  
  
 Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten actualizar un servicio están deshabilitados. La invocación de servicios también está deshabilitada.  
  
## <a name="location-of-files-generated-by-the-test-client"></a>Ubicación de los archivos generados por el cliente de prueba  
 De forma predeterminada, los almacenes de cliente de prueba WCF generan archivos de código y la configuración de cliente en la carpeta "%appdata%\Local\temp\Test Client Projects". Esta carpeta se elimina después de que salga del cliente de prueba WCF. Si se modifica un archivo de configuración de cliente de prueba WCF y la **siempre regenerar la configuración cuando se inicien servicios** opción está deshabilitada, el archivo modificado se copia en la carpeta "CachedConfig" bajo "Mi Documents\Test Client Projects" con un archivo XML de asignación (metadatos-dirección-a-nombre de archivo) como un índice.  
  
 También puede iniciar el cliente de prueba WCF en una línea de comandos, use el `/ProjectPath` cambiar para especificar una nueva ruta de acceso deseado para almacenar los archivos generados o usar la `/RestoreProjectPath` conmutador para restaurar la ubicación predeterminada. La sintaxis es la siguiente:  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 Ejecutar este comando no abre el cliente de prueba WCF. Sólo cambia la ubicación de la carpeta. Puede ejecutar este comando si el cliente de prueba WCF se está ejecutando o no. La nueva ubicación se aplica cuando se reinicia el cliente de prueba WCF. La información de ubicación se puede guardar en el registro, o en el archivo WcfTestClient.exe.option de la carpeta "%appdata%\Local\temp\Test Client Projects".  
  
## <a name="features-supported-by-wcf-test-client"></a>Características admitidas por WCF Test Client  
 La siguiente es una lista de las características admitidas por WCF Test Client:  
  
- Invocación del servicio: Solicitud/respuesta y mensaje unidireccional.  
  
- Enlaces: todos los enlaces admitidos por Svcutil.exe.  
  
- Control de sesión.  
  
- Contrato de mensaje.  
  
- Serialización XML.  
  
 La siguiente es una lista de características no admitidas por WCF Test Client:  
  
- Tipos: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, tipos que implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable>, incluido el atributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> relacionado, y los tipos <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement>, así como el tipo <xref:System.Data.DataTable> de ADO.NET.  
  
- Contrato dúplex.  
  
- Transacción.  
  
- Seguridad: [!INCLUDE[infocard](../../../includes/infocard-md.md)], mediante certificado y mediante nombre de usuario/contraseña.  
  
- Enlaces: WSFederationbinding, cualquier contexto y enlace Https, WebHttpbinding (compatibilidad con mensajes de respuesta de Json).  
  
## <a name="closing-wcf-test-client"></a>Cerrar el cliente de prueba de WCF  
 Puede cerrar el cliente de prueba WCF de las maneras siguientes:  
  
- En el **archivo** menú, haga clic en **Exit**. Como alternativa, en la ventana principal del cliente de prueba WCF, haga clic en **cerrar**. Tanto de estas acciones también apague el Host de servicio WCF y detener el proceso de depuración de Visual Studio si se ha iniciado el cliente de prueba WCF mediante Visual Studio.  
  
- Haga clic en el **Host de servicio WCF** en el área de notificación y, a continuación, haga clic en icono **Exit.** Esto apaga el Host de servicio WCF y de cliente de prueba WCF y detiene el proceso de depuración de Visual Studio.  
  
## <a name="see-also"></a>Vea también

- [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
