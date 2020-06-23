---
title: Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)
description: Use el visor de seguimiento de servicio para combinar, ver y filtrar los mensajes de seguimiento en el registro para que pueda diagnosticar, reparar y comprobar los problemas del servicio WCF.
ms.date: 03/30/2017
ms.assetid: 9027efd3-df8d-47ed-8bcd-f53d55ed803c
ms.openlocfilehash: 0ad6094965291a965346522688a8334abbd4e6b3
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244574"
---
# <a name="service-trace-viewer-tool-svctraceviewerexe"></a>Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)

La herramienta del visor de seguimiento del servicio Windows Communication Foundation (WCF) le ayuda a analizar los seguimientos de diagnóstico generados por WCF. El visor de seguimiento de servicio proporciona una manera fácil de combinar, ver y filtrar los mensajes de seguimiento en el registro para que pueda diagnosticar, reparar y comprobar los problemas del servicio WCF.

## <a name="configuring-tracing"></a>Configurar seguimiento

El seguimiento de diagnóstico le proporciona información que muestra lo que está pasando a lo largo de la operación de su aplicación. Como su propio nombre indica, también puede seguir las operaciones desde el origen hasta el destino y en los puntos intermedios.

Puede configurar el seguimiento mediante el archivo de configuración de la aplicación, ya sea Web.config para las aplicaciones hospedadas en web o *appname*. config para las aplicaciones autohospedadas. Este es un ejemplo:

```xml
<system.diagnostics>
    <trace autoflush="true" />
    <sources>
            <source name="System.ServiceModel"
                    switchValue="Information, ActivityTracing"
                    propagateActivity="true">
            <listeners>
               <add name="sdt"
                   type="System.Diagnostics.XmlWriterTraceListener"
                   initializeData= "SdrConfigExample.e2e" />
            </listeners>
         </source>
    </sources>
</system.diagnostics>
```

En este ejemplo, se especifican el nombre y el tipo del agente de escucha de traza. El agente de escucha se denomina `sdt` y se agrega como tipo el agente de escucha de traza estándar de .NET Framework (System.Diagnostics.XmlWriterTraceListener). El `initializeData` atributo se usa para establecer el nombre del archivo de registro para que el agente de escucha sea `SdrConfigExample.e2e` . Para el archivo de registro, puede sustituir una ruta de acceso completa para un nombre de archivo simple.

El ejemplo crea un archivo en el directorio raíz denominado SdrConfigExample.e2e. Cuando use el visor de seguimiento para abrir el archivo tal y como se describe en la sección "abrir y ver archivos de seguimiento de WCF", puede ver todos los mensajes que se han enviado.

La configuración de `switchValue` controla el nivel de traza. En la siguiente tabla se describen los niveles de seguimiento disponibles.

|Nivel de seguimiento|Descripción|
|-----------------|-----------------|
|Crítica|-Registra las entradas de error y de registro de eventos, y realiza un seguimiento de la información de correlación. A continuación se muestran algunos ejemplos de cuándo se puede utilizar el nivel Crítico:<br />-El AppDomain dejó de funcionar debido a una excepción no controlada.<br />-La aplicación no se inicia.<br />: El mensaje que causó el error se originó en el proceso MyApp.exe.|
|Error|-Registra todas las excepciones. Puede utilizar el nivel Error en las situaciones siguientes:<br />-El código se bloqueó debido a una excepción de conversión no válida.<br />-Una excepción "no se pudo crear el punto de conexión" está provocando un error en la aplicación al iniciarse.|
|Advertencia|-Existe una condición que puede producir posteriormente un error o un error crítico. Puede utilizar este nivel en las situaciones siguientes:<br />-La aplicación está recibiendo más solicitudes de las que permite la configuración de limitación.<br />-La cola receptora está en el 98 por ciento de su capacidad configurada.|
|Información|-Se generan mensajes útiles para supervisar y diagnosticar el estado del sistema, medir el rendimiento o la generación de perfiles. Puede utilizar esa información para el diseño de la capacidad y la gestión del rendimiento. Puede utilizar este nivel en las situaciones siguientes:<br />-Se produjo un error después de que el mensaje alcanzase el AppDomain y estaba deserializado.<br />-Se produjo un error mientras se creaba el enlace HTTP.|
|Verbose|-Seguimiento de nivel de depuración para el código de usuario y el servicio. Establezca este nivel cuando:<br />: No está seguro de qué método del código se llamó cuando se produjo el error.<br />: Tiene configurado un extremo incorrecto y el servicio no se pudo iniciar porque la entrada en el almacén de reserva está bloqueada.|
|ActivityTracing|Transmitir eventos entre actividades de procesamiento y componentes.<br /><br /> Este nivel permite a los administradores y programadores poner en correlación las aplicaciones en el mismo dominio de aplicación.<br /><br /> -Seguimientos de los límites de actividad: iniciar/detener.<br />: Realiza un seguimiento de las transferencias.|

 Puede utilizar `add` para especificar el nombre y tipo de agente de escucha de seguimiento que desea utilizar. En la configuración del ejemplo, el agente de escucha se denomina `sdt` y se agrega como tipo el agente de escucha de traza de .NET Framework estándar (`System.Diagnostics.XmlWriterTraceListener`). Utilice `initializeData` para establecer el nombre del archivo de registro para ese agente de escucha. Además, puede sustituir un nombre de archivo simple por una ruta de acceso completa.

A partir de .NET Framework 4,8, los controles ComboBox en algunos temas de contraste alto se muestran en el color correcto. Puede deshabilitar este cambio quitando la siguiente configuración del archivo de *svcTraceViewer.exe.config* :

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

## <a name="using-the-service-trace-viewer-tool"></a>Utilizar la herramienta de visor de seguimiento de servicio

### <a name="opening-and-viewing-wcf-trace-files"></a>Abrir y ver los archivos de seguimiento de WCF

