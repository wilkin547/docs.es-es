---
title: Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)
ms.date: 03/30/2017
ms.assetid: 9027efd3-df8d-47ed-8bcd-f53d55ed803c
ms.openlocfilehash: 723b1c6858f0c56d4834dc937b9f4883e22156e6
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57680391"
---
# <a name="service-trace-viewer-tool-svctraceviewerexe"></a>Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)
Herramienta Service Trace Viewer de Windows Communication Foundation (WCF) le ayuda a analizar seguimientos del diagnóstico generados por WCF. Service Trace Viewer proporciona una manera de combinar fácilmente, ver y filtrar los mensajes de seguimiento en el registro de modo que puede diagnosticar, reparar y comprobar los problemas de servicio WCF.  
  
## <a name="configuring-tracing"></a>Configurar seguimiento  
 El seguimiento de diagnóstico le proporciona información que muestra lo que está pasando a lo largo de la operación de su aplicación. Como su propio nombre indica, también puede seguir las operaciones desde el origen hasta el destino y en los puntos intermedios.  
  
 Puede configurar el seguimiento mediante el archivo de configuración de la aplicación, o bien Web.config para las aplicaciones hospedadas en Web o *Appname*.config para las aplicaciones autohospedadas. A continuación se muestra un ejemplo:  
  
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
  
 En este ejemplo, se especifican el nombre y el tipo del agente de escucha de traza. El agente de escucha se denomina `sdt` y se agrega como tipo el agente de escucha de traza estándar de .NET Framework (System.Diagnostics.XmlWriterTraceListener). El `initializeData` atributo se usa para establecer el nombre del archivo de registro para ese agente de escucha ser `SdrConfigExample.e2e`. Para el archivo de registro, puede sustituir una ruta de acceso completa para un nombre de archivo simple.  
  
 El ejemplo crea un archivo en el directorio raíz denominado SdrConfigExample.e2e. Cuando se usa el Visor de seguimiento para abrir el archivo como se describe en la sección "Abrir y ver archivos WCF de seguimiento", puede ver todos los mensajes que se han enviado.  
  
 La configuración de `switchValue` controla el nivel de traza. En la siguiente tabla se describen los niveles de seguimiento disponibles.  
  
|Nivel de seguimiento|Descripción|  
|-----------------|-----------------|  
|Crítico|: Registra las entradas Fail-Fast y registro de eventos y la información de correlación de seguimiento. A continuación se muestran algunos ejemplos de cuándo se puede utilizar el nivel Crítico:<br />-Su AppDomain ha fallado debido a una excepción no controlada.<br />-La aplicación no puede iniciarse.<br />-El mensaje que provocó el error que se origina en el proceso MyApp.exe.|  
|Error|: Registra todas las excepciones. Puede utilizar el nivel Error en las situaciones siguientes:<br />-El código se ha bloqueado debido a una excepción de conversión no válida.<br />-Una excepción "no se pudo crear el punto de conexión" provoca que la aplicación no pueda iniciarse.|  
|Advertencia|-Existe una condición que posteriormente puede producir un error o un error crítico. Puede utilizar este nivel en las situaciones siguientes:<br />-La aplicación está recibiendo más solicitudes que permite la configuración de su límite.<br />-La cola receptora está al 98 por ciento de su capacidad configurada.|  
|Información|-Los mensajes útiles para supervisar y diagnosticar el estado del sistema, medir el rendimiento o de generación de perfiles se generan. Puede utilizar esa información para el diseño de la capacidad y la gestión del rendimiento. Puede utilizar este nivel en las situaciones siguientes:<br />-Error después de que el mensaje llegase al AppDomain y se ha deserializado.<br />-Error mientras se creaba el enlace HTTP.|  
|Detallado|Nivel de depuración seguimiento tanto el código de usuario y de mantenimiento. Establezca este nivel cuando:<br />-No estás seguro de qué método en el código se llamó cuando se produjo el error.<br />-Tiene configurado un extremo incorrecto y el servicio no se pudo iniciar porque la entrada en el almacén de reserva está bloqueada.|  
|ActivityTracing|Transmitir eventos entre actividades de procesamiento y componentes.<br /><br /> Este nivel permite a los administradores y programadores poner en correlación las aplicaciones en el mismo dominio de aplicación.<br /><br /> -Seguimientos de los límites de actividad: iniciar o detener.<br />-Seguimiento de las transferencias.|  
  
 Puede utilizar `add` para especificar el nombre y tipo de agente de escucha de seguimiento que desea utilizar. En la configuración del ejemplo, el agente de escucha se denomina `sdt` y se agrega como tipo el agente de escucha de traza de .NET Framework estándar (`System.Diagnostics.XmlWriterTraceListener`). Utilice `initializeData` para establecer el nombre del archivo de registro para ese agente de escucha. Además, puede sustituir un nombre de archivo simple por una ruta de acceso completa.  

A partir de .NET Framework 4.8, controles de cuadro combinado en algunos temas de contraste alto se muestran en el color correcto. Puede deshabilitar este cambio mediante la eliminación de la siguiente configuración de la *svcTraceViewer.exe.config* archivo:

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

## <a name="using-the-service-trace-viewer-tool"></a>Utilizar la herramienta de visor de seguimiento de servicio  
  
### <a name="opening-and-viewing-wcf-trace-files"></a>Abrir y ver los archivos de seguimiento de WCF  
 El visor de seguimiento de servicio admite tres tipos de archivo:  
  
-   (.SvcLog) del archivo de seguimiento de WCF  
  
-   Archivo de seguimiento de eventos (.etl)  
  
-   Archivo de seguimiento carmesí  
  
 El visor de seguimiento de servicio le permite abrir cualquier archivo de seguimiento compatible, agregar e integrar archivos de seguimiento adicionales o abrir y fusionar mediante combinación simultáneamente un grupo de archivos de seguimiento.  
  
##### <a name="to-open-a-trace-file"></a>Para abrir un archivo de seguimiento  
  
