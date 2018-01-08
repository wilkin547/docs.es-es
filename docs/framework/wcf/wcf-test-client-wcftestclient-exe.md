---
title: Cliente de prueba de WCF (WcfTestClient.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
caps.latest.revision: "45"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18866260c5d14cf27634afcd8391b159abac1dd1
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2018
---
# <a name="wcf-test-client-wcftestclientexe"></a>Cliente de prueba de WCF (WcfTestClient.exe)
El cliente de prueba de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] (WcfTestClient.exe) es una herramienta de interfaz gráfica de usuario (GUI) que permite a los usuarios especificar parámetros de prueba, enviar esa entrada al servicio y ver la respuesta que éste devuelve. Proporciona un servicio de prueba sin problemas cuando se combina con el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Normalmente puede encontrar el [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (WcfTestClient.exe) en la siguiente ubicación: C:\Program Files (x86) \Microsoft Visual Studio\2017\Community\Common7\IDE - Comunidad puede ser uno de "Enterprise", "Professional" o "Comunidad" Dependiendo de qué nivel de Visual Studio está instalado.
  
## <a name="scenarios-for-using-test-client"></a>Escenarios para utilizar el cliente de prueba  
 En las secciones siguientes se discuten los escenarios más comunes en los que puede utilizar el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para hacer su proceso de desarrollo más eficiente.  
  
### <a name="inside-visual-studio"></a>Descripción general de Visual Studio  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>El host de servicio de WCF inicia el cliente de prueba de WCF con un servicio único  
 Después de crear un nuevo proyecto de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y presionar F5 para iniciar el depurador, el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] empieza a hospedar el servicio en su proyecto. Entonces, el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se abre automáticamente y muestra una lista de extremos de servicio definidos en el archivo de configuración. Puede probar los parámetros e invocar el servicio y repetir este proceso para probar y validar su servicio de forma continuada.  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>El host de servicio de WCF inicia el cliente de prueba de WCF con varios servicios  
 También puede usar el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] como ayuda para depurar un proyecto de servicio que contiene varios servicios. Cuando el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se abre, recorre automáticamente en iteración la lista de servicios de su proyecto y los abre para probarlos.  
  
### <a name="outside-visual-studio"></a>Fuera de Visual Studio  
 También puede invocar el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) fuera de Visual Studio para probar un servicio arbitrario en Internet. Para encontrar la herramienta, vaya a la ubicación siguiente:  
  
 C:\Archivos de programa\Microsoft Visual Studio 9.0\Common7\IDE\  
  
 Para usar la herramienta, haga doble clic en el nombre de archivo para abrirlo desde esta ubicación o iníciela desde una línea de comandos.  
  
 El cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] toma un número arbitrario de URI como argumentos de la línea de comandos.  Se trata de los URI de los servicios que se pueden probar.  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 Después de la [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se abre la ventana de cliente de prueba, haga clic en **archivo**->**Agregar servicio**y escriba la dirección del extremo del servicio que desea abrir.  
  
## <a name="wcf-test-client-user-interface"></a>Interfaz de usuario del cliente de prueba de WCF  
 Puede utilizar el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con un servicio único o con varios servicios.  
  
### <a name="service-operations"></a>Operaciones de servicio  
 El panel izquierdo de la ventana principal del cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] muestra todos los servicios disponibles, junto con sus extremos y operaciones respectivos.  
  
 Al hacer doble clic en una operación, puede ver su contenido en el panel derecho dentro de una nueva pestaña con el nombre de la operación.  
  
 El panel izquierdo también hace una lista de los archivos de configuración del cliente. Haga doble clic en cualquiera de los elementos para mostrar el contenido del archivo en una nueva ventana con pestañas en el panel derecho.  
  
### <a name="entering-test-parameters"></a>Introducir parámetros de prueba  
 Para ver los parámetros de prueba, haga doble clic en una operación para abrirla en el panel derecho. Los parámetros se muestran en **con formato** vista de forma predeterminada, donde puede escribir valores arbitrarios para los parámetros probar el servicio.  
  
 Para ver el XML del mensaje, haga clic en **XML**. Para enviarlos al servicio, haga clic en **Invoke**.  
  
 Para un parámetro de conjunto de datos, haga clic en el **...** situado junto a **editar...** para editarlo en una nueva ventana que muestra el control DataGrid. Tenga en cuenta la apariencia de la **copiar DataSet** y **pegar DataSet** botones. Si el esquema del objeto DataSet no se conoce al editarlo por primera vez, el DataGrid está vacío. Debe pegar un objeto DataSet con el mismo esquema en el objeto actual del DataGrid. (Tenga en cuenta que debe copiar el esquema desde otro lugar antes de la operación de pegado.) También puede copiar un objeto de conjunto de datos para el uso futuro, haga clic en el **copiar DataSet** botón.  
  
 La respuesta del servicio aparece debajo de los parámetros de pruebas.  
  