El visor de seguimiento de servicio admite tres tipos de archivo:

- Archivo de seguimiento de WCF (. svcLog)

- Archivo de seguimiento de eventos (.etl)

- Archivo de seguimiento carmesí

 El visor de seguimiento de servicio le permite abrir cualquier archivo de seguimiento compatible, agregar e integrar archivos de seguimiento adicionales o abrir y fusionar mediante combinación simultáneamente un grupo de archivos de seguimiento.

##### <a name="to-open-a-trace-file"></a>Para abrir un archivo de seguimiento

1. Inicie el visor de seguimiento de servicio mediante una ventana de comandos para navegar a la ubicación de instalación de WCF (C:\Archivos de Programa\microsoft SDKs\Windows\v6.0\Bin) y, a continuación, escriba `SvcTraceViewer.exe` .

> [!NOTE]
> La herramienta del visor de seguimiento de servicio puede asociar dos tipos de archivo: .svclog y .stvproj. Puede utilizar dos parámetros en línea de comandos para registrar y eliminar del registro las extensiones de archivo.
>
> /register: registrar la asociación de las extensiones de archivo “.svclog” y “.stvproj” con SvcTraceViewer.exe
>
> /unregister: eliminar del registro la asociación de las extensiones de archivo “.svclog” y “.stvproj” con SvcTraceViewer.exe

1. Cuando se inicie el visor de seguimiento de servicio, haga clic en **archivo** y seleccione **abrir**. Navegue a la ubicación donde se almacenan sus archivos de seguimiento.

2. Haga doble clic en el archivo de seguimiento que desea abrir.

    > [!NOTE]
    > Presione MAYÚS mientras hace clic en varios archivos de seguimiento para seleccionarlos y abrirlos de forma simultánea. El visor de seguimiento de servicio combina el contenido de todos los archivos y los muestra en una vista. Por ejemplo, puede abrir archivos de seguimiento tanto de cliente como de servicio. Esto es útil cuando ha habilitado en la configuración el registro de mensajes y la propagación de la actividad. De esta manera, puede examinar el intercambio de mensajes entre cliente y servicio. También puede arrastrar varios archivos al visor o utilizar la pestaña **proyecto** . Consulte la sección Administración del proyecto para obtener más detalles.

3. Para agregar archivos de seguimiento adicionales a la colección que está abierta, haga clic en **archivo** y, a continuación, seleccione **Agregar**. En la ventana que se abre, navegue a la ubicación de los archivos de seguimiento y haga doble clic en el archivo que desea agregar.

> [!CAUTION]
> No se recomienda cargar un archivo de seguimiento mayor de 200MB. Si intenta cargar un archivo mayor que ese límite, el proceso de carga puede tardar mucho tiempo, dependiendo de su recurso informático. Puede que la herramienta del visor de seguimiento de servicio no responda durante mucho tiempo o que agote la memoria de su equipo. Se recomienda que configure carga parcial para evitarlo. Para obtener más información sobre cómo hacerlo, vea la sección “Cargar archivos de seguimiento grandes”.

#### <a name="event-tracing-and-crimson-tracing"></a>Traza de eventos y traza carmesí

El formato nativo del visor es el formato de seguimiento de actividad que emite WCF. Las trazas emitidas en un formato diferente se deben convertir antes de que el visor las muestre. Actualmente, además del formato de traza de la actividad, el visor admite traza de eventos y traza carmesí.

Al abrir un archivo que no contiene seguimientos de actividad, el visor intenta convertir el archivo. Debe especificar el nombre y la ubicación del archivo que contendrá los datos de seguimiento convertidos. Una vez convertidos los datos, el visor muestra el contenido del nuevo archivo.

> [!NOTE]
> La conversión requiere espacio en disco para almacenar la información de seguimiento convertida. Antes de iniciar una conversión, asegúrese de tener suficiente espacio en disco para almacenar los datos. De lo contrario, se produce un error en la conversión.

### <a name="managing-projects"></a>Administrar proyectos

El visor admite proyectos para facilitar la vista de varios archivos de seguimiento. Por ejemplo, si tiene un archivo de seguimiento de cliente y un archivo de seguimiento de servicio, puede agregarlos a un proyecto. A continuación, cada vez que abra el proyecto, se cargan todos los archivos de seguimiento en el proyecto de manera simultánea.

Hay dos maneras de administrar los proyectos:

- En el menú **archivo** , puede abrir, guardar y cerrar proyectos.

- En la pestaña **proyecto** , puede Agregar archivos a un proyecto.

### <a name="viewing-wcf-traces"></a>Ver seguimiento de WCF

WCF emite seguimientos con el formato de traza de la actividad. En el modelo de seguimiento de actividad, los seguimientos individuales están agrupados en actividades según su propósito. El flujo de control lógico se transfiere entre las actividades. Por ejemplo, durante el tiempo que dura una aplicación, aparecen y desaparecen muchas "actividades de envío de mensaje". Para obtener más información sobre cómo ver los seguimientos y las actividades, así como la interfaz de usuario del visor de seguimiento de servicio, vea [usar el visor de seguimiento de servicios para ver seguimientos correlacionados y solución de problemas](./diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).

#### <a name="switching-to-different-views"></a>Alternar vistas diferentes

El visor de seguimiento de servicio proporciona estas vistas diferentes. Se muestran como pestañas en el panel izquierdo del visor y también se puede tener acceso a ellas desde el menú **Ver** .

- Vista de actividad

- Project View

- Vista de mensaje

- Vista de gráfico

##### <a name="activity-view"></a>Vista de actividad

Una vez abiertos los archivos de seguimiento, puede ver los seguimientos agrupados en actividades y mostrarlos en la vista de **actividad** en el panel izquierdo.

La vista de **actividad** muestra los nombres de actividad, el número de seguimientos de la actividad, la duración de la hora de inicio y la hora de finalización.

