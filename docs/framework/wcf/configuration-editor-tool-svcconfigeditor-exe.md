---
title: "Herramienta del editor de configuraci&#243;n (SvcConfigEditor.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Archivo de configuración"
  - "esquema de los archivos de configuración"
  - "archivos de configuración"
  - "archivos de configuración, crear"
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
caps.latest.revision: 45
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 45
---
# Herramienta del editor de configuraci&#243;n (SvcConfigEditor.exe)
El editor de configuración de servicio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] permite a los administradores y desarrolladores crear y modificar la configuración para [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] mediante una interfaz gráfica de usuario.Con esta herramienta puede administrar los valores para los enlaces, comportamientos, servicios y diagnósticos [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sin tener que editar directamente los archivos de configuración XML.  
  
 El Editor de configuración de servicio se puede encontrar en la carpeta C:\\Archivos de programa\\Microsoft SDKs\\Windows\\v6.0\\Bin.  
  
## El editor de configuración de WCF  
 El editor de configuración de servicio viene con un asistente que lo guía a través de todos los pasos para configurar un servicio o cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Se le aconseja encarecidamente que utilice directamente el asistente en lugar del editor.  
  
 Si ya tiene algunos archivos de configuración que obedecen al esquema estándar de System.Configuration, puede administrar valores concretos para enlaces, comportamiento, servicios y diagnósticos mediante la interfaz de usuario.El editor de configuración de servicio le permite administrar los valores para los archivos de configuración [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] existentes, así como archivos ejecutables, servicios de COM\+ y servicios hospedados en web.Cuando se abre un servicio hospedado en web con el Editor de configuración de servicios, se muestran las secciones de configuraciones heredadas de los nodos de nivel superior y la propia configuración del servicio.  
  
 Dado que la configuración [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se encuentra en la sección `<system.serviceModel>` del archivo de configuración, el editor actúa exclusivamente sobre el contenido de este elemento y no accede a otros elementos del mismo archivo.Puede navegar directamente a archivos de configuración existentes o puede seleccionar un ensamblado que contenga un servicio, un directorio virtual o un servicio de COM\+.El editor carga el archivo de configuración para ese servicio particular y permite que el usuario agregue elementos nuevos o modifique elementos existentes anidados en la sección `<system.serviceModel>` del archivo de configuración.  
  
 El editor admite IntelliSense y exige la compatibilidad del esquema.Se garantiza que el resultado obtenido es compatible con el esquema del archivo de configuración y tiene valores de datos sintácticamente correctos.Sin embargo, el editor no garantiza que el archivo de configuración sea semánticamente válido.En otras palabras, el editor no garantiza que el archivo de configuración pueda funcionar con el servicio que configura.  
  
> [!CAUTION]
>  El editor no puede purgar un elemento de configuración a partir del archivo de configuración cuando ha modificado el elemento.Por ejemplo, si utiliza el editor para establecer el nombre de extremo en una cadena que no esté vacía y guardarlo, el archivo de configuración tendrá el contenido del ejemplo siguiente.  
>   
>  `<endpoint binding="basicHttpBinding" name="somename" />`  
>   
>  Si intenta quitar el nombre estableciéndolo en una cadena vacía y guardar el archivo, el archivo de configuración todavía contendrá el atributo `name`, como se muestra en el ejemplo siguiente.  
>   
>  `<endpoint binding="basicHttpBinding" name="" />`  
>   
>  Para purgar el atributo, debe modificar manualmente el elemento mediante otro editor de texto.  
>   
>  Debería tener mucho cuidado con este problema al utilizar el elemento `issueToken` del comportamiento de extremo `clientCredential`.Específicamente, el atributo `address` de su subelemento `localIssuer` no debe ser una cadena vacía.Si ha modificado el atributo `address` mediante el editor de configuración y desea quitarlo completamente, debería hacerlo utilizando una herramienta diferente del editor.De lo contrario, el atributo contiene una cadena vacía y su aplicación inicia una excepción.  
  
## Utilización del editor de configuración  
 El Editor de configuración de servicio se puede encontrar en la siguiente ubicación de instalación de Windows SDK:  
  
 C:\\Archivos de Programa\\Microsoft SDKs\\Windows\\v6.0\\Bin\\SvcConfigEditor.exe  
  
 Después de iniciar el editor de configuración de servicio, puede utilizar el menú **Archivo\/Abrir** para buscar el servicio o ensamblado que desea administrar.Puede abrir directamente los archivos de configuración, busque [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \/servicios COM \+ y abra los archivos de configuración para servicios hospedados en web.  
  
 La interfaz de usuario del editor de configuración de servicio está dividida en las áreas siguientes:  
  
-   Panel Ver árbol, que muestra los elementos de configuración en una estructura de árbol a la izquierda.Puede realizar operaciones en el árbol haciendo clic con el botón secundario en los nodos.  
  
-   Panel de tareas, que muestra las tareas comunes para los elementos vigentes en la parte inferior izquierda de la ventana.  
  
-   Panel de detalles, que muestra valores detallados del nodo de configuración seleccionado en Ver árbol a la derecha.  
  
### Abrir un archivo de configuración  
  
1.  Utilice una ventana de comandos para navegar a la ubicación de instalación de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y, a continuación, escriba `SvcConfigEditor.exe` para iniciar el editor de configuración de servicio.  
  
2.  En el menú **Archivo**, seleccione **Abrir** y haga clic en el tipo de archivo que desee administrar.  
  
3.  En el cuadro de diálogo **Abrir**, navegue al archivo concreto que desea administrar y haga doble clic en él.  
  
 El visor sigue automáticamente la ruta de acceso de combinación de configuración y crea una vista de la configuración combinada.Por ejemplo, la configuración real de un servicio no hospedado es una combinación de Machine.config y App.config.Cualquier cambio se aplica al archivo activo en SvcConfigEditor.Si desea modificar un archivo concreto en la ruta de acceso de combinación de configuración, debería abrirlo directamente.  
  
> [!NOTE]
>  El editor de configuración recarga el archivo de configuración abierto actualmente cuando éste se ha modificado fuera del editor.Cuando esto pasa, se pierden todos los cambios que no están guardados dentro del Editor de forma duradera.Si la recarga sucede constantemente, la causa más probable es un servicio que tiene acceso al archivo de configuración continuamente, por ejemplo un software antivirus que se ejecuta en segundo plano.Para resolver esto, asegúrese de que el editor de configuración es el único proceso que puede tener acceso al archivo cuando se abre.  
  
### Servicios  
 El nodo **Servicios** muestra todos los servicios asignados actualmente en el archivo de configuración.Cada subnodo en el árbol corresponde a un subelemento del elemento \<`services`\> en el archivo de configuración.  
  
 Al hacer clic en el nodo **Servicios**, puede ver o realizar tareas en la página de resumen del servicio, en el panel **Detalles**.  
  
#### Crear una nueva configuración de servicio  
 Puede crear una nueva configuración de servicio de las maneras siguientes:  
  
-   Crear a mediante un Asistente: haga clic en el vínculo **Crear un nuevo servicio…** en el panel de tareas o en la página de resumen para iniciar el Asistente.También puede hacer esto en el menú **Archivo** \-\> **Agregar nuevo elemento**.  
  
-   Crear manualmente: puede hacer clic con el botón secundario en el nodo **Servicios** y seleccionar **Nuevo servicio**.  
  
#### Crear una nueva configuración de extremo de servicio  
 Puede crear una nueva configuración de extremo de servicio de las maneras siguientes:  
  
-   Crear a mediante un Asistente: haga clic en el vínculo **Crear un nuevo extremo de servicio...** en el panel de tareas o en la página de resumen para iniciar el Asistente.También puede hacerlo en el menú **Archivo**\> \-  **Agregar nuevo elemento**.  
  
-   Crear manualmente: cuando cree un servicio, puede hacer clic con el botón secundario en el nodo **Extremos** y seleccionar “**Nuevo extremo de servicio**”.  
  
#### Editar una configuración de servicio  
  
1.  Haga clic en un nodo **Servicio**.  
  
2.  Edite la configuración en la cuadrícula de propiedades.  
  
#### Editar una configuración de extremo de servicio  
  
1.  Haga clic en un nodo **Extremo de servicio**.  
  
2.  Edite la configuración en la cuadrícula de propiedades.  
  
#### Agregar una dirección base  
  
1.  Haga clic en el nodo **Host**.  
  
2.  Haga clic en el botón **Nuevo…** en la sección **Direcciones base**.  
  
3.  Escriba el URI de la dirección base en el cuadro de diálogo.  
  
4.  Haga clic en **Aceptar**.  
  
> [!NOTE]
>  No puede editar el valor de [\<baseAddressPrefixFilters\>](../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) dentro de esta herramienta.Para agregar o modificar este elemento, debe utilizar un editor de texto o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
### Cliente  
 El nodo **Cliente** muestra todos los extremos de cliente en el archivo de configuración.Cada subnodo en el árbol corresponde a un subelemento del elemento \<`client`\> en el archivo de configuración.  
  
 Al hacer clic en el nodo **Cliente**, puede ver o realizar tareas en la **Página de resumen** del cliente, en el **Panel de detalles**.  
  
#### Crear una nueva configuración de extremo de cliente  
 Puede crear una nueva configuración de extremo de cliente de las maneras siguientes:  
  
-   Crear a mediante un Asistente: haga clic en el vínculo **Crear nuevo cliente…**, en el **Panel de tareas** situado en la parte inferior izquierda de la ventana, o en la **Página de resumen** para iniciar el asistente.También puede hacer esto en el menú **Archivo** \-\> **Agregar nuevo elemento**.El asistente le pedirá que indique la ubicación de la configuración de servicio, a partir de la cual se genera la configuración del cliente.A continuación podrá elegir el extremo de servicio con el que conectarse.  
  
-   Crear manualmente: haga clic con el botón secundario en el nodo **Extremos**, en **Cliente**, y elija **Nuevo extremo de cliente**.  
  
#### Editar una configuración de extremo de cliente  
  
1.  Haga clic en un nodo **Extremo de cliente**.  
  
2.  Edite la configuración en la cuadrícula de propiedades.  
  
### Extremo estándar  
 Los extremos estándar son extremos especializados que tienen uno o más aspectos de la dirección, contrato y conjunto obligatorio definidos en los valores predeterminados.  
  
 Esas configuraciones están almacenadas en el nodo **Extremo estándar**.El nodo **Extremo estándar** muestra todos los valores de extremo estándar en el archivo de configuración.Cada subnodo en el árbol corresponde a un subelemento del elemento `<standardEndpoints>` en el archivo de configuración.  
  
 Al hacer clic en el nodo **Extremo estándar**, puede ver o realizar tareas en la **Página de resumen** de extremo estándar, en el **Panel de detalles**.  
  
#### Crear una nueva configuración de extremo estándar  
 Puede crear una nueva configuración de extremo estándar de las maneras siguientes:  
  
-   Haga clic con el botón secundario en el nodo **Extremo estándar** y seleccione **Configuración de un nuevo extremo estándar…**. Seleccione el tipo de enlace en el cuadro de diálogo y haga clic en **Aceptar**.  
  
-   Seleccione el nodo **Extremo estándar** y haga clic en **Configuración de un nuevo extremo estándar** en el **Panel de tareas** de la parte inferior izquierda de la ventana.  
  
 El cuadro de diálogo **Crear un nuevo extremo estándar** muestra y enumera todos los tipos de extremo estándar registrados.  
  
#### Ver y editar una configuración de extremo estándar  
 Puede abrir una configuración de extremo estándar para verla y editarla de las siguientes maneras:  
  
-   Haga clic para expandir el nodo **Extremo estándar** y haga clic en el subnodo del extremo respectivo.  
  
-   Haga clic en el nodo **Extremo estándar** y haga clic en el extremo respectivo en el Panel de detalles.  
  
 Los atributos para el extremo se muestran en el panel derecho para edición.  
  
#### Eliminar una configuración de extremo estándar  
 Puede eliminar una configuración de extremo estándar de las maneras siguientes:  
  
-   Haga clic para expandir el nodo **Extremo estándar** y haga clic con el botón secundario en el subnodo del extremo respectivo.Utilice el contexto comando **Eliminar la configuración de un extremo estándar** para eliminar el extremo.  
  
-   Haga clic en el nodo **Extremo estándar**.En el panel **Tarea**, haga clic en **Eliminar la configuración de un extremo estándar**.  
  
 Si el extremo estándar se está usando, se muestra un mensaje de advertencia al intentar eliminarlo: **El extremo estándar está en uso. Si lo elimina ahora, asegúrese de eliminar todas sus referencias en otras partes de la configuración \(por ejemplo, en el extremo de servicio o extremo del cliente\). De lo contrario, la configuración no será válida y no se puede abrir la próxima vez. ¿Está seguro de que desea eliminar el extremo estándar?".**  
  
### Enlace  
 Las configuraciones de enlace se usan para configurar enlaces en extremos.Esas configuraciones están almacenadas en el nodo **Enlace**.Los extremos hacen referencia a las configuraciones de enlace por nombre y varios extremos pueden hacer referencia a una configuración de enlace única.  
  
 El nodo **Enlaces** muestra todos los valores de enlace en el archivo de configuración.Cada subnodo en el árbol corresponde a un subelemento del elemento \<`bindings`\> en el archivo de configuración.  
  
 Al hacer clic en el nodo **Enlaces**, puede ver o realizar tareas en la **Página de resumen** de enlaces, en el **Panel de detalles**.  
  
#### Crear una nueva configuración de enlace  
 Puede crear una nueva configuración de enlace de las maneras siguientes.  
  
-   Haga clic con el botón secundario en el nodo **Enlaces** y seleccione **Nueva configuración de enlace**. Seleccione el tipo de enlace en el cuadro de diálogo y haga clic en **Aceptar**.  
  
-   Seleccione el nodo **Enlaces** y haga clic en **Nueva configuración de enlace** en el **Panel de tareas** de la parte inferior izquierda de la ventana.  
  
-   En el servicio o en la página de resumen del cliente, haga clic en **Hacer clic para crear** en el campo **Configuración de enlace** con el fin de crear una configuración de enlace para el extremo correspondiente.  
  
#### Agregar extensiones de elemento de enlace a un enlace personalizado  
  
1.  Seleccione el enlace al que desea agregar un elemento de extensión.  
  
2.  Haga clic en **Agregar**.  
  
3.  De la lista de extensiones disponibles, seleccione la extensión de elemento de enlace que desea agregar.Para seleccionar varios elementos, presione simultáneamente la tecla CTRL.  
  
4.  Haga clic en **Agregar**.  
  
#### Ajustar la posición de la extensión en un enlace personalizado  
 Un enlace personalizado es una colección de elementos de enlace que forman una pila.Cada elemento de enlace en la pila tiene su propia configuración.El orden de las extensiones de elemento de enlace en un enlace personalizado indica sus posiciones en la pila.Se aplican primero los elementos de la parte superior de la pila.Para cambiar el orden:  
  
1.  Seleccione el nodo de enlace personalizado.  
  
2.  Seleccione un elemento de extensión de enlace en la sección **Posición de extensión de elemento de enlace**.  
  
3.  Utilice los botones **Arriba** o **Abajo** en el lado izquierdo de la lista para cambiar la posición del elemento seleccionado.  
  
#### Editar la configuración de extensiones de elemento de enlace en un enlace personalizado  
  
1.  Seleccione el nodo de enlace en el árbol.  
  
2.  Seleccione el enlace personalizado que contiene el elemento que desea editar.  
  
3.  Seleccione la extensión de elemento de enlace que desea editar.La configuración del elemento aparece en el panel derecho, donde se puede editar.  
  
### Diagnósticos  
 El nodo **Diagnósticos** muestra toda la configuración de diagnóstico en el archivo de configuración.Le permite activar o desactivar contadores de rendimiento, habilitar o deshabilitar el Instrumental de administración de Windows \(WMI\) y configurar la traza [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y el registro de mensajes [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].La configuración en el nodo **Diagnósticos** corresponde a la sección \<`system.diagnostics`\> y a la sección `<diagnostics>` en `<system.serviceModel>`, en el archivo de configuración.  
  
 Al hacer clic en el nodo **Diagnósticos**, puede ver o realizar tareas en la **Página de resumen** de diagnósticos, en el **Panel de detalles**.  
  
#### Configurar contadores de rendimiento y WMI  
  
1.  Haga clic en el nodo **Diagnósticos**.  
  
2.  Haga clic en **Alternar contadores de rendimiento**.El contador de rendimiento tiene tres estados: Apagado \(valor predeterminado\), ServiceOnly y todos.Al hacer clic en el vínculo, se alterna el valor entre estos tres estados.  
  
#### Configurar proveedor de WMI  
  
1.  Haga clic en el nodo **Diagnósticos**.  
  
2.  Para habilitar un proveedor de WMI, haga clic en el vínculo **Habilitar proveedor de WMI**.  
  
#### Habilitar la traza WCF  
 Puede crear un archivo de seguimiento [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con propiedades estándar o configurar un archivo de seguimiento personalizado.  
  
1.  Haga clic en el nodo **Diagnósticos**.  
  
2.  Haga clic en **Habilitar traza**.  
  
3.  Haga clic en el vínculo **Nivel de seguimiento** para ajustar el nivel de seguimiento.Hay seis niveles de seguimiento: apagado, crítico, error, advertencia, información y detallado.Las opciones **Traza de la actividad** y **Propagar actividad** le permiten usar la característica de traza de la actividad [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
4.  Haga clic en el nombre del agente de escucha de traza para especificar el archivo y las opciones de seguimiento.  
  
#### Habilitar el registro del WCF  
 Puede crear un archivo de seguimiento [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con propiedades estándar o configurar un archivo de seguimiento personalizado.  
  
1.  Haga clic en el nodo **Diagnósticos**.  
  
2.  Haga clic en **Habilitar registro de mensajes**.  
  
3.  Haga clic en el vínculo **Nivel de registro** para ajustar el nivel del registro.Hay tres niveles de registro: incorrecto, servicio y transporte.  
  
4.  Haga clic en el nombre de agente de escucha para especificar el archivo y las opciones de registro.  
  
> [!NOTE]
>  Si desea vaciar los registros de mensajes y seguimiento de manera automática cuando se cierra su aplicación, habilite la opción **Vaciado automático**.  
  
 La **Página de resumen** de **diagnósticos** le permite realizar las tareas más comunes de configuración de diagnósticos.Sin embargo, si desea editar manualmente la configuración de escuchas y orígenes, debe expandir el nodo **Diagnósticos** y editar la configuración en los nodos **Registro de mensajes**, **Escuchas** y **Orígenes**.  
  
#### Habilitar traza personalizada o registro de mensajes de WCF  
  
1.  Haga clic en el nodo **Diagnósticos** y expándalo.  
  
2.  Haga clic con el botón secundario en el nodo **Escuchas** y seleccione **Nueva escucha**.  
  
3.  Escriba el nombre del archivo de seguimiento en el campo **InitData**.Puede hacer clic en el botón "..." para ir a una ruta de acceso.  
  
4.  Al hacer clic en la línea **TypeName** aparece un botón "...".Haga clic en este botón para abrir el **Explorador de tipos de escucha de seguimiento**, que puede usar para buscar las escuchas de seguimiento preconfiguradas que ya estén instaladas.  
  
5.  Tenga en cuenta la sección **Origen**.Haga clic en **Agregar** en esta sección para abrir un cuadro de diálogo con un menú desplegable, que contiene una lista de orígenes de traza disponibles.Seleccione un origen de traza y haga clic en **Aceptar**.  
  
6.  Para editar los valores del registro de mensajes, haga clic en el nodo **Registro de mensajes**.Puede editar los valores en la cuadrícula de propiedad.  
  
### Avanzado  
  
#### Comportamientos  
 El nodo **Comportamientos** muestra los comportamientos que se definen actualmente en el archivo de configuración.  
  
 Las configuraciones de comportamiento se utilizan para configurar comportamientos de extremos y servicios.Tal configuración está almacenada en el nodo **Opciones avanzadas**, bajo **Comportamientos de servicio** y **Comportamientos de extremo**.Los servicios utilizan comportamientos de servicios; pero los extremos utilizan comportamientos de extremo.  
  
 Los comportamientos son una colección de elementos de extensión que forman una pila.Se aplica primero el elemento en la parte superior de la pila.Cada elemento de extensión puede tener su propia configuración.  
  
##### Crear una nueva configuración de comportamiento  
 Puede crear una nueva configuración de comportamiento de dos maneras:  
  
-   Haga clic con el botón secundario en uno de los nodos de comportamiento y seleccione “**Nueva configuración de comportamiento**...  
  
-   Seleccione uno de los nodos de comportamiento y haga clic en **Configuración de un nuevo extremo estándar** en el **Panel de tareas** de la parte inferior izquierda de la ventana.  
  
##### Agregar las extensiones de elemento de comportamiento a un comportamiento  
  
1.  Seleccione uno de los nodos de comportamiento.  
  
2.  Seleccione el comportamiento que desee editar.  
  
3.  Haga clic en **Agregar**.  
  
4.  De la lista de extensiones disponibles, seleccione la extensión de elemento de comportamiento que desea agregar.  
  
5.  Haga clic en **Agregar**.  
  
##### Ajustar la posición de la extensión en un comportamiento  
 Los comportamientos son colecciones de elementos que forman una pila.Cada elemento de la pila tiene su propia configuración.El orden de las extensiones de elemento de comportamiento en un comportamiento indica sus posiciones en la pila.Se aplican primero los elementos de la parte superior de la pila.Para cambiar el orden:  
  
1.  Seleccione uno de los nodos de comportamiento.  
  
2.  Seleccione el comportamiento que desee editar.  
  
3.  Seleccione un elemento de extensión de comportamiento en la sección **Posición de extensión de elemento de comportamiento**.  
  
4.  Utilice los botones **Arriba** o **Abajo** en el lado izquierdo de la lista para cambiar la posición del elemento seleccionado.  
  
##### Editar la configuración de extensiones de elemento de comportamiento  
  
1.  Seleccione uno de los nodos de comportamiento del árbol.  
  
2.  Seleccione el comportamiento que contiene el elemento que desea editar.  
  
3.  Seleccione la extensión de elemento de comportamiento que desea editar.La configuración del elemento aparece en el panel derecho, donde se puede editar.  
  
#### ProtocolMapping  
 Esta sección permite establecer los tipos de enlaces predeterminados para los distintos protocolos como http, tcp, MSMQ o net.pipe mediante la asignación entre los esquemas de direcciones de protocolo y los posibles enlaces.También puede agregar nuevas asignaciones a otros protocolos.  
  
#### Extensiones  
 Las nuevas extensiones de enlace, extensiones de elemento de enlace y extensiones de extremo estándar se pueden registrar para su uso en la configuración [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Las extensiones son pares de nombre\/tipo.El nombre define el nombre de la extensión en la configuración, mientras que el tipo implementa la extensión.Hay cuatro tipos de extensiones:  
  
-   Las extensiones de enlace definen un tipo entero de enlace.Ejemplo: `basicHttpBinding`.  
  
-   Las extensiones de elemento de enlace definen un elemento de un enlace.Ejemplo: `textMessageEncoding`.  
  
-   Las extensiones de extremo estándar definen un extremo estándar completo.Ejemplo: `discoveryEndpoint`.  
  
-   Las extensiones de elemento de comportamiento definen un elemento de un comportamiento.Ejemplo: `clientVia`.  
  
 Las extensiones registradas en configuración se pueden utilizar como cualquier otro componente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] del mismo tipo.  
  
##### Agregar una nueva extensión  
 Seleccione uno de los nodos de extensión en los nodos avanzados:  
  
1.  Haga clic en **Nuevo**.  
  
2.  Escriba un nombre y tipo.  
  
3.  Haga clic en **Aceptar**.  
  
4.  La extensión aparece ahora en el lugar adecuado en el editor.Por ejemplo, si agrega una extensión de elemento de comportamiento, aparece en la lista de extensiones disponibles.  
  
#### Entorno de hospedaje  
 Esta sección permite definir la configuración de creación de instancias para el entorno de hospedaje de servicio.  
  
### Crear un archivo de configuración mediante el asistente  
 Una forma de crear un archivo de configuración nuevo es utilizar el Asistente para nuevo elemento de servicio.El Asistente busca los tipos de servicio instalados y otros elementos compatibles con [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en el equipo, incluidos directorios COM\+ y directorios virtuales hospedados en web, y los carga para que la creación de la configuración sea más simple.  
  
#### Crear un archivo de configuración  
  
1.  Utilice una ventana de comandos para navegar a la ubicación de instalación de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y, a continuación, escriba `SvcConfigEditor.exe` para iniciar el editor de configuración de servicio.  
  
2.  En el menú **Archivo**, seleccione **Abrir** y haga clic en **Ejecutable**, **Servicio COM\+**o **Servicio WebHosted**, según el tipo de archivo de configuración que desee crear.  
  
3.  En el cuadro de diálogo **Abrir**, navegue al archivo concreto para el que desea crear un archivo de configuración y haga doble clic en él.  
  
4.  En el menú **Archivo**, señale **Agregar nuevo elemento** y haga clic en **Servicio**.Se abre el Asistente para nuevo elemento de servicio.  
  
5.  Siga los pasos en el asistente para crear el nuevo servicio.  
  
> [!NOTE]
>  Si desea utilizar NetPeerTcpBinding del archivo de configuración generado por el asistente, tiene que agregar manualmente un elemento de configuración de enlace y modificar el atributo `mode` de su elemento `security` a "Ninguno".  
  
## Configurar COM\+  
 El editor de configuración de servicio le permite crear un nuevo archivo de configuración para una aplicación COM\+ existente o editar una configuración COM\+ existente.El nodo **Contrato COM** solo es visible cuando la sección \<`comContract`\> está en el archivo de configuración.  
  
### Crear una nueva configuración de COM\+  
 Antes de crear una nueva configuración de COM\+, asegúrese de que su aplicación COM\+ esté instalada en servicios de componente y registrada en la caché global de ensamblados \(GAC\).  
  
1.  Seleccione el menú **Archivo** \-\> **Integrar** \-\> **Aplicación COM\+.** Esta operación cierra el archivo abierto actual.Si hay datos no guardados en el archivo actual, aparece el cuadro de diálogo Guardar.Se inicia el **Asistente de integración de COM\+** a continuación.  
  
2.  En la primera página, seleccione la aplicación COM\+ del árbol.Si no encuentra su aplicación COM\+ en el árbol, compruebe que está instalada en los servicios de componente y registrada en la caché global de ensamblados \(GAC\).  
  
3.  En la página siguiente, seleccione qué método\(s\) quiere exponer como servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Todos los métodos compatibles en la aplicación COM\+ se muestran y se seleccionan de forma predeterminada.  
  
4.  Elija un método de hospedaje.  
  
5.  Configure otros valores según las guías en el Asistente.  
  
6.  El editor de configuración de servicio utiliza en segundo plano ComSvcConfig.exe para generar un archivo de configuración.Después de este paso, puede ver un resumen y salir del Asistente.Se abre el archivo de configuración generado para que pueda editarlo directamente.  
  
### Editar una configuración COM\+ existente  
  
1.  Seleccione el menú **Archivo** \-\>**Abrir** \-\> **Servicio COM\+**.  
  
2.  Seleccione el servicio COM\+ que desee editar en la lista.  
  
3.  Edite la configuración en el nodo **Contratos COM**.  
  
    > [!NOTE]
    >  También puede abrir directamente un archivo de configuración que contenga contratos COM\+ y modificarlo.  
  
## Seguridad  
 No se garantiza que un archivo de configuración de servicio generado por el editor de configuración sea seguro.Vea la documentación [Seguridad](../../../docs/framework/wcf/feature-details/security.md) para averiguar cómo proteger sus servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Además, el editor de configuración solo se puede utilizar para leer y escribir elementos de configuración [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] válidos.La herramienta omite los elementos conformes a esquema definidos por el usuario.Tampoco intenta quitar estos elementos del archivo de configuración ni determinar sus efectos en los elementos [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] conocidos.Es la responsabilidad del usuario determinar si estos elementos suponen una amenaza para la aplicación o el sistema.