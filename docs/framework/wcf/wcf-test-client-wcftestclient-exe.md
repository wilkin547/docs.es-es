---
title: "Cliente de prueba de WCF (WcfTestClient.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
caps.latest.revision: 45
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 45
---
# Cliente de prueba de WCF (WcfTestClient.exe)
El cliente de prueba de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] \(WcfTestClient.exe\) es una herramienta de interfaz gráfica de usuario \(GUI\) que permite a los usuarios especificar parámetros de prueba, enviar esa entrada al servicio y ver la respuesta que éste devuelve.  Proporciona un servicio de prueba sin problemas cuando se combina con el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Puede encontrar el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(WcfTestClient.exe\) en la ubicación siguiente: C:\\Archivos de programa\\Microsoft Visual Studio 9.0\\Common7\\IDE\\  
  
## Escenarios para utilizar el cliente de prueba  
 En las secciones siguientes se discuten los escenarios más comunes en los que puede utilizar el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para hacer su proceso de desarrollo más eficiente.  
  
### Descripción general de Visual Studio  
  
#### El host de servicio de WCF inicia el cliente de prueba de WCF con un servicio único  
 Después de crear un nuevo proyecto de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y presionar F5 para iniciar el depurador, el host de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] empieza a hospedar el servicio en su proyecto.  Entonces, el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se abre automáticamente y muestra una lista de extremos de servicio definidos en el archivo de configuración.  Puede probar los parámetros e invocar el servicio y repetir este proceso para probar y validar su servicio de forma continuada.  
  
#### El host de servicio de WCF inicia el cliente de prueba de WCF con varios servicios  
 También puede usar el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] como ayuda para depurar un proyecto de servicio que contiene varios servicios.  Cuando el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se abre, recorre automáticamente en iteración la lista de servicios de su proyecto y los abre para probarlos.  
  
### Fuera de Visual Studio  
 También puede invocar el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(WcfTestClient.exe\) fuera de Visual Studio para probar un servicio arbitrario en Internet.  Para encontrar la herramienta, vaya a la ubicación siguiente:  
  
 C:\\Archivos de programa\\Microsoft Visual Studio 9.0\\Common7\\IDE\\  
  
 Para usar la herramienta, haga doble clic en el nombre de archivo para abrirlo desde esta ubicación o iníciela desde una línea de comandos.  
  
 El cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] toma un número arbitrario de URI como argumentos de la línea de comandos.  Se trata de los URI de los servicios que se pueden probar.  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 Una vez abierta la ventana del cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], haga clic en **Archivo**\-\>**Agregar servicio** y escriba la dirección del extremo del servicio que quiere abrir.  
  
## Interfaz de usuario del cliente de prueba de WCF  
 Puede utilizar el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con un servicio único o con varios servicios.  
  
### Operaciones de servicio  
 El panel izquierdo de la ventana principal del cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] muestra todos los servicios disponibles, junto con sus extremos y operaciones respectivos.  
  
 Al hacer doble clic en una operación, puede ver su contenido en el panel derecho dentro de una nueva pestaña con el nombre de la operación.  
  
 El panel izquierdo también hace una lista de los archivos de configuración del cliente.  Haga doble clic en cualquiera de los elementos para mostrar el contenido del archivo en una nueva ventana con pestañas en el panel derecho.  
  
### Introducir parámetros de prueba  
 Para ver los parámetros de prueba, haga doble clic en una operación para abrirla en el panel derecho.  De forma predeterminada, los parámetros se muestran en la vista **Con formato**, y puede escribir valores arbitrarios para los mismos con objeto de probar el servicio.  
  
 Para ver el XML del mensaje, haga clic en **XML**.  Para enviarlos al servicio, haga clic en **Invocar**.  
  
 Para un parámetro DataSet, haga clic en el botón **…** situado junto a **Editar…** para editarlo en una nueva ventana que muestra el DataGrid.  Observe que aparecen los botones **Copiar DataSet** y **Pegar DataSet**.  Si el esquema del objeto DataSet no se conoce al editarlo por primera vez, el DataGrid está vacío.  Debe pegar un objeto DataSet con el mismo esquema en el objeto actual del DataGrid.  \(Tenga en cuenta que debe copiar el esquema desde otro lugar antes de la operación de pegado.\) También puede copiar un objeto Dataset para usarlo en el futuro haciendo clic en el botón **Copiar DataSet**.  
  
 La respuesta del servicio aparece debajo de los parámetros de pruebas.  
  