Haciendo clic en cualquiera de las actividades de la lista, los seguimientos en esta actividad se muestran en el panel de seguimiento a la derecha. Puede seleccionar a continuación un seguimiento para ver sus detalles.

Puede seleccionar varias actividades presionando la tecla **Ctrl** o **MAYÚS** y haciendo clic en las actividades deseadas. El panel de seguimiento muestra todos los seguimientos de las actividades seleccionadas.

Puede hacer doble clic en una actividad para mostrarla en la vista **gráfico** . La manera alternativa es seleccionar una actividad y cambiar a la vista de **gráfico** .

> [!NOTE]
> La actividad "000000000000" es una actividad especial que no se puede mostrar en la vista del gráfico. Dado que las otras actividades se vinculan a ella, mostrar esta actividad tiene un impacto importante en el rendimiento.

Puede hacer clic en el título de la columna para ordenar la lista de actividades. Las actividades que contienen seguimientos de advertencia tienen un fondo amarillo y aquéllas que contienen seguimientos de error tienen un fondo rojo.

Hay diferentes tipos de actividades, y cada tipo corresponde a un icono en el lado izquierdo de cada actividad. Puede consultar la sección Introducción a los iconos de seguimiento para conocer su significado.

##### <a name="project-view"></a>Project View

Esta vista le permite administrar los archivos de seguimiento en el proyecto actual. Para obtener información más detallada, consulte la sección Administrar proyecto.

##### <a name="message-view"></a>Vista de mensaje

Esta vista permite ver todos los seguimientos del registro de mensajes, como Action, Date/Time, Process, Acivity y from/to, y navegar a los detalles del seguimiento de registro de mensajes asociado. Puede agrupar los seguimientos del registro de mensajes por límite de actividad, proceso o subproceso, o enviar & recibir para facilitar la navegación del flujo de mensajes.

##### <a name="graph-view"></a>Vista de gráfico

Esta vista muestra los datos de seguimiento de una actividad determinada en formato de gráfico. Esta opción de gráficos le permite ver la ejecución paso a paso de eventos y las relaciones mutuas entre varias actividades cuando los datos se mueven entre ellas.

Para cambiar a la vista de **gráfico** , seleccione una actividad en la vista de **actividad** y haga clic en la pestaña **actividad** o en un seguimiento de registro de mensajes en la vista de **mensajes** . Si se cargan varios archivos de seguimiento y la actividad implica seguimientos de más de un archivo, todos los seguimientos pertinentes aparecen en la vista de Gráfico. Al hacer doble clic en las actividades y en los seguimientos del registro de mensajes también se lleva a la vista **gráfico** .

En la vista de **gráfico** , cada columna vertical representa una actividad y cada bloque de la columna representa un seguimiento. Las actividades se agrupan por proceso (o subproceso). Las flechas pequeñas entre las actividades representan las transferencias. Las flechas grandes entre los procesos representan el intercambio de mensajes. La actividad seleccionada siempre aparece en amarillo.

###### <a name="selecting-traces-in-the-graph"></a>Seleccionar seguimientos en el gráfico

1. Haga clic en un bloque del gráfico.

2. Utilice las teclas arriba y abajo para seleccionar los seguimientos adyacentes.

3. Puede ver la información del seguimiento en el panel de seguimiento y en el panel detalle.

###### <a name="expanding-or-collapsing-activity-transfers"></a>Expandir o contraer transferencias de la actividad

Puede expandir las transferencias de la actividad cuando la actividad seleccionada transfiere a otra actividad. Le permite seguir las transferencias.

Para expandir o contraer transferencias de la actividad,

1. Busque el seguimiento de transferencia con un signo "+" a la izquierda del icono de transferencia.

2. Haga clic en "+" o presione **Ctrl** y "+" con el teclado.

3. La actividad siguiente aparece en el gráfico.

4. Aparece un "-" a la izquierda del icono de transferencia. Haga clic en el signo "-" o presione Ctrl y "-", la transferencia de la actividad se contrae.

> [!NOTE]
> Cuando una actividad tiene varias transferencias y expande una de ellas, se muestran las actividades que llevan a la nueva actividad desde la actividad raíz. Estas nuevas actividades se muestran en formato contraído. Si desea ver los detalles de estas actividades, expándalas verticalmente haciendo clic en el icono de expandir, en el encabezado del gráfico.

###### <a name="expanding-or-collapsing-activities-vertically"></a>Expandir o contraer verticalmente las actividades

El visor contrae las actividades para así ocultar detalles innecesarios en el gráfico de la actividad. En una actividad contraída no se muestran los seguimientos individuales. Sólo aparecen las transferencias de seguimiento. Si desea ver todas las trazas en una actividad, expanda verticalmente la actividad haciendo clic en el símbolo de expansión de la actividad situado en el encabezado del gráfico.

Para expandir o contraer verticalmente las actividades,

1. Haga clic en el icono "+" en el encabezado de la actividad para expandir la actividad verticalmente.

2. Tenga en cuenta que todas las trazas se muestran en el gráfico.

3. Haga clic en el icono "-" en el encabezado de la actividad para contraer la actividad verticalmente.

4. Tenga en cuenta que sólo se muestran en la actividad las transferencias importantes, registros de mensajes y seguimientos de advertencia y de excepción.

###### <a name="options"></a>Opciones

Puede seleccionar dos opciones en el menú de **Opciones** de la vista gráfico.

- Mostrar seguimientos de límite de la actividad que, cuando se desactiva, omite los seguimientos del límite de la actividad en el gráfico.

- Mostrar seguimientos detallados sin mensaje que, cuando se desactiva, omite todos los seguimientos de nivel detallados, excepto los seguimientos de mensajes. En la mayoría de los casos, los seguimientos de nivel detallados son menos importantes para el análisis. Esta opción es útil cuando no desea analizar los seguimientos de nivel detallados y sólo desea centrarse en seguimientos más importantes.