> [!NOTE]
>  Si el valor de devolución esperado es una cadena, el resultado se mostrará como cadena entrecomillada aunque la entrada proporcionada no estuviera entre comillas.  
  
 Si especificó una operación determinada como unidireccional cuando creó el contrato para el servicio, no se mostrará ninguna respuesta del servicio. En cuanto el mensaje se ponga en la cola para la entrega, se abrirá un cuadro de diálogo para notificarle que el mensaje se envió correctamente.  
  
### <a name="session-support"></a>Compatibilidad de sesión  
 El **iniciar nuevo proxy** casilla de verificación en la pestaña de una operación de servicio le permite activar o desactivar la compatibilidad de la sesión. Este cuadro está desactivado de forma predeterminada.  
  
 Cuando se especifican los parámetros de prueba de una operación concreta (u otra operación en el mismo extremo de servicio) y haga clic en **Invoke** varias veces con la casilla de verificación desactivada, estas operaciones comparten un proxy y el estado del servicio es se conserva entre varias operaciones.  
  
 Si el **iniciar nuevo proxy** casilla está activada, se inicia un nuevo proxy para cada **Invoke**, el escenario de la sesión anterior finaliza y se restablece el estado del servicio.  
  
### <a name="editing-client-configuration"></a>Edición de la configuración del cliente  
 El panel izquierdo de la ventana principal del cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] muestra los archivos de configuración del cliente. Haga doble clic en cualquiera de los elementos para mostrar el contenido del archivo en el panel derecho.  
  
#### <a name="edit-with-service-configuration-editor"></a>Edición con el Editor de configuración de servicios  
 Haga clic en **el archivo de configuración** en el panel izquierdo y seleccione el menú contextual **editar con SvcConfigEditor**. El Editor de configuración de servicios se inicia con el contenido de la configuración del cliente. Puede editar la configuración y guardarla dentro de la herramienta.  
  
 Después de guardar el archivo en el Editor de configuración de servicios, el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] muestra un mensaje de advertencia para informarle de que el archivo se ha modificado fuera y pregunta si desea recargarlo.  
  
 Si selecciona **Sí**, el contenido de la configuración de la pestaña "Client.dll.config" refleja los cambios realizados en el editor.  
  
 Si selecciona **n**, no cambie el contenido de la configuración de la pestaña "Client.dll.config" y el contenido modificado se guarda automáticamente en el archivo de origen.  
  
#### <a name="restore-to-default-configuration"></a>Restauración de la configuración predeterminada  
 Si desea cancelar todos los cambios y restaurar la configuración de cliente predeterminada, haga clic en **el archivo de configuración** en el panel izquierdo y seleccione el menú contextual **Restablecer configuración predeterminada**. El valor de configuración predeterminado se cargan y se restaura el contenido en la pestaña "Client.dll.config".  
  
#### <a name="validate-changes"></a>Validación de los cambios  
 Cuando se cargan los cambios guardados en el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], se comprueba la validez de la configuración respecto al esquema de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Si se detectan errores, aparece un cuadro de diálogo con los detalles del error.  
  
 Durante la generación de proxy, compilación de binarios o la invocación de servicios, los elementos de menú que admiten la edición (es decir, "Editar...", "Restaurar..." etc.) están deshabilitados. La invocación de servicios está también deshabilitada al cargar la configuración actualizada en el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
#### <a name="persist-client-configuration"></a>Conservación de la configuración del cliente  
 El **herramientas**->**opciones**->**configuración de cliente** pestaña contiene un **siempre regenerar la configuración al iniciar Servicios** opción, que está habilitada de forma predeterminada. Esta opción especifica que cada vez que el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] carga un servicio, vuelve a generar un archivo de configuración basado en el último contrato de servicio y en los archivos App.config del servicio.  
  
 Si ha modificado la configuración del cliente para su [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio y desea usar siempre este archivo actualizado para depurar el servicio, puede desactivar la **regenerar** opción. Al hacerlo, incluso al actualizar el servicio y volver a abrir el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], el archivo Client.dll.config es el que actualizó previamente en lugar de uno regenerado a partir del servicio actualizado.  
  
 Sin embargo, es posible que necesite modificar el archivo de configuración para que sea coherente con el proxy regenerado. Si el proxy regenerado y el archivo de configuración no coinciden porque se ha actualizado un servicio, se producirán errores cuando se invoque el servicio.  
  
> [!CAUTION]
>  Si modificó el archivo de configuración del cliente y seleccionó su reutilización en el futuro, puede encontrar el archivo en la ubicación siguiente:  
>   
>  \Documents and Settings\\[cuenta de usuario] \My Documents\Test cliente proyectos.  
>   
>  La Lista de control de acceso (ACL) de esta carpeta protege cualquier información de credenciales actualizada almacenada en el archivo de configuración del cliente.  
  