1.  Inicie Service Trace Viewer mediante una ventana de comandos para navegar a la ubicación de instalación de WCF (C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin) y, a continuación, escriba `SvcTraceViewer.exe`.  
  
> [!NOTE]
>  La herramienta del visor de seguimiento de servicio puede asociar dos tipos de archivo: .svclog y .stvproj. Puede utilizar dos parámetros en línea de comandos para registrar y eliminar del registro las extensiones de archivo.  
>   
>  /register: registrar la asociación de las extensiones de archivo “.svclog” y “.stvproj” con SvcTraceViewer.exe  
>   
>  /unregister: eliminar del registro la asociación de las extensiones de archivo “.svclog” y “.stvproj” con SvcTraceViewer.exe  
  
1.  Cuando se inicia el Visor de seguimiento de servicio, haga clic en **archivo** y, a continuación, elija **abierto**. Navegue a la ubicación donde se almacenan sus archivos de seguimiento.  
  
2.  Haga doble clic en el archivo de seguimiento que desea abrir.  
  
    > [!NOTE]
    >  Presione MAYÚS mientras hace clic en varios archivos de seguimiento para seleccionarlos y abrirlos de forma simultánea. El visor de seguimiento de servicio combina el contenido de todos los archivos y los muestra en una vista. Por ejemplo, puede abrir archivos de seguimiento tanto de cliente como de servicio. Esto es útil cuando ha habilitado en la configuración el registro de mensajes y la propagación de la actividad. De esta manera, puede examinar el intercambio de mensajes entre cliente y servicio. También puede arrastrar varios archivos al visor o utilizar el **proyecto** ficha. Para obtener información más detallada, consulte la sección Administrar proyecto.  
  
3.  Para agregar archivos de seguimiento adicionales a la colección que está abierta, haga clic en **archivo** y, a continuación, elija **agregar**. En la ventana que se abre, navegue a la ubicación de los archivos de seguimiento y haga doble clic en el archivo que desea agregar.  
  
> [!CAUTION]
>  No se recomienda cargar un archivo de seguimiento mayor de 200MB. Si intenta cargar un archivo mayor que ese límite, el proceso de carga puede tardar mucho tiempo, dependiendo de su recurso informático. Puede que la herramienta del visor de seguimiento de servicio no responda durante mucho tiempo o que agote la memoria de su equipo. Se recomienda que configure carga parcial para evitarlo. Para obtener más información sobre cómo hacerlo, vea la sección “Cargar archivos de seguimiento grandes”.  
  
#### <a name="event-tracing-and-crimson-tracing"></a>Traza de eventos y traza carmesí  
 Formato original del Visor es el formato de seguimiento de actividad que emite WCF. Las trazas emitidas en un formato diferente se deben convertir antes de que el visor las muestre. Actualmente, además del formato de traza de la actividad, el visor admite traza de eventos y traza carmesí.  
  
 Al abrir un archivo que no contiene seguimientos de actividad, el visor intenta convertir el archivo. Debe especificar el nombre y la ubicación del archivo que contendrá los datos de seguimiento convertidos. Una vez convertidos los datos, el visor muestra el contenido del nuevo archivo.  
  
> [!NOTE]
>  La conversión requiere espacio en disco para almacenar la información de seguimiento convertida. Antes de iniciar una conversión, asegúrese de tener suficiente espacio en disco para almacenar los datos. De lo contrario, se produce un error en la conversión.  
  
### <a name="managing-projects"></a>Administrar proyectos  
 El visor admite proyectos para facilitar la vista de varios archivos de seguimiento. Por ejemplo, si tiene un archivo de seguimiento de cliente y un archivo de seguimiento de servicio, puede agregarlos a un proyecto. A continuación, cada vez que abra el proyecto, se cargan todos los archivos de seguimiento en el proyecto de manera simultánea.  
  
 Hay dos maneras de administrar los proyectos:  
  
-   En el **archivo** menú, puede abrir, guardar y cerrar proyectos.  
  
-   En el **proyecto** ficha, puede agregar archivos a un proyecto.  
  