###### <a name="layout-mode"></a>Modo de diseño

El visor tiene dos modos de diseño: **proceso** y **subproceso**. Esta configuración define la unidad más grande de organización. El modo de diseño predeterminado es **proceso**, lo que significa que las actividades se agrupan por procesos en el gráfico.

###### <a name="execution-list"></a>Lista de ejecución

Puede seleccionar qué proceso o subproceso de este menú desplegable se va a mostrar en el gráfico. Por ejemplo, si tiene abiertos los archivos de seguimiento de dos clientes (A y B) y un servicio, y sólo desea mostrar el servicio y el cliente A en el gráfico, puede anular la selección del cliente B en la lista.

#### <a name="viewing-trace-details"></a>Ver detalles del seguimiento

Para ver un detalle del seguimiento, seleccione un seguimiento en el panel de traza. Los detalles se muestran en el panel detalle.

##### <a name="trace-pane"></a>Panel de traza

El panel superior derecho en el visor de seguimiento de servicio es el panel de traza. Contiene una lista de todos los seguimientos en la actividad seleccionada con información adicional, como nivel de seguimiento, id. de subproceso y nombre del proceso.

Puede copiar el XML sin formato del seguimiento en el portapapeles haciendo clic con el botón secundario en un seguimiento y seleccionando **copiar seguimiento en portapapeles**.

##### <a name="detail-pane"></a>Panel de detalles

El panel inferior izquierdo en el visor de seguimiento de servicio es el Panel de detalles. Tiene tres pestañas para ver los detalles de seguimiento.

La vista **con formato** muestra la información de una manera más organizada. Contiene una lista de todos los elementos XML conocidos en tablas y árboles, por lo que será más fácil leer y entender la información.

La vista **XML** muestra el XML correspondiente al seguimiento seleccionado. Permite resaltar y colorear la sintaxis. Cuando se usa **Buscar** para buscar cadenas, se resaltan los resultados de la búsqueda.

La vista de **mensajes** muestra la parte de mensaje del XML en los seguimientos del registro de mensajes. No se puede ver si selecciona un seguimiento sin mensaje.

### <a name="filtering-wcf-traces"></a>Filtrar los seguimientos de WCF

Para facilitar el análisis de seguimientos, puede filtrarlos de las maneras siguientes:

- La barra de herramientas de filtro proporciona el acceso a los filtros predefinidos y personalizados. Se puede habilitar a través del menú **Ver** .

- El filtro predefinido del visor se puede usar para filtrar selectivamente partes de los seguimientos de WCF. Se establece de forma predeterminada que todos los seguimientos de infraestructura puedan pasar. La configuración de este filtro se define en el submenú **Opciones de filtro** , en el menú **Ver** .

- Los filtros del XPath personalizados les dan a los usuarios el control completo sobre cómo filtrar. Pueden definirse en el **filtro personalizado** en el menú **Ver** .

Sólo se muestran los seguimientos que atraviesan todos los filtros.

#### <a name="using-the-filter-toolbar"></a>Utilizar la barra de herramientas del filtro

La barra de herramientas del filtro aparece en la parte superior de la herramienta. Si no está presente, puede activarlo en el menú **Ver** . La barra tiene tres componentes:

- Buscar: **busca** define el asunto que se buscará en la operación de filtro. Por ejemplo, si desea buscar todos los seguimientos emitidos en el contexto del proceso X, establezca este campo en X y el campo **Buscar en** en ' nombre del proceso '. Este campo cambia a un control de selector DateTime cuando se selecciona un filtro basado en tiempo.

- Buscar en: este campo define el tipo de filtro que se va a aplicar.

- Nivel: el valor de nivel define el nivel de seguimiento mínimo permitido por el filtro. Por ejemplo, si se fija el nivel en “Error y arriba”, sólo se muestran los seguimientos en el nivel error y crítico. Este filtro se combina con los criterios especificados en Buscar y Buscar en.

El botón **filtrar ahora** inicia la operación de filtro. Algunos filtros, sobre todo cuando se aplican a un conjunto de datos grande, tardan un buen rato en terminar. Para cancelar la operación de filtrado, presione el botón **detener** que aparece en la barra de estado en el menú **operaciones** .

El botón **Borrar** restablece los filtros predefinidos y personalizados para permitir que se pasen todos los seguimientos.

#### <a name="filter-options"></a>Opciones de filtro:

El visor puede quitar de la vista automáticamente los seguimientos de WCF. Puede quitar selectivamente seguimientos emitidos por áreas concretas de WCF, por ejemplo, mediante la eliminación de la vista de seguimientos relacionados con la transacción.

La configuración de este filtro se define en el submenú **Opciones de filtro** , en el menú **Ver** .

#### <a name="custom-filters"></a>Filtros personalizados

Si está familiarizado con el lenguaje XML Path Language (XPath), puede utilizarlo y así construir filtros personalizados para buscar en los datos de seguimiento cualquier elemento XML que le interese. Se puede acceder a los filtros a través de la barra de herramientas de filtro.

Los filtros personalizados pueden incluir parámetros. También puede importar filtros personalizados que ya existan.

##### <a name="creating-a-custom-filter"></a>Crear un filtro personalizado

Los filtros se pueden crear de dos maneras:

###### <a name="creating-a-custom-filter-using-the-template-wizard"></a>Crear un filtro personalizado mediante el Asistente para plantillas

Puede hacer clic en un seguimiento existente y crear un filtro basado en la estructura del seguimiento. En este ejemplo se crea un filtro personalizado basado en un id. de subproceso.

1. En el panel de traza, en la parte superior derecha del visor, seleccione un seguimiento que incluya el elemento que desea filtrar.

2. Haga clic en el botón **crear filtro personalizado** situado en la parte superior del panel de seguimiento.