### <a name="adding-removing-and-refreshing-services"></a>Adición, eliminación y actualización de servicios  
  
#### <a name="add-service"></a>Agregar servicio  
 Haga clic en **archivo**->**Agregar servicio** para agregar un servicio a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] cliente de prueba. Después, debe escribir el URI (dirección del punto de conexión) del servicio que se va a agregar. La dirección del servicio puede ser una dirección mex o WSDL.  
  
 También puede encontrar una lista de extremos de 10 servicio recientemente agregados en la **servicios recientes** submenú. Si selecciona uno de ellos, el servicio especificado se agregará al cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 También puede haga clic en la raíz del árbol de servicios **Mis proyectos de servicios**y seleccione **Agregar servicio** para lograr el mismo resultado.  
  
 Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten agregar un servicio están deshabilitados. La invocación de servicios también está deshabilitada.  
  
#### <a name="remove-service"></a>Eliminación de servicios  
 Haga clic en la raíz del servicio que desea quitar y seleccione **quitar el servicio** para quitar un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] cliente de prueba.  
  
 Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten quitar un servicio están deshabilitados. La invocación de servicios también está deshabilitada.  
  
#### <a name="refresh-service"></a>Actualización de servicios  
 Si se realiza un cambio en el servicio mientras [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] cliente de prueba se está ejecutando y desea asegurarse de que el [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] implementación de cliente de prueba para que el servicio está actualizado, haga clic en la raíz del servicio y seleccione **actualizar Servicio**. Observe que, después de actualizar, se restablece el estado del servicio.  
  
 Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten actualizar un servicio están deshabilitados. La invocación de servicios también está deshabilitada.  
  
## <a name="location-of-files-generated-by-the-test-client"></a>Ubicación de los archivos generados por el cliente de prueba  
 De forma predeterminada, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] almacena de cliente de prueba generado los archivos de código y la configuración de cliente en la carpeta "%appdata%\Local\temp\Test Client Projects". Esta carpeta se elimina después de cerrar el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Si se modifica un archivo de configuración en [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] cliente de prueba y el **siempre regenerar la configuración cuando se inicien servicios** opción está deshabilitada, el archivo modificado se copia en la carpeta "Cached Config" en "Mis documentos\test Client Projects Documents\Test Client Projects"con un archivo de asignación (dirección de metadatos-a-archivo-nombre) XML como un índice.  
  
 También puede iniciar el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en una línea de comandos, usar el modificador `/ProjectPath` para especificar la nueva ruta de acceso donde desea almacenar los archivos generados o usar el modificador `/RestoreProjectPath` para restaurar la ubicación predeterminada. La sintaxis es la siguiente:  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 Al ejecutar este comando, no se abre el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Sólo cambia la ubicación de la carpeta. Puede ejecutar este comando tanto si el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se está ejecutando como si no. La nueva ubicación se aplica cuando se reinicia el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. La información de ubicación puede guardarse en el registro o en el archivo WcfTestClient.exe.option de la carpeta "%appdata%\Local\temp\Test Client Projects".  
  
## <a name="features-supported-by-wcf-test-client"></a>Características admitidas por WCF Test Client  
 En la siguiente lista se muestran las características admitidas por el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]:  
  
-   Invocación de servicio: solicitud/respuesta y mensaje unidireccional.  
  
-   Enlaces: todos los enlaces admitidos por Svcutil.exe.  
  
-   Control de sesión.  
  
-   Contrato de mensaje.  
  
-   Serialización XML.  
  
 En la siguiente lista se muestran las características no admitidas por el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]:  
  
-   Tipos: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, tipos que implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable>, incluido el atributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> relacionado, y los tipos <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement>, así como el tipo <xref:System.Data.DataTable> de ADO.NET.  
  
-   Contrato dúplex.  
  
-   Transacción.  
  
-   Seguridad: [!INCLUDE[infocard](../../../includes/infocard-md.md)], mediante certificado y mediante nombre de usuario/contraseña.  
  
-   Enlaces: WSFederationbinding, cualquier enlace de contexto y enlace HTTPS, WebHttpbinding (compatibilidad con mensajes de respuesta JSON).  
  
## <a name="closing-wcf-test-client"></a>Cerrar el cliente de prueba de WCF  
 El cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se puede cerrar de las maneras siguientes:  
  
-   En el **archivo** menú, haga clic en **Exit**. O bien, en la [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ventana principal del cliente de prueba, haga clic en **cerrar**. Estas dos acciones también cierran el host de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y detienen el proceso de depuración de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] si [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ha iniciado el cliente de prueba de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
-   Haga clic en el **Host de servicio WCF** icono en el área de notificación y, a continuación, haga clic en **salir.** Esto apaga el host automático de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y detiene el proceso de depuración [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