> [!NOTE]
>  Si el valor de devolución esperado es una cadena, el resultado se mostrará como cadena entrecomillada aunque la entrada proporcionada no estuviera entre comillas.  
  
 Si especificó una operación determinada como unidireccional cuando creó el contrato para el servicio, no se mostrará ninguna respuesta del servicio.  En cuanto el mensaje se ponga en la cola para la entrega, se abrirá un cuadro de diálogo para notificarle que el mensaje se envió correctamente.  
  
### Compatibilidad de sesión  
 La casilla **Iniciar nuevo proxy** de la pestaña de una operación de servicio permite alternar la compatibilidad de la sesión.  Este cuadro está desactivado de forma predeterminada.  
  
 Si escribe los parámetros de prueba de una operación concreta \(u otra operación en el mismo extremo de servicio\) y hace clic varias veces en **Invocar** con la casilla desactivada, estas operaciones comparten un proxy y el estado del servicio se conserva entre varias operaciones.  
  
 Si se activa la casilla **Iniciar nuevo proxy**, se inicia un nuevo proxy con cada **invocación**, el escenario de la sesión anterior finaliza y se restablece el estado del servicio.  
  
### Edición de la configuración del cliente  
 El panel izquierdo de la ventana principal del cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] muestra los archivos de configuración del cliente.  Haga doble clic en cualquiera de los elementos para mostrar el contenido del archivo en el panel derecho.  
  
#### Edición con el Editor de configuración de servicios  
 Haga clic con el botón secundario en **Archivo de configuración** en el panel izquierdo y seleccione **Editar con SvcConfigEditor** en el menú contextual.  El Editor de configuración de servicios se inicia con el contenido de la configuración del cliente.  Puede editar la configuración y guardarla dentro de la herramienta.  
  
 Después de guardar el archivo en el Editor de configuración de servicios, el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] muestra un mensaje de advertencia para informarle de que el archivo se ha modificado fuera y pregunta si desea recargarlo.  
  
 Si selecciona **Sí**, el contenido de configuración de la pestaña "Client.dll.config" refleja los cambios que realizó en el editor.  
  
 Si selecciona **No**, el contenido de configuración de la pestaña "Client.dll.config" se mantiene sin modificar y el contenido modificado se guarda automáticamente en el archivo de código fuente.  
  
#### Restauración de la configuración predeterminada  
 Si desea cancelar todos los cambios y restaurar la configuración predeterminada del cliente, haga clic con el botón secundario en **Archivo de configuración** en el panel izquierdo y seleccione **Restablecer configuración predeterminada** en el menú contextual.  Se cargará el valor de configuración predeterminado y se restaurará el contenido de la pestaña "Client.dll.config".  
  
#### Validación de los cambios  
 Cuando se cargan los cambios guardados en el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], se comprueba la validez de la configuración respecto al esquema de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  Si se detectan errores, aparece un cuadro de diálogo con los detalles del error.  
  
 Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten la edición \(es decir, "Editar", "Restaurar", etc.\) están deshabilitados.  La invocación de servicios está también deshabilitada al cargar la configuración actualizada en el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
#### Conservación de la configuración del cliente  
 La pestaña **Herramientas**\-\>**Opciones**\-\>**Configuración del cliente** contiene una opción **Volver a generar siempre la configuración cuando se inicien servicios**, que está habilitada de forma predeterminada.  Esta opción especifica que cada vez que el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] carga un servicio, vuelve a generar un archivo de configuración basado en el último contrato de servicio y en los archivos App.config del servicio.  
  
 Si ha editado la configuración del cliente para el servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y desea usar siempre este archivo actualizado para depurar el servicio, puede desactivar la opción **Volver a generar**.  Al hacerlo, incluso al actualizar el servicio y volver a abrir el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], el archivo Client.dll.config es el que actualizó previamente en lugar de uno regenerado a partir del servicio actualizado.  
  
 Sin embargo, es posible que necesite modificar el archivo de configuración para que sea coherente con el proxy regenerado.  Si el proxy regenerado y el archivo de configuración no coinciden porque se ha actualizado un servicio, se producirán errores cuando se invoque el servicio.  
  
> [!CAUTION]
>  Si modificó el archivo de configuración del cliente y seleccionó su reutilización en el futuro, puede encontrar el archivo en la ubicación siguiente:  
>   
>  \\Documents and Settings\\\[cuenta de usuario\]\\Mis documentos\\Test Client Projects.  
>   
>  La Lista de control de acceso \(ACL\) de esta carpeta protege cualquier información de credenciales actualizada almacenada en el archivo de configuración del cliente.  
  
### Adición, eliminación y actualización de servicios  
  