3. En el cuadro de diálogo que aparece, escriba un nombre para su filtro. En este ejemplo, escriba `Thread ID` . También puede proporcionar una descripción de su filtro.

4. La vista de árbol a la izquierda muestra la estructura del registro de seguimiento que seleccionó en el paso 1. Vaya al elemento para el que desea crear una condición. En este ejemplo, busque el ThreadID que se va a ubicar en el /E2ETraceEvent/System/Execution/@ThreadID nodo XPath:. Haga doble clic en el atributo ThreadID en la vista de árbol. Esto crea una expresión para el atributo a la derecha del diálogo.

5. Cambie el campo de parámetro de la condición ThreadID de None a ' {0} '. Este paso permite configurar el valor de ThreadID cuando se aplica el filtro. (Vea la sección Cómo aplicar un filtro) Puede definir hasta cuatro parámetros. Las condiciones se combinan mediante el operador O.

6. Haga clic en **Aceptar** para crear el filtro.

> [!NOTE]
> Una vez que se haya creado un filtro mediante el Asistente para plantillas, solo se podrá editar manualmente. No es posible activar el Asistente para un filtro que se ha creado previamente. Además, las condiciones de un filtro de XPath creado mediante el Asistente para plantillas se combinan con el operador O. Si necesita una operador Y, puede modificar la expresión del filtro una vez haya sido creado.

###### <a name="creating-a-custom-filter-manually"></a>Crear manualmente un filtro personalizado

El menú Filtros personalizados le permite escribir manualmente los filtros de XPath.

1. En el menú Ver, haga clic en el elemento de menú **filtros personalizados** .

2. En el cuadro de diálogo que aparece, haga clic en **nuevo.**

3. Como mínimo especifique un nombre de filtro y una expresión XPath.

4. Haga clic en **OK**.

###### <a name="applying-a-custom-filter"></a>Aplicar un filtro personalizado

Una vez creado un filtro personalizado, puede acceder a él a través de la barra de herramientas de filtro. Seleccione el filtro que desea aplicar en el campo **Buscar en** de la barra de herramientas del filtro. Para el ejemplo anterior, seleccione “Thread ID”.

1. Especifique el valor que está buscando en el campo **Buscar** . En este ejemplo, escriba el id. del subproceso que desea buscar.

2. Haga clic en **filtrar ahora**y observe el resultado de la operación.

Si el filtro usa varios parámetros, escríbalos con ";" como separador en el campo **Buscar** . Por ejemplo, la cadena siguiente define tres parámetros: ‘1;findValue;text’. El visor aplica ' 1 ' al {0} parámetro del filtro. ' findValue ' y ' text ' se aplican a {1} y, {2} respectivamente.

###### <a name="sharing-custom-filters"></a>Compartir filtros personalizados

Los filtros personalizados se pueden compartir entre sesiones diferentes y usuarios diferentes. Puede exportar los filtros a un archivo de definición e importar este archivo en otra ubicación.

 Para importar un filtro personalizado:

1. En el menú **Ver** , haga clic en **filtros personalizados**.

2. En el cuadro de diálogo que se abre, haga clic en el botón **importar** .

3. Navegue hasta el archivo de filtro personalizado (. stvcf), haga clic en el archivo y, a continuación, haga clic en el botón **abrir** .

Para exportar un filtro personalizado:

1. En el menú Ver, haga clic en **filtros personalizados**.

2. En el cuadro de diálogo que aparece, seleccione el filtro que desea exportar.

3. Haga clic en el botón **Exportar**.

4. Especifique el nombre y la ubicación del archivo de definición de filtro personalizado (. stvcf) y haga clic en el botón **Guardar** .

> [!NOTE]
> Estos filtros personalizados se pueden importar y exportar sólo desde el visor de seguimiento de servicio. No se pueden leer con otras herramientas.

### <a name="finding-data"></a>Buscar datos

El visor proporciona las maneras siguientes de buscar datos:

- La barra de herramientas Buscar proporciona un acceso rápido a las opciones de búsqueda más comunes.

- El cuadro de diálogo Buscar proporciona más opciones de búsqueda. Se puede obtener acceso a ella a través del menú **edición** o por la clave abreviada Ctrl + F.

La barra de herramientas Buscar aparece en la parte superior del visor. Si no está presente, puede activarlo en el menú **Ver** . La barra tiene dos componentes:

- Buscar: le permite escribir una palabra clave de búsqueda.

- Buscar en: le permite introducir un área de búsqueda. Puede seleccionar buscar en todas las actividades o sólo en la actividad actual.

El cuadro de diálogo de la búsqueda proporciona dos opciones adicionales:

- Buscar destino:

  - La opción "datos de registro sin procesar" busca la palabra clave en todos los datos sin procesar.

  - Las opciones "texto XML" y "atributo XML" solo buscan en elementos XML.

  - La opción "mensaje registrado" busca la palabra clave solo en los mensajes.

- Omitir actividad raíz: la búsqueda omite los seguimientos en la actividad "000000000000". De esta forma, se mejora el rendimiento de los archivos de seguimiento grandes cuando la actividad raíz tiene miles de trazas, la mayoría de las cuales son transferencias.

### <a name="navigating-traces"></a>Navegar por los seguimientos

Dado que los seguimientos se graban paso a paso durante el tiempo de ejecución de la aplicación, navegar por los seguimientos puede ayudarle a depurar su aplicación. El visor de seguimiento de servicio proporciona varias maneras de navegar por los seguimientos.

#### <a name="step-forward-or-backward"></a>Paso hacia delante o hacia atrás

Si considera cada seguimiento como una línea de código en el programa, avanzar es muy similar a "paso a paso por procedimientos" en el entorno de desarrollo integrado (IDE) de Visual Studio. La diferencia radica en que también puede ir hacia atrás en los seguimientos. Avanzar paso a paso significa ir a la traza siguiente de la actividad.