### <a name="viewing-wcf-traces"></a>Ver seguimiento de WCF  
 WCF emite trazas usando el formato de seguimiento de actividad. En el modelo de seguimiento de actividad, los seguimientos individuales están agrupados en actividades según su propósito. El flujo de control lógico se transfiere entre las actividades. Por ejemplo, durante el tiempo que dura una aplicación, aparecen y desaparecen muchas "actividades de envío de mensaje". Para obtener más información sobre cómo ver los seguimientos y las actividades y la interfaz de usuario de Service Trace Viewer demasiado, consulte [utilizando Service Trace Viewer para ver seguimientos correlacionados y solución de problemas](../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
#### <a name="switching-to-different-views"></a>Alternar vistas diferentes  
 El visor de seguimiento de servicio proporciona estas vistas diferentes. Se muestran como pestañas en el panel izquierdo del Visor y también se puede acceder desde el **vista** menú.  
  
-   Vista de actividad  
  
-   Vista de proyecto  
  
-   Vista de mensaje  
  
-   Vista de gráfico  
  
##### <a name="activity-view"></a>Vista de actividad  
 Una vez que se abren los archivos de seguimiento, puede ver los seguimientos agrupados por actividades y se muestra en el **actividad** vista en el panel izquierdo.  
  
 El **actividad** vista muestra los nombres de actividad, número de seguimientos de la actividad, duración, hora de inicio y hora de finalización.  
  
 Haciendo clic en cualquiera de las actividades de la lista, los seguimientos en esta actividad se muestran en el panel de seguimiento a la derecha. Puede seleccionar a continuación un seguimiento para ver sus detalles.  
  
 Puede seleccionar varias actividades presionando el **Ctrl** o **MAYÚS** clave y haga clic en las actividades deseadas. El panel de seguimiento muestra todos los seguimientos de las actividades seleccionadas.  
  
 Haga doble clic en una actividad para mostrarla en **Graph** vista. La manera alternativa es seleccionar una actividad y cambiar a **Graph** vista.  
  
> [!NOTE]
>  La actividad "000000000000" es una actividad especial que no se muestran en la vista gráfico. Dado que las otras actividades se vinculan a ella, mostrar esta actividad tiene un impacto importante en el rendimiento.  
  
 Puede hacer clic en el título de la columna para ordenar la lista de actividades. Las actividades que contienen seguimientos de advertencia tienen un fondo amarillo y aquéllas que contienen seguimientos de error tienen un fondo rojo.  
  
 Hay diferentes tipos de actividades, y cada tipo corresponde a un icono en el lado izquierdo de cada actividad. Puede consultar la sección Introducción a los iconos de seguimiento para conocer su significado.  
  
##### <a name="project-view"></a>Vista de proyecto  
 Esta vista le permite administrar los archivos de seguimiento en el proyecto actual. Para obtener información más detallada, consulte la sección Administrar proyecto.  
  
##### <a name="graph-view"></a>Vista de gráfico  
 Una de las características más eficaces de Service Trace Viewer es el **Graph** vista, que muestra los datos de seguimiento para una actividad determinada en forma de gráfico. Esta opción de gráficos le permite ver la ejecución paso a paso de eventos y las relaciones mutuas entre varias actividades cuando los datos se mueven entre ellas.  
  
 Para cambiar a **Graph** ver, seleccione una actividad en el **actividad** ver y haga clic en el **actividad** ficha o un seguimiento del registro de mensajes en el **mensaje**Vista. Si se cargan varios archivos de seguimiento y la actividad implica seguimientos de más de un archivo, todos los seguimientos pertinentes aparecen en la vista de Gráfico. Haga doble clic en las actividades y seguimientos del registro de mensajes también podrá acceder a la **Graph** vista.  
  
 En **Graph** ver, cada columna vertical representa una actividad, y cada bloque de la columna representa un seguimiento. Las actividades se agrupan por proceso (o subproceso). Las flechas pequeñas entre las actividades representan las transferencias. Las flechas grandes entre los procesos representan el intercambio de mensajes. La actividad seleccionada siempre aparece en amarillo.  
  
###### <a name="selecting-traces-in-the-graph"></a>Seleccionar seguimientos en el gráfico  
  
1.  Haga clic en un bloque del gráfico.  
  
2.  Utilice las teclas arriba y abajo para seleccionar los seguimientos adyacentes.  
  
3.  Puede ver la información del seguimiento en el panel de seguimiento y en el panel detalle.  
  
###### <a name="expanding-or-collapsing-activity-transfers"></a>Expandir o contraer transferencias de la actividad  
 Puede expandir las transferencias de la actividad cuando la actividad seleccionada transfiere a otra actividad. Le permite seguir las transferencias.  
  
 Para expandir o contraer transferencias de la actividad,  
  
1.  Busque la traza de transferencia con un signo "+" de la izquierda del icono de transferencia.  
  
2.  Haga clic en "+", o presione **Ctrl** y "+" mediante el teclado.  
  
3.  La actividad siguiente aparece en el gráfico.  
  
4.  Un "-" aparece a la izquierda del icono de transferencia. Haga clic en el "-" iniciar sesión o presione la tecla Ctrl y "-", se contrae la transferencia de actividad.  
  
> [!NOTE]
>  Cuando una actividad tiene varias transferencias y expande una de ellas, se muestran las actividades que llevan a la nueva actividad desde la actividad raíz. Estas nuevas actividades se muestran en formato contraído. Si desea ver los detalles de estas actividades, expándalas verticalmente haciendo clic en el icono de expandir, en el encabezado del gráfico.  
  
###### <a name="expanding-or-collapsing-activities-vertically"></a>Expandir o contraer verticalmente las actividades  
 El visor contrae las actividades para así ocultar detalles innecesarios en el gráfico de la actividad. En una actividad contraída no se muestran los seguimientos individuales. Sólo aparecen las transferencias de seguimiento. Si desea ver todas las trazas en una actividad, expanda verticalmente la actividad haciendo clic en el símbolo de expansión de la actividad situado en el encabezado del gráfico.  
  
 Para expandir o contraer verticalmente las actividades,  
  
1.  Haga clic en el icono "+" en el encabezado de la actividad para expandir verticalmente la actividad.  
  
2.  Tenga en cuenta que todas las trazas se muestran en el gráfico.  
  
3.  Haga clic en el "-" icono en el encabezado de la actividad para contraer verticalmente la actividad.  
  
4.  Tenga en cuenta que sólo se muestran en la actividad las transferencias importantes, registros de mensajes y seguimientos de advertencia y de excepción.  
  
###### <a name="options"></a>Opciones  
 Puede seleccionar dos opciones en el **opción** menú en la vista de gráfico.  
  
-   Mostrar seguimientos de límite de la actividad que, cuando se desactiva, omite los seguimientos del límite de la actividad en el gráfico.  
  
-   Mostrar seguimientos detallados sin mensaje que, cuando se desactiva, omite todos los seguimientos de nivel detallados, excepto los seguimientos de mensajes. En la mayoría de los casos, los seguimientos de nivel detallados son menos importantes para el análisis. Esta opción es útil cuando no desea analizar los seguimientos de nivel detallados y sólo desea centrarse en seguimientos más importantes.  
  
###### <a name="layout-mode"></a>Modo de diseño  
 El Visor tiene dos modos de diseño: **Proceso** y **subprocesos**. Esta configuración define la unidad más grande de organización. El valor predeterminado es el modo de diseño **proceso**, lo que significa que las actividades se agrupan por procesos en el gráfico.  
  
###### <a name="execution-list"></a>Lista de ejecución  
 Puede seleccionar qué proceso o subproceso de este menú desplegable se va a mostrar en el gráfico. Por ejemplo, si tiene abiertos los archivos de seguimiento de dos clientes (A y B) y un servicio, y sólo desea mostrar el servicio y el cliente A en el gráfico, puede anular la selección del cliente B en la lista.  
  
#### <a name="viewing-trace-details"></a>Ver detalles del seguimiento  
 Para ver un detalle del seguimiento, seleccione un seguimiento en el panel de traza. Los detalles se muestran en el panel detalle.  
  
##### <a name="trace-pane"></a>Panel de traza  
 El panel superior derecho en el visor de seguimiento de servicio es el panel de traza. Contiene una lista de todos los seguimientos en la actividad seleccionada con información adicional, como nivel de seguimiento, id. de subproceso y nombre del proceso.  
  
 Puede copiar el XML sin formato del seguimiento al Portapapeles haciendo clic en un seguimiento y seleccionando **copiar seguimiento a Portapapeles**.  
  
##### <a name="detail-pane"></a>Panel detalle  
 El panel inferior izquierdo en el visor de seguimiento de servicio es el Panel de detalles. Tiene tres pestañas para ver los detalles de seguimiento.  
  
 El **con formato** vista muestra la información de una manera más organizada. Contiene una lista de todos los elementos XML conocidos en tablas y árboles, por lo que será más fácil leer y entender la información.  
  
 El **XML** vista muestra el XML que corresponden al seguimiento seleccionado. Permite resaltar y colorear la sintaxis. Cuando usas **buscar** para buscar cadenas, resalta los resultados de búsqueda.  
  
 El **mensaje** vista muestra la parte del mensaje de XML en los seguimientos de registro de mensajes. No se puede ver si selecciona un seguimiento sin mensaje.  
  
### <a name="filtering-wcf-traces"></a>Filtrar los seguimientos de WCF  
 Para facilitar el análisis de seguimientos, puede filtrarlos de las maneras siguientes:  
  
-   La barra de herramientas de filtro proporciona el acceso a los filtros predefinidos y personalizados. Se puede habilitar a través de la **vista** menú.  
  
-   El filtro predefinido del Visor se puede usar para filtrar selectivamente partes de los seguimientos WCF. Se establece de forma predeterminada que todos los seguimientos de infraestructura puedan pasar. La configuración de este filtro se define en el **opciones de filtro** submenú **vista** menú.  
  
-   Los filtros del XPath personalizados les dan a los usuarios el control completo sobre cómo filtrar. Se pueden definir en el **filtro personalizado** en **vista** menú.  
  
 Sólo se muestran los seguimientos que atraviesan todos los filtros.  
  
#### <a name="using-the-filter-toolbar"></a>Utilizar la barra de herramientas del filtro  
 La barra de herramientas del filtro aparece en la parte superior de la herramienta. Si no está presente, puede activarla en el **vista** menú. La barra tiene tres componentes:  
  
-   Busca: **Busque** define el asunto que se busca en la operación de filtrado. Por ejemplo, si desea buscar todos los seguimientos que se emitieron en el contexto de proceso X, establezca este campo a X y el **buscar en** campo nombre del proceso. Este campo cambia a un control de selector DateTime cuando se selecciona un filtro basado en tiempo.  
  
-   Buscar en: Este campo define el tipo de filtro para aplicar.  
  
-   Nivel: La configuración del nivel define el nivel de seguimiento mínimo permitido por el filtro. Por ejemplo, si se fija el nivel en “Error y arriba”, sólo se muestran los seguimientos en el nivel error y crítico. Este filtro se combina con los criterios especificados en Buscar y Buscar en.  
  
 El **filtrar ahora** botón inicia la operación de filtrado. Algunos filtros, sobre todo cuando se aplican a un conjunto de datos grande, tardan un buen rato en terminar. Puede cancelar la operación de filtrado presionando el **detener** botón que aparece en la barra de estado en el **operaciones** menú.  
  
 El **clara** botón restablece los filtros predefinidos y personalizados para permitir que pasen todos los seguimientos.  
  
#### <a name="filter-options"></a>Opciones de filtro:  
 El visor puede quitar de la vista automáticamente los seguimientos de WCF. Puede quitar selectivamente seguimientos emitidos por áreas concretas de WCF, por ejemplo, mediante la eliminación de la vista de seguimientos relacionados con la transacción.  
  
 La configuración de este filtro se define en el **opciones de filtro** submenú **vista** menú.  
  
#### <a name="custom-filters"></a>Filtros personalizados  
 Si está familiarizado con el lenguaje XML Path Language (XPath), puede utilizarlo y así construir filtros personalizados para buscar en los datos de seguimiento cualquier elemento XML que le interese. Se puede acceder a los filtros a través de la barra de herramientas de filtro.  
  
 Los filtros personalizados pueden incluir parámetros. También puede importar filtros personalizados que ya existan.  
  
##### <a name="creating-a-custom-filter"></a>Crear un filtro personalizado  
 Los filtros se pueden crear de dos maneras:  
  
###### <a name="creating-a-custom-filter-using-the-template-wizard"></a>Crear un filtro personalizado mediante el Asistente para plantillas  
 Puede hacer clic en un seguimiento existente y crear un filtro basado en la estructura del seguimiento. En este ejemplo se crea un filtro personalizado basado en un id. de subproceso.  
  
1.  En el panel de traza, en la parte superior derecha del visor, seleccione un seguimiento que incluya el elemento que desea filtrar.  
  
2.  Haga clic en el **Crear filtro personalizado** situado en la parte superior del panel de traza.  
  
3.  En el cuadro de diálogo que aparece, escriba un nombre para su filtro. En este ejemplo, escriba `Thread ID`. También puede proporcionar una descripción de su filtro.  
  
4.  La vista de árbol a la izquierda muestra la estructura del registro de seguimiento que seleccionó en el paso 1. Vaya al elemento para el que desea crear una condición. En este ejemplo, vaya a ThreadID, que se encuentra en la expresión XPath: /E2ETraceEvent/System/Execution/@ThreadID nodo. Haga doble clic en el atributo ThreadID en la vista de árbol. Esto crea una expresión para el atributo a la derecha del diálogo.  
  
5.  Cambie el campo de parámetro para la condición ThreadID de ninguno a '{0}'. Este paso permite configurar el valor de ThreadID cuando se aplica el filtro. (Vea la sección Cómo aplicar un filtro) Puede definir hasta cuatro parámetros. Las condiciones se combinan mediante el operador O.  
  
6.  Haga clic en **Aceptar** para crear el filtro.  
  
> [!NOTE]
>  Una vez que se haya creado un filtro mediante el Asistente para plantillas, solo se podrá editar manualmente. No es posible activar el Asistente para un filtro que se ha creado previamente. Además, las condiciones de un filtro de XPath creado mediante el Asistente para plantillas se combinan con el operador O. Si necesita una operador Y, puede modificar la expresión del filtro una vez haya sido creado.  
  
###### <a name="creating-a-custom-filter-manually"></a>Crear manualmente un filtro personalizado  
 El menú Filtros personalizados le permite escribir manualmente los filtros de XPath.  
  
1.  En el menú Ver, haga clic en el **filtros personalizados** elemento de menú.  
  
2.  En el cuadro de diálogo que aparece, haga clic en **nuevo.**  
  
3.  Como mínimo especifique un nombre de filtro y una expresión XPath.  
  
4.  Haga clic en **Aceptar**.  
  
###### <a name="applying-a-custom-filter"></a>Aplicar un filtro personalizado  
 Una vez creado un filtro personalizado, puede acceder a él a través de la barra de herramientas de filtro. Seleccione el filtro que desea aplicar en el **buscar en** campo de la barra de herramientas de filtro. Para el ejemplo anterior, seleccione “Thread ID”.  
  
1.  Especifique el valor que está buscando en el **buscar** campo. En este ejemplo, escriba el id. del subproceso que desea buscar.  
  
2.  Haga clic en **filtrar ahora**y observe el resultado de la operación.  
  
 Si su filtro usa varios parámetros, escríbalos mediante ';' como separador en la **buscar** campo. Por ejemplo, la cadena siguiente define 3 parámetros: '1; findValue; text'. El Visor aplica '1' para el {0} parámetro del filtro. 'findValue' y 'text' se aplican a {1} y {2} respectivamente.  
  
###### <a name="sharing-custom-filters"></a>Compartir filtros personalizados  
 Los filtros personalizados se pueden compartir entre sesiones diferentes y usuarios diferentes. Puede exportar los filtros a un archivo de definición e importar este archivo en otra ubicación.  
  
 Para importar un filtro personalizado:  
  
1.  En el **vista** menú, haga clic en **filtros personalizados**.  
  
2.  En el cuadro de diálogo que aparece, haga clic en el **importación** botón.  
  
3.  Navegue hasta el archivo de filtro personalizado (.stvcf), haga clic en el archivo y haga clic en el **abierto** botón.  
  
 Para exportar un filtro personalizado:  
  
1.  En el menú Ver, haga clic en **filtros personalizados**.  
  
2.  En el cuadro de diálogo que aparece, seleccione el filtro que desea exportar.  
  
3.  Haga clic en el **exportar** botón.  
  
4.  Especifique el nombre y la ubicación del archivo de definición de filtro personalizado (.stvcf) y haga clic en el **guardar** botón.  
  
> [!NOTE]
>  Estos filtros personalizados se pueden importar y exportar sólo desde el visor de seguimiento de servicio. No se pueden leer con otras herramientas.  
  
### <a name="finding-data"></a>Buscar datos  
 El visor proporciona las maneras siguientes de buscar datos:  
  
-   La barra de herramientas Buscar proporciona un acceso rápido a las opciones de búsqueda más comunes.  
  
-   El cuadro de diálogo Buscar proporciona más opciones de búsqueda. Es accesible a través de la **editar** menú, o mediante la combinación de teclas Ctrl + f el.  
  
 La barra de herramientas Buscar aparece en la parte superior del visor. Si no está presente, puede activarla en el **vista** menú. La barra tiene dos componentes:  
  
-   Buscar: Permite especificar la palabra clave de búsqueda.  
  
-   Buscar en: Permite especificar el ámbito de búsqueda. Puede seleccionar buscar en todas las actividades o sólo en la actividad actual.  
  
 El cuadro de diálogo de la búsqueda proporciona dos opciones adicionales:  
  
-   Buscar destino:  
  
    -   La opción "datos de registro sin procesar" busca la palabra clave en todos los datos sin procesar.  
  
    -   Las opciones "Texto XML" y "Atributo XML" solo buscan en elementos XML.  
  
    -   La opción "Mensaje registrado" busca la palabra clave sólo en los mensajes.  
  
-   Ignorar la actividad raíz: La búsqueda ignora las trazas en la actividad "000000000000". De esta forma, se mejora el rendimiento de los archivos de seguimiento grandes cuando la actividad raíz tiene miles de trazas, la mayoría de las cuales son transferencias.  
  
### <a name="navigating-traces"></a>Navegar por los seguimientos  
 Dado que los seguimientos se graban paso a paso durante el tiempo de ejecución de la aplicación, navegar por los seguimientos puede ayudarle a depurar su aplicación. El visor de seguimiento de servicio proporciona varias maneras de navegar por los seguimientos.  
  
#### <a name="step-forward-or-backward"></a>Paso hacia delante o hacia atrás  
 Si considera cada seguimiento como una línea de código en el programa, ir hacia delante es muy similar a "Paso a paso" en el entorno de desarrollo integrado (IDE) de Visual Studio. La diferencia radica en que también puede ir hacia atrás en los seguimientos. Avanzar paso a paso significa ir a la traza siguiente de la actividad.  
  
-   Avanzar paso a paso: Use la **actividad** menús o presione "F10". También puede usar tecla de dirección "abajo" en el panel de seguimiento.  
  
-   Retroceder paso a paso: Use la **actividad** menús o presione "F9". También puede usar tecla de dirección "up" en el panel de seguimiento.  
  
> [!NOTE]
>  Esto puede llevarlo a una actividad que se producen en un proceso diferente o incluso en un equipo diferente, porque los mensajes de WCF pueden llevar identificadores de actividad que abarcan varias máquinas.  
  
#### <a name="follow-transfer"></a>Seguir la transferencia  
 Los seguimientos de transferencia son seguimientos especiales en el archivo de seguimiento. Una actividad puede transferir a otra actividad mediante un seguimiento de transferencia. Por ejemplo, "Actividad A" puede transferir a la "Actividad B". En este caso, hay una traza de transferencia en la "actividad A" con el nombre "para: La actividad"y el icono de transferencia. Esta traza de transferencia es un vínculo entre las dos trazas. En la "Actividad B", también podría haber una traza de transferencia al final de la actividad para transferir de vuelta a la "Actividad A". Esto es similar a las llamadas de función en programas: Una llama a B, a continuación, B devuelve.  
  
 "Seguir a transferencia" es similar a "Ir a" en un depurador. Sigue la transferencia de A a B. No tiene ningún efecto en otras trazas.  
  
 Hay dos maneras de seguir una transferencia: con el mouse o con el teclado:  
  
-   Con el Mouse: Haga doble clic en el seguimiento de transferencia en el panel de seguimiento.  
  
-   Con el teclado: Seleccione una traza de transferencia y use "Seguir transferencia" en el **actividad** menús o presione "F11"  
  
> [!NOTE]
>  En muchos casos, cuando la actividad A transfiere a la actividad B, la actividad A espera hasta que la actividad B transfiere de vuelta a la actividad A. Esto significa que la actividad A no tiene registrado ningún seguimiento cuando la actividad B realiza un seguimiento activo. Sin embargo, también es posible que la actividad A no espere y continúe registrando los seguimientos. También es posible que la actividad B no transfiera de vuelta a la actividad A. En este sentido, las transferencias de actividad aún son diferentes de las llamadas de función. Es más fácil entender las transferencias de actividad en la vista de gráfico.  
  
#### <a name="jump-to-next-or-previous-transfer"></a>Pasar a la siguiente o anterior transferencia  
 Cuando analice la actividad actual, o las actividades seleccionadas cuando se han seleccionado varias actividades, puede que desee buscar rápidamente las actividades a las que transfiere. "Pasar a la siguiente transferencia" le permite localizar la siguiente traza de transferencia de la actividad. Una vez que encuentre la traza de transferencia, puede usar "Seguir transferencia" para ir a la siguiente actividad.  
  
-   Saltar a la transferencia siguiente: Use la **actividad** menús o presione "Ctrl + F10".  
  
-   Saltar a la transferencia anterior: Use la **actividad** menús o presione "Ctrl + F9".  
  
#### <a name="navigate-in-graph-view"></a>Navegar en la vista del gráfico  
 Aunque la navegación en el panel de actividad y seguimiento es similar a depurar, usar **Graph** vista proporciona una mejor experiencia de navegación. Para obtener más información, vea la sección "Vista de gráfico".  
  
### <a name="loading-large-trace-files"></a>Cargar archivos de seguimiento grandes  
 Algunos archivos de seguimiento pueden ser muy grandes. Por ejemplo, si activa el seguimiento en el nivel "Detallado, el archivo de seguimiento resultante" de ejecutar unos minutos puede fácilmente ser cientos de megabytes o incluso mayor, según el patrón de comunicación y la velocidad de red.  
  
 Abrir un archivo de seguimiento muy grande en el visor de seguimiento de servicio puede repercutir negativamente en el rendimiento del sistema. La velocidad de carga y el tiempo de respuesta después de haber terminado la carga pueden ser lentos. La velocidad real difiere de vez en cuando, según su configuración del hardware. En la mayoría de los PC, cargar un archivo de seguimiento de más de 200 MB repercute seriamente en el rendimiento. Y en el caso de archivos de seguimiento de más de 1 Gb, la herramienta puede agotar toda la memoria disponible o no responder durante bastante tiempo.  
  
 Para evitar la carga lenta y el tiempo de respuesta en analizar archivos de seguimiento grandes, Service Trace Viewer proporciona una característica llamada "Carga parcial", que solo se cargan partes pequeñas del seguimiento a la vez. Por ejemplo, puede darse el caso de que tenga un archivo de seguimiento de más de un 1 GB y que esté ejecutándose durante varios días en el servidor. Cuando hayan ocurrido algunos errores y desee analizar el seguimiento, no es necesario abrir todo el archivo de seguimiento. En su lugar, puede cargar los seguimientos pertenecientes al período de tiempo en el que se puede haber producido el error. Dado que el área es menor, la herramienta de visor de seguimiento de servicio puede cargar el archivo más rápido, e identificar así los errores utilizando un conjunto menor de datos.  
  
#### <a name="enabling-partial-loading"></a>Habilitar la carga parcial  
 No necesita habilitar manualmente la carga parcial. Si el tamaño total de los archivos de seguimiento que intenta cargar supera los 40 MB, el visor de seguimiento de servicio muestra automáticamente un diálogo de carga parcial para que usted seleccione la parte que desea cargar.  
  
> [!NOTE]
>  Dado que puede que los seguimientos no se distribuyan de manera uniforme en el intervalo de tiempo, la longitud del período de tiempo que especifique en la barra de herramientas de carga parcial puede que no sea proporcional al tamaño de carga que se muestra. El tamaño de carga real puede ser menor que el tamaño estimado en el diálogo de carga parcial.  
  
#### <a name="adjusting-partial-loading"></a>Ajustar la carga parcial  
 Después de haber cargado parcialmente el archivo de seguimiento, puede cambiar el conjunto de datos que se está cargando. Puede hacer esto ajustando la barra de herramientas de carga parcial en la parte superior del visor.  
  
1.  Mueva la barra de herramientas con el mouse o escriba la hora de inicio y finalización.  
  
2.  Haga clic en el **ajustar** botón.  
  
## <a name="understanding-trace-icons"></a>Introducción a los iconos de seguimiento  
 La siguiente es una lista de iconos que usa la herramienta Service Trace Viewer en el **actividad** vista, **Graph** vista y **seguimiento** panel para representar elementos diferentes.  
  
> [!NOTE]
>  Algunos seguimientos que no están categorizados (por ejemplo, "se cierra un mensaje") no tienen ningún icono.  
  
### <a name="activity-tracing-traces"></a>Seguimiento de la actividad  
  
|Iconos|Descripción|  
|----------|-----------------|  
|![Seguimiento de advertencia](../../../docs/framework/wcf/media/7457c4ed-8383-4ac7-bada-bcb27409da58.gif "7457c4ed-8383-4ac7-bada-bcb27409da58")|Seguimiento de advertencia: Un seguimiento que se emite en el nivel de advertencia|  
|![Seguimiento de errores](../../../docs/framework/wcf/media/7d908807-4967-4f6d-9226-d52125db69ca.gif "7d908807-4967-4f6d-9226-d52125db69ca")|Seguimiento de errores: Un seguimiento que se emite en el nivel de error.|  
|![Seguimiento de inicio de actividad:](../../../docs/framework/wcf/media/8a728f91-5f80-4a95-afe8-0b6acd6e0317.gif "8a728f91-5f80-4a95-afe8-0b6acd6e0317")|Seguimiento de inicio de actividad: Un seguimiento que marca el principio de una actividad. Contiene el nombre de la actividad. Como diseñador o programador de aplicaciones, debería definir un seguimiento de inicio de actividad por id. de actividad, por proceso o subproceso.<br /><br /> Si el id. de actividad se propaga por los orígenes de traza para la correlación de seguimiento, puede ver varios inicios para el mismo id. de actividad (uno por origen de traza). Se emite la traza de inicio si ActivityTracing está habilitado para el origen de traza.|  
|![Detener traza de actividad](../../../docs/framework/wcf/media/a0493e95-653e-4af8-84a4-4d09a400bc31.gif "a0493e95-653e-4af8-84a4-4d09a400bc31")|Detener traza de actividad: Un seguimiento que marca el final de una actividad. . Contiene el nombre de la actividad. Como diseñador o programador de aplicaciones, debe definir una traza de detención por identificador de actividad por origen de traza. Ningún seguimiento de un origen de traza determinado aparece después del fin de actividad emitido por ese origen de traza, excepto si la granularidad de tiempo del seguimiento no es lo bastante pequeña. Cuando eso pasa, se pueden intercalar dos seguimientos con la misma hora, incluyendo uno de fin, al mostrarlos. Si el id. de actividad se propaga por los orígenes de traza para la correlación de seguimiento, puede ver varios finales para el mismo id. de actividad (uno por origen de traza). Se emite la traza de detención si ActivityTracing está habilitado para el origen de traza.|  
|![Seguimiento de actividad Suspend](../../../docs/framework/wcf/media/6f7f4191-df2b-4592-8998-8379769e2d32.gif "6f7f4191-df2b-4592-8998-8379769e2d32")|Seguimiento de suspensión de actividad: Un seguimiento que marca la hora a una actividad está en pausa. No se emite ningún rastro en una actividad suspendida hasta que se reanuda la actividad. Una actividad suspendida denota que no se está efectuando ningún procesamiento en esa actividad en el área del origen de traza. Los seguimientos de suspensión/reanudación son útiles para perfilar. Se emite el seguimiento de suspensión si ActivityTracing está habilitado para el origen de traza.|  
|![Seguimiento de reanudación de actividad](../../../docs/framework/wcf/media/1060d9d2-c9c8-4e0a-9988-cdc2f7030f17.gif "1060d9d2-c9c8-4e0a-9988-cdc2f7030f17")|Seguimiento de reanudación de actividad: Un seguimiento que marca la hora a que una actividad se reanuda después de que se suspendió. Se pueden volver a emitir seguimientos en esa actividad. Los seguimientos de suspensión/reanudación son útiles para perfilar. Se emite el seguimiento de reanudación si ActivityTracing está habilitado para el origen de traza.|  
|![Transfer](../../../docs/framework/wcf/media/b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5.gif "b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5")|Transferencia: Un seguimiento que se genera cuando el flujo de control lógico se transfiere desde una actividad a otra. La actividad en la que se origina la transferencia puede continuar realizando el trabajo en paralelo a la actividad a la que va la transferencia. Se emite la traza de transferencia si ActivityTracing está habilitado para el origen de traza.|  
|![Transferir desde](../../../docs/framework/wcf/media/1df215cb-b344-4f36-a20d-195999bda741.gif "1df215cb-b344-4f36-a20d-195999bda741")|Transferir desde: Un seguimiento que define a una transferencia desde otra actividad a la actividad actual.|  
|![Transferir a](../../../docs/framework/wcf/media/74255b6e-7c47-46ef-8e53-870c76b04c3f.gif "74255b6e-7c47-46ef-8e53-870c76b04c3f")|Transferir a: Un seguimiento que define a una transferencia de flujo de control lógico desde la actividad actual a otra actividad.|  
  
### <a name="wcf-traces"></a>Seguimiento WCF  
  
|Iconos|Descripción|  
|----------|-----------------|  
|![Seguimiento del registro de mensajes](../../../docs/framework/wcf/media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994-2476-4260-a0db-98948b9af197")|Seguimiento del registro de mensajes: Un seguimiento que se genera cuando se registra un mensaje de WCF mediante la característica de registro de mensajes, cuando el `System.ServiceModel.MessageLogging` origen de seguimiento está habilitado. Al hacer clic en este seguimiento, se muestra el mensaje. Hay cuatro puntos de registro configurables para un mensaje: ServiceLevelSendRequest, TransportSend, TransportReceive y ServiceLevelReceiveRequest, que también se puede especificar el `messageSource` atributo en el seguimiento de registro de mensajes.|  
|![Seguimiento de mensajes recibidos](../../../docs/framework/wcf/media/de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c.gif "de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c")|Seguimiento de mensaje recibido: Un seguimiento que se genera cuando se recibe un mensaje de WCF, si el `System.ServiceModel` origen de seguimiento está habilitado en el nivel de información o detallado. Este seguimiento es esencial para ver la flecha de correlación del mensaje en la actividad **Graph** vista.|  
|![Seguimiento de mensajes enviados](../../../docs/framework/wcf/media/558943c4-17cf-4c12-9405-677e995ac387.gif "558943c4-17cf-4c12-9405-677e995ac387")|Seguimiento de mensajes enviados: Un seguimiento que se genera cuando se envía un mensaje WCF si la `System.ServiceModel` origen de seguimiento está habilitado en el nivel de información o detallado. Este seguimiento es esencial para ver la flecha de correlación del mensaje en la actividad **Graph** vista.|  
  
### <a name="activities"></a>Actividades  
  
|Iconos|Descripción|  
|----------|-----------------|  
|![Activity](../../../docs/framework/wcf/media/wcfc-defaultactivityc.gif "wcfc_defaultActivityc")|Actividad: Indica que la actividad actual es una actividad genérica.|  
|![Actividad raíz](../../../docs/framework/wcf/media/5dc8e0eb-1c32-4076-8c66-594935beaee9.gif "5dc8e0eb-1c32-4076-8c66-594935beaee9")|Actividad raíz: Indica la actividad raíz de un proceso.|  
  
### <a name="wcf-activities"></a>Actividades WCF  
  
|Iconos|Descripción|  
|----------|-----------------|  
|![Actividades del entorno](../../../docs/framework/wcf/media/29fa00ac-cf78-46e5-822d-56222fff61d1.gif "29fa00ac-cf78-46e5-822d-56222fff61d1")|Actividades del entorno: Una actividad que crea, abre o cierra un cliente o host WCF. Los errores que se han producido durante estas fases aparecerán en esta actividad.|  
|![Escuchar actividad](../../../docs/framework/wcf/media/d7b135f6-ec7d-45d7-9913-037ab30e4c26.gif "d7b135f6-ec7d-45d7-9913-037ab30e4c26")|Actividad de escucha: Una actividad que registra los seguimientos relacionados con un agente de escucha. Dentro de esta actividad, podemos ver información del agente de escucha y solicitudes de conexión.|  
|![Recibir actividad de Bytes](../../../docs/framework/wcf/media/2f628580-b80f-45a7-925b-616c96426c0e.gif "2f628580-b80f-45a7-925b-616c96426c0e")|Actividad de recepción de bytes: una actividad que agrupa todos los seguimientos relacionados con la recepción de bytes de entrada en una conexión entre dos extremos. Esta actividad es esencial para ponerse en correlación con actividades de transporte que propagan su identificador de actividad como http.sys. Esta actividad es esencial para ponerse en correlación con actividades de transporte que propagan su id. de actividad como http.sys. En esta actividad aparecerán errores de conexión tales como interrupciones.|  
|![Procesar la actividad de mensaje](../../../docs/framework/wcf/media/wcfc-executionactivityiconc.GIF "wcfc_ExecutionActivityIconc")|Actividad de mensaje de proceso: Una actividad que agrupa los seguimientos relacionados con la creación de un mensaje de WCF. En esta actividad aparecerán errores debidos a una envoltura no válida o a un mensaje incorrecto. Dentro de esta actividad, podemos inspeccionar los encabezados del mensaje para ver si un id. de actividad se propagó a partir del autor de la llamada. Si esto es verdad, cuando transferimos a la actividad de procesamiento de acción (el icono siguiente), también podemos asignar a esa actividad el id. de actividad propagado para la correlación entre el autor de la llamada y los seguimientos del destinatario.|  
|![Seguimiento del registro de mensajes](../../../docs/framework/wcf/media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994-2476-4260-a0db-98948b9af197")|Actividad de acción de proceso: Una actividad que agrupa todos los seguimientos relacionados con una solicitud WCF a través de dos puntos de conexión. Si `propagateActivity` está establecido en `true` en los dos extremos de la configuración, se combinan todos los seguimientos de ambos extremos en una actividad para la correlación directa. Tal actividad contendrá los errores debidos al procesamiento de seguridad o transporte, extendiéndose al límite del código de usuario y de vuelta (si existe una respuesta).|  
|![Procesar la actividad de mensaje](../../../docs/framework/wcf/media/wcfc-executionactivityiconc.GIF "wcfc_ExecutionActivityIconc")|Ejecute la actividad de código de usuario: Una actividad que agrupa los seguimientos del código de usuario para procesar una solicitud.|  
  
## <a name="troubleshooting"></a>Solución de problemas  
 Si no tiene permiso para escribir en el registro, obtendrá el siguiente mensaje de error "Microsoft Service Trace Viewer no se registró en el sistema" cuando se usa el "`svctraceviewer /register`" comando para registrar la herramienta. Si ocurre esto, debe iniciar una sesión con una cuenta que tenga acceso de escritura al registro.  
  
 Además, las herramienta del visor de seguimiento de servicio escribe algunos valores (por ejemplo, filtros personalizados y opciones de filtro) en el archivo SvcTraceViewer.exe.settings de su carpeta de ensamblado. Si no tiene permiso de lectura para el archivo, puede iniciar la herramienta pero no puede cargar los valores.  
  
 Si obtiene el mensaje de error "Se ha producido un error desconocido al procesar uno o más seguimientos" al abrir el archivo .etl, quiere decir que el formato del archivo .etl no es válido.  
  
 Si se abre un registro de seguimiento creado utilizando un sistema operativo árabe, puede observar que el filtro horario no funciona. Por ejemplo, el año 2005 corresponde al año 1427 en el calendario árabe. Sin embargo, el intervalo temporal admitido por el filtro de la herramienta del visor de seguimiento de servicio no admite una fecha anterior a 1752. Esto puede hacer que no pueda seleccionar una fecha correcta en el filtro. Para resolver este problema, puede crear un filtro personalizado (**ver/filtros personalizados**) mediante una expresión XPath para incluir un intervalo de tiempo específico.  
  
## <a name="see-also"></a>Vea también
- [Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas](../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Configuración de la traza](../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [Traza de un extremo a otro](./diagnostics/tracing/end-to-end-tracing.md)