#### Agregar servicio  
 Haga clic en **Archivo**\-\>**Agregar servicio** para agregar un servicio al cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  Después, debe escribir el URI \(dirección del extremo\) del servicio que se va a agregar.  La dirección del servicio puede ser una dirección mex o WSDL.  
  
 Además, puede encontrar una lista con los 10 últimos extremos de servicio agregados en el submenú **Servicios recientes**.  Si selecciona uno de ellos, el servicio especificado se agregará al cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Para lograr el mismo resultado también puede hacer clic con el botón secundario en la raíz del árbol de servicios **Mis proyectos de servicios**y seleccionar **Agregar servicio**.  
  
 Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten agregar un servicio están deshabilitados.  La invocación de servicios también está deshabilitada.  
  
#### Eliminación de servicios  
 Haga clic con el botón secundario en la raíz del servicio que desea quitar y seleccione **Quitar servicio** para quitar un servicio del cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten quitar un servicio están deshabilitados.  La invocación de servicios también está deshabilitada.  
  
#### Actualización de servicios  
 Si se realiza un cambio en el servicio mientras se está ejecutando el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y desea asegurarse de que la implementación del cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para ese servicio está actualizada, haga clic con el botón secundario en la raíz del servicio y seleccione **Actualizar servicio**.  Observe que, después de actualizar, se restablece el estado del servicio.  
  
 Durante la generación de proxies, la compilación de binarios o la invocación de servicios, los elementos de menú que permiten actualizar un servicio están deshabilitados.  La invocación de servicios también está deshabilitada.  
  
## Ubicación de los archivos generados por el cliente de prueba  
 De forma predeterminada, el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] almacena el código de cliente generado y los archivos de configuración en la carpeta “%appdata%\\Local\\temp\\Test Client Projects".  Esta carpeta se elimina después de cerrar el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  Si se modifica un archivo de configuración en el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y la opción **Volver a generar la configuración siempre cuando se inicien servicios** está deshabilitada, el archivo modificado se copia en la carpeta “Cached Config” de “Mis documentos\\Test Client Projects Documents\\Test Client Projects” con un archivo XML de asignación \(dirección de metadatos a nombre de archivo\) a modo de índice.  
  
 También puede iniciar el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en una línea de comandos, usar el modificador `/ProjectPath` para especificar la nueva ruta de acceso donde desea almacenar los archivos generados o usar el modificador `/RestoreProjectPath` para restaurar la ubicación predeterminada.  La sintaxis es la siguiente:  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 Al ejecutar este comando, no se abre el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  Sólo cambia la ubicación de la carpeta.  Puede ejecutar este comando tanto si el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se está ejecutando como si no.  La nueva ubicación se aplica cuando se reinicia el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  La información sobre la ubicación se puede guardar en el Registro o en el archivo WcfTestClient.exe.option de la carpeta "%appdata%\\Local\\temp\\Test Client Projects".  
  
## Características admitidas por WCF Test Client  
 En la siguiente lista se muestran las características admitidas por el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]:  
  
-   Invocación de servicio: solicitud\/respuesta y mensaje unidireccional.  
  
-   Enlaces: todos los enlaces admitidos por Svcutil.exe.  
  
-   Control de sesión.  
  
-   Contrato de mensaje.  
  
-   Serialización XML.  
  
 En la siguiente lista se muestran las características no admitidas por el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]:  
  
-   Tipos: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, tipos que implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable>, incluido el atributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> relacionado, y los tipos <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement>, así como el tipo <xref:System.Data.DataTable> de ADO.NET.  
  
-   Contrato dúplex.  
  
-   Transacción.  
  
-   Seguridad: [!INCLUDE[infocard](../../../includes/infocard-md.md)], mediante certificado y mediante nombre de usuario\/contraseña.  
  
-   Enlaces: WSFederationbinding, cualquier enlace de contexto y enlace HTTPS, WebHttpbinding \(compatibilidad con mensajes de respuesta JSON\).  
  
## Cerrar el cliente de prueba de WCF  
 El cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se puede cerrar de las maneras siguientes:  
  
-   En el menú **Archivo**, haga clic en **Salir**.  Alternativamente, en la ventana principal del cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], haga clic en **Cerrar**.  Estas dos acciones también cierran el host de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y detienen el proceso de depuración de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] si [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ha iniciado el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Haga clic con el botón secundario en el icono **Host de servicio de WCF** en el área de notificación y, a continuación, haga clic en **Salir.** Esto apaga el host automático de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y el cliente de prueba [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y detiene el proceso de depuración [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
## Vea también  
 [Host de servicio WCF \(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)