- Avanzar paso a paso: Use el menú **actividad** o presione "F10". También puede usar la tecla de dirección "abajo" en el panel de seguimiento.

- Retroceder paso a paso: Use el menú **actividad** o presione "F9". También puede usar la tecla de dirección "arriba" en el panel de seguimiento.

> [!NOTE]
> Esto puede llevarle a una actividad que se está produciendo en un proceso diferente o incluso en un equipo diferente, ya que los mensajes de WCF pueden llevar identificadores de actividad que abarcan los equipos.

#### <a name="follow-transfer"></a>Seguir la transferencia

Los seguimientos de transferencia son seguimientos especiales en el archivo de seguimiento. Una actividad puede transferir a otra actividad mediante un seguimiento de transferencia. Por ejemplo, la "actividad A" puede transferirse a la "actividad B". En tal caso, hay un seguimiento de transferencia en la "actividad a" con el nombre "a: actividad" y el icono de transferencia. Esta traza de transferencia es un vínculo entre las dos trazas. En "actividad B", también podría haber un seguimiento de transferencia al final de la actividad para volver a transferirlo a la "actividad a". Esto es similar a las llamadas de función en programas: A llama a B, a continuación, B devuelve.

"Seguir transferencia" es similar a "ir a" en un depurador. Sigue la transferencia de A a B. No tiene ningún efecto en otras trazas.

Hay dos maneras de seguir una transferencia: con el mouse o con el teclado:

- Con el mouse: haga doble clic en el seguimiento de transferencia del panel de traza.

- Mediante el teclado: Seleccione un seguimiento de transferencia y use "seguir transferencia" en el menú **actividad** o presione "F11".

> [!NOTE]
> En muchos casos, cuando la actividad A transfiere a la actividad B, la actividad A espera hasta que la actividad B transfiere de vuelta a la actividad A. Esto significa que la actividad A no tiene registrado ningún seguimiento cuando la actividad B realiza un seguimiento activo. Sin embargo, también es posible que la actividad A no espere y continúe registrando los seguimientos. También es posible que la actividad B no transfiera de vuelta a la actividad A. En este sentido, las transferencias de actividad aún son diferentes de las llamadas de función. Es más fácil entender las transferencias de actividad en la vista de gráfico.

#### <a name="jump-to-next-or-previous-transfer"></a>Pasar a la siguiente o anterior transferencia

Cuando analice la actividad actual, o las actividades seleccionadas cuando se han seleccionado varias actividades, puede que desee buscar rápidamente las actividades a las que transfiere. "Saltar a la siguiente transferencia" le permite localizar el siguiente seguimiento de transferencia en la actividad. Una vez que encuentre el seguimiento de transferencia, puede usar "seguir transferencia" para ir a la actividad siguiente.

- Saltar a la siguiente transferencia: Use el menú **actividad** o presione "Ctrl + F10".

- Saltar a la transferencia anterior: Use el menú **actividad** o presione "Ctrl + F9".

#### <a name="navigate-in-graph-view"></a>Navegar en la vista del gráfico

Aunque navegar por el panel de actividad y el panel de seguimiento es similar a la depuración, el uso de la vista de **gráfico** proporciona una experiencia mucho mejor en la navegación. Vea la sección "vista de gráfico" para obtener más información.

### <a name="loading-large-trace-files"></a>Cargar archivos de seguimiento grandes

Algunos archivos de seguimiento pueden ser muy grandes. Por ejemplo, si activa el seguimiento en el nivel "detallado", el archivo de seguimiento resultante para ejecutar unos minutos puede ser fácilmente de cientos de megabytes o incluso mayor, según la velocidad de la red y el patrón de comunicación.

Abrir un archivo de seguimiento muy grande en el visor de seguimiento de servicio puede repercutir negativamente en el rendimiento del sistema. La velocidad de carga y el tiempo de respuesta después de haber terminado la carga pueden ser lentos. La velocidad real difiere de vez en cuando, según su configuración del hardware. En la mayoría de los PC, cargar un archivo de seguimiento de más de 200 MB repercute seriamente en el rendimiento. Y en el caso de archivos de seguimiento de más de 1 Gb, la herramienta puede agotar toda la memoria disponible o no responder durante bastante tiempo.

Con el fin de evitar la carga lenta y el tiempo de respuesta en el análisis de archivos de seguimiento grandes, el visor de seguimiento de servicio proporciona una característica denominada "carga parcial", que solo carga una pequeña parte del seguimiento a la vez. Por ejemplo, puede darse el caso de que tenga un archivo de seguimiento de más de un 1 GB y que esté ejecutándose durante varios días en el servidor. Cuando hayan ocurrido algunos errores y desee analizar el seguimiento, no es necesario abrir todo el archivo de seguimiento. En su lugar, puede cargar los seguimientos pertenecientes al período de tiempo en el que se puede haber producido el error. Dado que el área es menor, la herramienta de visor de seguimiento de servicio puede cargar el archivo más rápido, e identificar así los errores utilizando un conjunto menor de datos.

#### <a name="enabling-partial-loading"></a>Habilitar la carga parcial

No necesita habilitar manualmente la carga parcial. Si el tamaño total de los archivos de seguimiento que intenta cargar supera los 40 MB, el visor de seguimiento de servicio muestra automáticamente un diálogo de carga parcial para que usted seleccione la parte que desea cargar.

> [!NOTE]
> Dado que puede que los seguimientos no se distribuyan de manera uniforme en el intervalo de tiempo, la longitud del período de tiempo que especifique en la barra de herramientas de carga parcial puede que no sea proporcional al tamaño de carga que se muestra. El tamaño de carga real puede ser menor que el tamaño estimado en el diálogo de carga parcial.

#### <a name="adjusting-partial-loading"></a>Ajustar la carga parcial

Después de haber cargado parcialmente el archivo de seguimiento, puede cambiar el conjunto de datos que se está cargando. Puede hacer esto ajustando la barra de herramientas de carga parcial en la parte superior del visor.

1. Mueva la barra de herramientas con el mouse o escriba la hora de inicio y finalización.

2. Haga clic en el botón **ajustar** .

## <a name="understanding-trace-icons"></a>Introducción a los iconos de seguimiento

A continuación se muestra una lista de los iconos que utiliza la herramienta Visor de seguimiento de servicio en la vista de **actividad** , la vista de **gráfico** y el panel de **seguimiento** para representar diferentes elementos.

> [!NOTE]
> Algunos seguimientos que no están clasificados (por ejemplo, "se cierra un mensaje") no tienen ningún icono.

### <a name="activity-tracing-traces"></a>Seguimiento de la actividad

|Icono|Descripción|
|----------|-----------------|
|![Seguimiento de advertencia](./media/7457c4ed-8383-4ac7-bada-bcb27409da58.gif "7457c4ed-8383-4ac7-bada-bcb27409da58")|Traza de advertencia: traza que se emite en el nivel de advertencia|
|![Seguimiento de errores](./media/7d908807-4967-4f6d-9226-d52125db69ca.gif "7d908807-4967-4f6d-9226-d52125db69ca")|Seguimiento de error: un seguimiento que se emite en el nivel de error.|
|![Seguimiento de inicio de actividad:](./media/8a728f91-5f80-4a95-afe8-0b6acd6e0317.gif "8a728f91-5f80-4a95-afe8-0b6acd6e0317")|Seguimiento de inicio de actividad: un seguimiento que marca el principio de una actividad. Contiene el nombre de la actividad. Como diseñador o programador de aplicaciones, debería definir un seguimiento de inicio de actividad por id. de actividad, por proceso o subproceso.<br /><br /> Si el id. de actividad se propaga por los orígenes de traza para la correlación de seguimiento, puede ver varios inicios para el mismo id. de actividad (uno por origen de traza). Se emite la traza de inicio si ActivityTracing está habilitado para el origen de traza.|
|![Seguimiento de detención de actividad](./media/a0493e95-653e-4af8-84a4-4d09a400bc31.gif "a0493e95-653e-4af8-84a4-4d09a400bc31")|Detener traza de actividad: una traza que marca el fin de una actividad. . Contiene el nombre de la actividad. Como diseñador o programador de aplicaciones, debe definir una traza de detención por identificador de actividad por origen de traza. Ningún seguimiento de un origen de traza determinado aparece después del fin de actividad emitido por ese origen de traza, excepto si la granularidad de tiempo del seguimiento no es lo bastante pequeña. Cuando eso pasa, se pueden intercalar dos seguimientos con la misma hora, incluyendo uno de fin, al mostrarlos. Si el id. de actividad se propaga por los orígenes de traza para la correlación de seguimiento, puede ver varios finales para el mismo id. de actividad (uno por origen de traza). Se emite la traza de detención si ActivityTracing está habilitado para el origen de traza.|
|![Traza de suspensión de actividad](./media/6f7f4191-df2b-4592-8998-8379769e2d32.gif "6f7f4191-df2b-4592-8998-8379769e2d32")|Seguimiento de suspensión de actividad: un seguimiento que marca la hora que se pausa una actividad. No se emite ningún rastro en una actividad suspendida hasta que se reanuda la actividad. Una actividad suspendida denota que no se está efectuando ningún procesamiento en esa actividad en el área del origen de traza. Los seguimientos de suspensión/reanudación son útiles para perfilar. Se emite el seguimiento de suspensión si ActivityTracing está habilitado para el origen de traza.|
|![Seguimiento de reanudación de actividad](./media/1060d9d2-c9c8-4e0a-9988-cdc2f7030f17.gif "1060d9d2-c9c8-4e0a-9988-cdc2f7030f17")|Seguimiento de reanudación de actividad: un seguimiento que marca la hora a la que se reanuda una actividad una vez suspendida. Se pueden volver a emitir seguimientos en esa actividad. Los seguimientos de suspensión/reanudación son útiles para perfilar. Se emite el seguimiento de reanudación si ActivityTracing está habilitado para el origen de traza.|
|![Transferencia](./media/b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5.gif "b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5")|Transferencia: un seguimiento que se emite cuando el flujo de control lógico se transfiere de una actividad a otra. La actividad en la que se origina la transferencia puede continuar realizando el trabajo en paralelo a la actividad a la que va la transferencia. Se emite la traza de transferencia si ActivityTracing está habilitado para el origen de traza.|
|![Transferir desde](./media/1df215cb-b344-4f36-a20d-195999bda741.gif "1df215cb-b344-4f36-a20d-195999bda741")|Transferir de: un seguimiento que define una transferencia desde otra actividad a la actividad actual.|
|![Transferir a](./media/74255b6e-7c47-46ef-8e53-870c76b04c3f.gif "74255b6e-7c47-46ef-8e53-870c76b04c3f")|Transferir a: un seguimiento que define una transferencia de flujo de control lógico desde la actividad actual a otra actividad.|

### <a name="wcf-traces"></a>Seguimiento WCF

|Icono|Descripción|
|----------|-----------------|
|![Seguimiento de registro de mensajes](./media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994-2476-4260-a0db-98948b9af197")|Seguimiento del registro de mensajes: un seguimiento que se emite cuando la característica de registro de mensajes registra un mensaje WCF, cuando el `System.ServiceModel.MessageLogging` origen de seguimiento está habilitado. Al hacer clic en este seguimiento, se muestra el mensaje. Hay cuatro puntos de registro configurables para un mensaje: ServiceLevelSendRequest, TransportSend, TransportReceive y ServiceLevelReceiveRequest, que también pueden ser especificados por el atributo `messageSource` en el seguimiento del registro de mensajes.|
|![Seguimiento de mensaje recibido](./media/de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c.gif "de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c")|Seguimiento de mensajes recibidos: un seguimiento que se emite cuando se recibe un mensaje WCF, si el `System.ServiceModel` origen de seguimiento está habilitado en el nivel de información o detallado. Este seguimiento es esencial para ver la flecha de correlación de mensajes en la vista del **gráfico** de actividades.|
|![Seguimiento de mensaje enviado](./media/558943c4-17cf-4c12-9405-677e995ac387.gif "558943c4-17cf-4c12-9405-677e995ac387")|Seguimiento de mensaje enviado: un seguimiento que se emite cuando se envía un mensaje WCF si el `System.ServiceModel` origen de seguimiento está habilitado en el nivel de información o detallado. Este seguimiento es esencial para ver la flecha de correlación de mensajes en la vista del **gráfico** de actividades.|

### <a name="activities"></a>Actividades

|Icono|Descripción|
|----------|-----------------|
|![Actividad](./media/wcfc-defaultactivityc.gif "wcfc_defaultActivityc")|Actividad: indica que la actividad actual es una actividad genérica.|
|![Actividad raíz](./media/5dc8e0eb-1c32-4076-8c66-594935beaee9.gif "5dc8e0eb-1c32-4076-8c66-594935beaee9")|Actividad raíz: indica la actividad raíz de un proceso.|

### <a name="wcf-activities"></a>Actividades WCF

|Icono|Descripción|
|----------|-----------------|
|![Actividad del entorno](./media/29fa00ac-cf78-46e5-822d-56222fff61d1.gif "29fa00ac-cf78-46e5-822d-56222fff61d1")|Actividad del entorno: una actividad que crea, abre o cierra un host o un cliente de WCF. Los errores que se han producido durante estas fases aparecerán en esta actividad.|
|![Escuchar actividad](./media/d7b135f6-ec7d-45d7-9913-037ab30e4c26.gif "d7b135f6-ec7d-45d7-9913-037ab30e4c26")|Actividad de escucha: una actividad que registra los seguimientos relacionados con un agente de escucha. Dentro de esta actividad, podemos ver información del agente de escucha y solicitudes de conexión.|
|![Recibir actividad de bytes](./media/2f628580-b80f-45a7-925b-616c96426c0e.gif "2f628580-b80f-45a7-925b-616c96426c0e")|Actividad de recepción de bytes: agrupa todos los seguimientos relacionados con la recepción de bytes de entrada en una conexión entre dos puntos de conexión. Esta actividad es esencial para ponerse en correlación con actividades de transporte que propagan su id. de actividad como http.sys. En esta actividad aparecerán errores de conexión tales como interrupciones.|
|![Actividad de mensaje de proceso](./media/wcfc-executionactivityiconc.GIF "wcfc_ExecutionActivityIconc")|Actividad procesar mensaje: una actividad que agrupa seguimientos relacionados con la creación de un mensaje WCF. En esta actividad aparecerán errores debidos a una envoltura no válida o a un mensaje incorrecto. Dentro de esta actividad, podemos inspeccionar los encabezados del mensaje para ver si un id. de actividad se propagó a partir del autor de la llamada. Si esto es verdad, cuando transferimos a la actividad de procesamiento de acción (el icono siguiente), también podemos asignar a esa actividad el id. de actividad propagado para la correlación entre el autor de la llamada y los seguimientos del destinatario.|
|![Seguimiento de registro de mensajes](./media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994-2476-4260-a0db-98948b9af197")|Actividad procesar acción: una actividad que agrupa todos los seguimientos relacionados con una solicitud WCF a través de dos extremos. Si `propagateActivity` está establecido en `true` en los dos extremos de la configuración, se combinan todos los seguimientos de ambos extremos en una actividad para la correlación directa. Tal actividad contendrá los errores debidos al procesamiento de seguridad o transporte, extendiéndose al límite del código de usuario y de vuelta (si existe una respuesta).|
|![Actividad de mensaje de proceso](./media/wcfc-executionactivityiconc.GIF "wcfc_ExecutionActivityIconc")|Actividad de ejecución de código de usuario: una actividad que agrupa seguimientos de código de usuario para procesar una solicitud.|

## <a name="troubleshooting"></a>Solución de problemas

Si no tiene permiso para escribir en el registro, obtendrá el siguiente mensaje de error "el visor de seguimiento de servicio de Microsoft no se registró en el sistema" cuando use el `svctraceviewer /register` comando "" para registrar la herramienta. Si ocurre esto, debe iniciar una sesión con una cuenta que tenga acceso de escritura al registro.

Además, las herramienta del visor de seguimiento de servicio escribe algunos valores (por ejemplo, filtros personalizados y opciones de filtro) en el archivo SvcTraceViewer.exe.settings de su carpeta de ensamblado. Si no tiene permiso de lectura para el archivo, puede iniciar la herramienta pero no puede cargar los valores.

Si obtiene el mensaje de error "Se ha producido un error desconocido al procesar uno o más seguimientos" al abrir el archivo .etl, quiere decir que el formato del archivo .etl no es válido.

Si se abre un registro de seguimiento creado utilizando un sistema operativo árabe, puede observar que el filtro horario no funciona. Por ejemplo, el año 2005 corresponde al año 1427 en el calendario árabe. Sin embargo, el intervalo temporal admitido por el filtro de la herramienta del visor de seguimiento de servicio no admite una fecha anterior a 1752. Esto puede hacer que no pueda seleccionar una fecha correcta en el filtro. Para resolver este problema, puede crear un filtro personalizado (**vista/filtros personalizados**) utilizando una expresión XPath para incluir un intervalo de tiempo específico.

## <a name="see-also"></a>Consulte también

- [Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas](./diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Configurar seguimiento](./diagnostics/tracing/configuring-tracing.md)
- [Seguimiento de traza de un extremo a otro](./diagnostics/tracing/end-to-end-tracing.md)
