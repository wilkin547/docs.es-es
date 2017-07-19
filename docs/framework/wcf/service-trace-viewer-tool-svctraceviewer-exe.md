---
title: "Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe) | Microsoft Docs"
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
ms.assetid: 9027efd3-df8d-47ed-8bcd-f53d55ed803c
caps.latest.revision: 55
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 55
---
# Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)
La herramienta del visor de seguimiento de servicio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] le ayuda a analizar seguimientos del diagnóstico generados por [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].El visor de seguimiento de servicio proporciona una manera fácil de combinar, ver y filtrar los mensajes del registro para que así pueda diagnosticar, reparar y comprobar los problemas del servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
## Configurar traza  
 El seguimiento de diagnóstico le proporciona información que muestra lo que está pasando a lo largo de la operación de su aplicación.Como su propio nombre indica, también puede seguir las operaciones desde el origen hasta el destino y en los puntos intermedios.  
  
 Puede configurar el seguimiento usando el archivo de configuración de la aplicación, o bien Web.config para las aplicaciones hospedadas en web o *Appname*.config para las aplicaciones autohospedadas.A continuación se muestra un ejemplo:  
  
```  
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
  
 En este ejemplo, se especifican el nombre y el tipo del agente de escucha de traza.El agente de escucha se denomina `sdt` y se agrega como tipo el agente de escucha de traza estándar de .NET Framework \(System.Diagnostics.XmlWriterTraceListener\).El atributo `initializeData` se usa para establecer el nombre del archivo de registro para ese agente de escucha en `SdrConfigExample.e2e`.Para el archivo de registro, puede sustituir una ruta de acceso completa para un nombre de archivo simple.  
  
 El ejemplo crea un archivo en el directorio raíz denominado SdrConfigExample.e2e.Cuando use el visor de seguimiento para abrir el archivo como se describe en la sección “Abrir y ver los archivos de seguimiento de WCF”, podrá ver todos los mensajes que se han enviado.  
  
 La configuración de `switchValue` controla el nivel de seguimiento.En la siguiente tabla se describen los niveles de traza disponibles.  
  
|Nivel de seguimiento|Descripción|  
|--------------------------|-----------------|  
|Crítico|-   Registra entradas de Fail\-Fast y del Registro de eventos y la información de correlación del seguimiento.A continuación se muestran algunos ejemplos de cuándo se puede utilizar el nivel Crítico:<br />-   Su AppDomain ha fallado debido a una excepción no controlada.<br />-   Su aplicación no se inicia.<br />-   El mensaje que produjo el error se origina en el proceso MyApp.exe.|  
|Error|-   Registra todas las excepciones.Puede utilizar el nivel Error en las situaciones siguientes:<br />-   Su código se ha bloqueado debido a una excepción de conversión no válida.<br />-   Una excepción del tipo “no se ha podido crear el extremo” está haciendo que su aplicación no pueda iniciarse.|  
|Advertencia|-   Existe una condición que puede producir como consecuencia un error o un error crítico.Puede utilizar este nivel en las situaciones siguientes:<br />-   La aplicación está recibiendo más solicitudes que las que permiten su configuración de límites.<br />-   La cola receptora está al 98 por ciento de su capacidad configurada.|  
|Información|-   Se han generado mensajes útiles para supervisar y diagnosticar el estado del sistema, medir el rendimiento o perfilar.Puede utilizar esa información para el diseño de la capacidad y la gestión del rendimiento.Puede utilizar este nivel en las situaciones siguientes:<br />-   Se ha producido un error después de que el mensaje llegase al AppDomain y se deserializase.<br />-   Se ha producido un error mientras se creaba el enlace HTTP.|  
|Detalles|-   Traza del nivel de depuración para el código de usuario y para el servicio.Establezca este nivel cuando:<br />-   No esté seguro de qué método de su código se llamó cuando se produjo el error.<br />-   Tiene configurado un extremo incorrecto y el servicio no se ha podido iniciar porque la entrada en el almacén de reservas está bloqueada.|  
|ActivityTracing|Transmitir eventos entre actividades de procesamiento y componentes.<br /><br /> Este nivel permite a los administradores y programadores poner en correlación las aplicaciones en el mismo dominio de aplicación.<br /><br /> -   Seguimiento de los límites de actividad: iniciar\/detener.<br />-   Seguimiento de las transferencias.|  
  
 Puede utilizar `add` para especificar el nombre y tipo de agente de escucha de traza que desea utilizar.En la configuración del ejemplo, el agente de escucha se denomina `sdt` y se agrega como tipo el agente de escucha de traza de .NET Framework estándar \(`System.Diagnostics.XmlWriterTraceListener`\).Utilice `initializeData` para establecer el nombre del archivo de registro para ese agente de escucha.Además, puede sustituir un nombre de archivo simple por una ruta de acceso completa.  
  
## Utilizar la herramienta de visor de seguimiento de servicio  
  
### Abrir y ver los archivos de seguimiento de WCF  
 El visor de seguimiento de servicio admite tres tipos de archivo:  
  
-   Archivo de traza de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(.svcLog\)  
  
-   Archivo de traza de eventos \(.etl\)  
  
-   Archivo de traza carmesí  
  
 El visor de seguimiento de servicio le permite abrir cualquier archivo de seguimiento compatible, agregar e integrar archivos de seguimiento adicionales o abrir y combinar simultáneamente un grupo de archivos de seguimiento.  
  
##### Para abrir un archivo de seguimiento  
  
1.  Inicie el visor de seguimiento de servicio utilizando una ventana de comandos para navegar a su ubicación de instalación [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(\\Bin de C:\\Program Files\\Microsoft SDKs\\Windows\\v6 .0\) y, a continuación, escriba `SvcTraceViewer.exe`.  
  
> [!NOTE]
>  La herramienta del visor de seguimiento de servicio puede asociar dos tipos de archivo: .svclog y .stvproj.Puede utilizar dos parámetros en línea de comandos para registrar y eliminar del registro las extensiones de archivo.  
>   
>  \/register: registrar la asociación de las extensiones de archivo “.svclog” y “.stvproj” con SvcTraceViewer.exe  
>   
>  \/unregister: eliminar del registro la asociación de las extensiones de archivo “.svclog” y “.stvproj” con SvcTraceViewer.exe  
  
1.  Cuando se inicie el visor de seguimiento de servicio, haga clic en **Archivo** y, a continuación, señale **Abrir**.Navegue hasta la ubicación donde se almacenan sus archivos de seguimiento.  
  
2.  Haga doble clic en el archivo de seguimiento que desea abrir.  
  
    > [!NOTE]
    >  Presione MAYÚS mientras hace clic en varios archivos de seguimiento para seleccionarlos y abrirlos de forma simultánea.El visor de seguimiento de servicio combina el contenido de todos los archivos y los muestra en una vista.Por ejemplo, puede abrir archivos de seguimiento tanto de cliente como de servicio.Esto es útil cuando ha habilitado en la configuración el registro de mensajes y la propagación de la actividad.De esta manera, puede examinar el intercambio de mensajes entre cliente y servicio.También puede arrastrar varios archivos al visor o utilizar la pestaña **Proyecto**.Para obtener información más detallada, vea la sección Administrar proyecto.  
  
3.  Para agregar archivos de seguimiento adicionales a la colección que está abierta, haga clic en **Archivo** y, a continuación, señale **Agregar**.En la ventana que se abre, navegue a la ubicación de los archivos de seguimiento y haga doble clic en el archivo que desea agregar.  
  
> [!CAUTION]
>  No se recomienda cargar un archivo de seguimiento mayor de 200MB.Si intenta cargar un archivo mayor que ese límite, el proceso de carga puede tardar mucho tiempo, dependiendo de su recurso informático.Puede que la herramienta del visor de seguimiento de servicio no responda durante mucho tiempo o que agote la memoria de su equipo.Se recomienda que configure carga parcial para evitarlo.Para obtener más información sobre cómo hacerlo, vea la sección “Cargar archivos de seguimiento grandes”.  
  
#### Seguimiento de eventos y seguimiento carmesí  
 El formato original del visor es el formato de traza de la actividad que emite [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Los seguimientos emitidos en un formato diferente se deben convertir antes de que el visor los muestre.Actualmente, además del formato de traza de la actividad, el visor admite traza de eventos y traza carmesí.  
  
 Al abrir un archivo que no contiene seguimientos de actividad, el visor intenta convertir el archivo.Debe especificar el nombre y la ubicación del archivo que contendrá los datos de seguimiento convertidos.Una vez convertidos los datos, el visor muestra el contenido del nuevo archivo.  
  
> [!NOTE]
>  La conversión requiere espacio en disco para almacenar la información de seguimiento convertida.Antes de iniciar una conversión, asegúrese de tener suficiente espacio en disco para almacenar los datos.De lo contrario, se produce un error en la conversión.  
  
### Administrar proyectos  
 El visor admite proyectos para facilitar la vista de varios archivos de seguimiento.Por ejemplo, si tiene un archivo de seguimiento de cliente y un archivo de seguimiento de servicio, puede agregarlos a un proyecto.Así, cada vez que abra el proyecto, se cargan todos los archivos de seguimiento en el proyecto de manera simultánea.  
  
 Hay dos maneras de administrar los proyectos:  
  
-   En el menú **Archivo**, puede abrir, guardar y cerrar proyectos.  
  
-   En la pestaña **Proyecto** puede agregar archivos a un proyecto.  
  
### Ver seguimiento de WCF  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] emite trazas usando el formato de traza de la actividad.En el modelo de traza de la actividad, los seguimientos individuales están agrupados en actividades según su propósito.El flujo de control lógico se transfiere entre las actividades.Por ejemplo, durante el tiempo que dura una aplicación, aparecen y desaparecen muchas "actividades de envío de mensaje".Para obtener más información sobre cómo ver seguimientos y actividades, y también la interfaz de usuario del visor de seguimiento de servicio, vea [Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas](../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
#### Alternar vistas diferentes  
 El visor de seguimiento de servicio proporciona estas vistas diferentes.Se muestran como pestañas en el panel izquierdo del visor y también se puede acceder a ellas desde el menú **Ver**.  
  
-   Vista de actividad  
  
-   Vista de proyecto  
  
-   Vista de mensaje  
  
-   Vista de gráfico  
  
##### Vista de actividad  
 Una vez abiertos los archivos de seguimiento, puede ver los seguimientos agrupados por actividades en la vista de **Actividad**, en el panel izquierdo.  
  
 La vista de **Actividad** muestra los nombres de la actividad, el número de seguimientos de la actividad, la duración, la hora de inicio y la hora de finalización.  
  
 Haciendo clic en cualquiera de las actividades de la lista, los seguimientos en esta actividad se muestran en el panel de traza a la derecha.Puede seleccionar a continuación un seguimiento para ver sus detalles.  
  
 Puede seleccionar varias actividades presionando las teclas **Ctrl** o **Mayús** y haciendo clic en las actividades deseadas.El panel de traza muestra todos los seguimientos de las actividades seleccionadas.  
  
 Puede hacer doble clic en una actividad para mostrarla en la vista de **Gráfico**.La manera alternativa es seleccionar una actividad y cambiar a la vista **Gráfico**.  
  
> [!NOTE]
>  La actividad "000000000000" es una actividad especial que no se puede mostrar en la vista de Gráfico.Dado que las otras actividades se vinculan a ella, mostrar esta actividad tiene un impacto importante en el rendimiento.  
  
 Puede hacer clic en el título de la columna para ordenar la lista de actividades.Las actividades que contienen seguimientos de advertencia tienen un fondo amarillo y aquéllas que contienen seguimientos de error tienen un fondo rojo.  
  
 Hay diferentes tipos de actividades, y cada tipo corresponde a un icono en el lado izquierdo de cada actividad.Puede consultar la sección Introducción a los iconos de seguimiento para conocer su significado.  
  
##### Vista de proyecto  
 Esta vista le permite administrar los archivos de seguimiento en el proyecto actual.Para obtener información más detallada, vea la sección Administrar proyecto.  
  
##### Vista de gráfico  
 Una de las características más eficaces del visor de seguimiento de servicio es la vista de **Gráfico**, que muestra la información de seguimiento para una actividad determinada en gráficos.Esta opción de gráficos le permite ver la ejecución paso a paso de eventos y las relaciones mutuas entre varias actividades cuando los datos se mueven entre ellas.  
  
 Para cambiar a la vista de **Gráfico**, seleccione una actividad en la vista de **Actividad** y haga clic en la pestaña **Actividad** o seleccione un seguimiento del registro de mensajes en la vista **Mensaje**.Si se cargan varios archivos de seguimiento y la actividad implica seguimientos de más de un archivo, todos los seguimientos pertinentes aparecen en la vista de Gráfico.Al hacer doble clic en las actividades y seguimientos del registro de mensajes también podrá acceder a la vista de **Gráfico**.  
  
 En la vista de **Gráfico**, cada columna vertical representa una actividad y cada bloque de la columna representa un seguimiento.Las actividades se agrupan por proceso \(o subproceso\).Las flechas pequeñas entre las actividades representan las transferencias.Las flechas grandes entre los procesos representan el intercambio de mensajes.La actividad seleccionada siempre aparece en amarillo.  
  
###### Seleccionar seguimientos en el gráfico  
  
1.  Haga clic en un bloque del gráfico.  
  
2.  Utilice las teclas arriba y abajo para seleccionar los seguimientos adyacentes.  
  
3.  Puede ver la información del seguimiento en el Panel de traza y en el Panel de detalles.  
  
###### Expandir o contraer transferencias de la actividad  
 Puede expandir las transferencias de la actividad cuando la actividad seleccionada transfiere a otra actividad.Le permite seguir las transferencias.  
  
 Para expandir o contraer transferencias de la actividad,  
  
1.  Busque el seguimiento de transferencia con un signo "\+" a la izquierda del icono de transferencia.  
  
2.  Haga clic en "\+" o presione **Ctrl** y "\+" en el teclado.  
  
3.  La actividad siguiente aparece en el gráfico.  
  
4.  Aparece “\-” a la izquierda del icono de transferencia.Si hace clic en el signo “\-” o presiona Ctrl y “\-”, se contrae la transferencia de la actividad.  
  
> [!NOTE]
>  Cuando una actividad tiene varias transferencias y expande una de ellas, se muestran las actividades que llevan a la nueva actividad desde la actividad raíz.Estas nuevas actividades se muestran en formato contraído.Si desea ver los detalles de estas actividades, expándalas verticalmente haciendo clic en el icono de expandir, en el encabezado del gráfico.  
  
###### Expandir o contraer verticalmente las actividades  
 El visor contrae las actividades para así ocultar detalles innecesarios en el gráfico de la actividad.En una actividad contraída no se muestran los seguimientos individuales.Sólo aparecen las transferencias de seguimiento.Si desea ver todas las trazas en una actividad, expanda verticalmente la actividad haciendo clic en el símbolo de expansión de la actividad situado en el encabezado del gráfico.  
  
 Para expandir o contraer verticalmente las actividades,  
  
1.  Haga clic en el icono “\+” en el encabezado de la actividad para expandir verticalmente la actividad.  
  
2.  Tenga en cuenta que todos los seguimientos se muestran en el gráfico.  
  
3.  Haga clic en el icono “\-” en el encabezado de la actividad para contraer verticalmente la actividad.  
  
4.  Tenga en cuenta que sólo se muestran en la actividad las transferencias importantes, registros de mensajes y seguimientos de advertencia y de excepción.  
  
###### Opciones  
 Puede seleccionar dos opciones en el menú **Opción** en la vista de gráfico.  
  
-   Mostrar seguimientos de límite de la actividad que, cuando se desactiva, omite los seguimientos del límite de la actividad en el gráfico.  
  
-   Mostrar seguimientos detallados sin mensaje que, cuando se desactiva, omite todos los seguimientos de nivel detallados, excepto los seguimientos de mensajes.En la mayoría de los casos, los seguimientos de nivel detallados son menos importantes para el análisis.Esta opción es útil cuando no desea analizar los seguimientos de nivel detallados y sólo desea centrarse en seguimientos más importantes.  
  
###### Modo de diseño  
 El visor tiene dos modos de diseño: **Proceso** y **Subproceso**.Esta configuración define la unidad más grande de organización.El modo de diseño predeterminado es el de **Proceso**, es decir, las actividades están agrupadas por procesos en el gráfico.  
  
###### Lista de ejecución  
 Puede seleccionar qué proceso o subproceso de este menú desplegable se va a mostrar en el gráfico.Por ejemplo, si tiene abiertos los archivos de seguimiento de dos clientes \(A y B\) y un servicio, y sólo desea mostrar el servicio y el cliente A en el gráfico, puede anular la selección del cliente B en la lista.  
  
#### Ver detalles del seguimiento  
 Para ver un detalle del seguimiento, seleccione un seguimiento en el panel de traza.Los detalles se muestran en el Panel de detalles.  
  
##### Panel de traza  
 El panel superior derecho en el visor de seguimiento de servicio es el panel de traza.Contiene una lista de todos los seguimientos en la actividad seleccionada con información adicional, por ejemplo el nivel de seguimiento, el identificador de subproceso y el nombre del proceso.  
  
 Puede copiar el XML sin formato del seguimiento al Portapapeles haciendo clic con el botón secundario en un seguimiento y seleccionando **Copiar seguimiento a Portapapeles**.  
  
##### Panel de detalles  
 El panel inferior izquierdo en el visor de seguimiento de servicio es el Panel de detalles.Tiene tres pestañas para ver los detalles de seguimiento.  
  
 La vista **Con formato** muestra la información de una manera más organizada.Contiene una lista de todos los elementos XML conocidos en tablas y árboles, por lo que será más fácil leer y entender la información.  
  
 La vista **XML** muestra XML que corresponden al seguimiento seleccionado.Permite resaltar y colorear la sintaxis.Al utilizar **Buscar** para buscar en cadenas, resalta los resultados de la búsqueda.  
  
 La vista de **Mensaje** muestra la parte del mensaje del XML en los seguimientos del registro de mensajes.No se puede ver si selecciona un seguimiento sin mensaje.  
  
### Filtrar los seguimientos de WCF  
 Para facilitar el análisis de seguimientos, puede filtrarlos de las maneras siguientes:  
  
-   La barra de herramientas de filtro proporciona el acceso a los filtros predefinidos y personalizados.Se puede habilitar en el menú **Ver**.  
  
-   El filtro predefinido del visor se puede utilizar para filtrar selectivamente partes de los seguimientos de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Se establece de forma predeterminada que todos los seguimientos de infraestructura puedan pasar.La configuración de este filtro se define en el submenú **Opciones de filtro**, en el menú **Ver**.  
  
-   Los filtros del XPath personalizados les dan a los usuarios el control completo sobre cómo filtrar.Se pueden definir en **Filtro personalizado**, en el menú **Ver**.  
  
 Sólo se muestran los seguimientos que atraviesan todos los filtros.  
  
#### Utilizar la barra de herramientas del filtro  
 La barra de herramientas del filtro aparece en la parte superior de la herramienta.Si no aparece, puede activarla en el menú **Ver**.La barra tiene tres componentes:  
  
-   Buscar: **Buscar** define el tema u objeto que se ha de buscar en la operación de filtro.Por ejemplo, si desea buscar todos los seguimientos que se emitieron durante el proceso X, escriba en este campo X y en el campo  **Buscar en** el “nombre del proceso”.Este campo cambia a un control de selector DateTime cuando se selecciona un filtro basado en tiempo.  
  
-   Buscar en: este campo define el tipo de filtro que se va a aplicar.  
  
-   Nivel: el valor de nivel define el nivel de seguimiento mínimo permitido por el filtro.Por ejemplo, si se fija el nivel en “Error y arriba”, sólo se muestran los seguimientos en el nivel error y crítico.Este filtro se combina con los criterios especificados en Buscar y Buscar en.  
  
 El botón **Filtrar ahora** inicia la operación del filtro.Algunos filtros, sobre todo cuando se aplican a un conjunto de datos grande, tardan un buen rato en terminar.Puede cancelar la operación de filtrado presionando el botón **Detener** que aparece en la barra de estado en el menú **Operaciones**.  
  
 El botón **Borrar** restablece los filtros predefinidos y personalizados para permitir que pasen todos los seguimientos.  
  
#### Opciones de filtro  
 El visor puede quitar de la vista automáticamente los seguimientos [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Puede quitar selectivamente seguimientos emitidos por áreas concretas de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], por ejemplo, mediante la eliminación de la vista de seguimientos relacionados con la transacción.  
  
 La configuración de este filtro se define en el submenú **Opciones de filtro**, en el menú **Ver**.  
  
#### Filtros personalizados  
 Si está familiarizado con el lenguaje XML Path Language \(XPath\), puede utilizarlo y así construir filtros personalizados para buscar en los datos de seguimiento cualquier elemento XML que le interese.Se puede acceder a los filtros a través de la barra de herramientas de filtro.  
  
 Los filtros personalizados pueden incluir parámetros.También puede importar filtros personalizados que ya existan.  
  
##### Crear un filtro personalizado  
 Los filtros se pueden crear de dos maneras:  
  
###### Crear un filtro personalizado mediante el Asistente para plantillas  
 Puede hacer clic en un seguimiento existente y crear un filtro basado en la estructura del seguimiento.En este ejemplo se crea un filtro personalizado basado en un id. de subproceso.  
  
1.  En el panel de traza, en la parte superior derecha del visor, seleccione un seguimiento que incluya el elemento que desea filtrar.  
  
2.  Haga clic en el botón **Crear filtro personalizado** situado en la parte superior del panel de traza.  
  
3.  En el cuadro de diálogo que aparece, escriba un nombre para su filtro.En este ejemplo, escriba `Thread ID`.También puede proporcionar una descripción de su filtro.  
  
4.  La vista de árbol a la izquierda muestra la estructura del registro de seguimiento que seleccionó en el paso 1.Vaya al elemento para el que desea crear una condición.En este ejemplo, vaya a ThreadID, que se encuentra en el nodo XPath: \/E2ETraceEvent\/System\/Execution\/@ThreadID.Haga doble clic en el atributo ThreadID en la vista de árbol.Esto crea una expresión para el atributo a la derecha del diálogo.  
  
5.  Cambie el campo de parámetro para la condición ThreadID de Ninguno a “{0}”.Este paso permite configurar el valor de ThreadID cuando se aplica el filtro.\(Vea la sección Cómo aplicar un filtro\) Puede definir hasta cuatro parámetros.Las condiciones se combinan mediante el operador O.  
  
6.  Haga clic en **Aceptar** para crear el filtro.  
  
> [!NOTE]
>  Una vez que se haya creado un filtro mediante el Asistente para plantillas, solo se podrá editar manualmente.No es posible activar el Asistente para un filtro que se ha creado previamente.Además, las condiciones de un filtro de XPath creado mediante el Asistente para plantillas se combinan con el operador O.Si necesita una operador Y, puede modificar la expresión del filtro una vez haya sido creado.  
  
###### Crear manualmente un filtro personalizado  
 El menú Filtros personalizados le permite escribir manualmente los filtros de XPath.  
  
1.  En el menú Ver, haga clic en el elemento de menú **Filtros personalizados**.  
  
2.  En el diálogo que aparece, haga clic en **Nuevo.**  
  
3.  Como mínimo especifique un nombre de filtro y una expresión XPath.  
  
4.  Haga clic en **Aceptar**.  
  
###### Aplicar un filtro personalizado  
 Una vez creado un filtro personalizado, puede acceder a él a través de la barra de herramientas de filtro.Seleccione el filtro que desee aplicar en el campo **Buscar en** de la barra de herramientas de filtro.Para el ejemplo anterior, seleccione “Thread ID”.  
  
1.  Especifique el valor que está buscando en el campo **Buscar**.En este ejemplo, escriba el id. del subproceso que desea buscar.  
  
2.  Haga clic en **Filtrar ahora** y observe el resultado de la operación.  
  
 Si su filtro usa varios parámetros, escríbalos usando ';' como separador en el campo **Buscar**.Por ejemplo, la cadena siguiente define tres parámetros: ‘1;findValue;text’.El visor aplica ‘1’ al parámetro {0} del filtro.‘findValue’ y ‘text’ se aplican a {1} y {2} respectivamente.  
  
###### Compartir filtros personalizados  
 Los filtros personalizados se pueden compartir entre sesiones diferentes y usuarios diferentes.Puede exportar los filtros a un archivo de definición e importar este archivo en otra ubicación.  
  
 Para importar un filtro personalizado:  
  
1.  En el menú **Ver**, haga clic en **Filtros personalizados**.  
  
2.  En el cuadro de diálogo que aparece, haga clic en el botón **Importar**.  
  
3.  Navegue al archivo de filtro personalizado \(.stvcf\), haga clic en el archivo y haga clic en el botón **Abrir**.  
  
 Para exportar un filtro personalizado:  
  
1.  En el menú Ver, haga clic en **Filtros personalizados**.  
  
2.  En el cuadro de diálogo que aparece, seleccione el filtro que desea exportar.  
  
3.  Haga clic en el botón **Exportar**.  
  
4.  Especifique el nombre y la ubicación del archivo de definición de filtro personalizado \(.stvcf\) y haga clic en el botón **Guardar**.  
  
> [!NOTE]
>  Estos filtros personalizados se pueden importar y exportar sólo desde el visor de seguimiento de servicio.No se pueden leer con otras herramientas.  
  
### Buscar datos  
 El visor proporciona las maneras siguientes de buscar datos:  
  
-   La barra de herramientas Buscar proporciona un acceso rápido a las opciones de búsqueda más comunes.  
  
-   El cuadro de diálogo Buscar proporciona más opciones de búsqueda.Se puede acceder a él a través del menú **Editar** o mediante la combinación de teclas Ctrl \+ F.  
  
 La barra de herramientas Buscar aparece en la parte superior del visor.Si no aparece, puede activarla en el menú **Ver**.La barra tiene dos componentes:  
  
-   Buscar: le permite escribir una palabra clave de búsqueda.  
  
-   Buscar en: le permite introducir un área de búsqueda.Puede seleccionar buscar en todas las actividades o sólo en la actividad actual.  
  
 El cuadro de diálogo de la búsqueda proporciona dos opciones adicionales:  
  
-   Buscar destino:  
  
    -   La opción “datos de registro sin procesar” busca la palabra clave en todos los datos sin procesar.  
  
    -   Las opciones “texto XML” y “atributo XML” solo buscan en elementos XML.  
  
    -   La opción “Mensaje registrado” solo busca la palabra clave en mensajes.  
  
-   Ignorar la actividad raíz: la búsqueda ignora las trazas en la actividad “000000000000”.De esta forma, se mejora el rendimiento de los archivos de seguimiento grandes cuando la actividad raíz tiene miles de seguimientos, la mayoría de los cuales son transferencias.  
  
### Navegar por los seguimientos  
 Dado que los seguimientos se graban paso a paso durante el tiempo de ejecución de la aplicación, navegar por los seguimientos puede ayudarle a depurar su aplicación.El visor de seguimiento de servicio proporciona varias maneras de navegar por los seguimientos.  
  
#### Paso hacia delante o hacia atrás  
 Si considera cada seguimiento como una línea de código en el programa, ir hacia delante es muy similar al “paso a paso por procedimientos” en el entorno de desarrollo integrado de Visual Studio \(IDE\).La diferencia radica en que también puede ir hacia atrás en los seguimientos.Avanzar paso a paso significa ir a la traza siguiente de la actividad.  
  
-   Avanzar paso a paso: use el menú **Actividad** o presione “F10”.También puede usar la tecla de dirección “abajo” del panel de traza.  
  
-   Retroceder paso a paso: use el menú **Actividad** o presione “F9”.También puede usar la tecla de dirección “arriba” del panel de seguimiento.  
  
> [!NOTE]
>  Esto puede llevarlo a una actividad que ocurre en un proceso diferente o incluso en un equipo diferente, porque los mensajes de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] pueden llevar identificadores de actividad que abarcan varias máquinas.  
  
#### Seguir la transferencia  
 Las trazas de transferencia son trazas especiales en el archivo de seguimiento.Una actividad puede transferirse a otra actividad mediante un seguimiento de transferencia.Por ejemplo, la “actividad A” puede transferir a la “actividad B”.En este caso, hay una traza de transferencia en la “Actividad A” con el nombre “A: actividad” y el icono de transferencia.Esta traza de transferencia es un vínculo entre las dos trazas.En la “actividad B”, podría haber también una traza de transferencia al final de la actividad para transferir de vuelta a la “actividad A”.Esto es similar a las llamadas de función en programas: A llama a B, a continuación, B devuelve.  
  
 “Seguir transferencia” es similar a la opción “Ir a” en un depurador.Sigue la transferencia de A a B.No tiene ningún efecto en otros seguimientos.  
  
 Hay dos maneras de seguir una transferencia: con el mouse o con el teclado:  
  
-   Con el mouse: haga doble clic en el seguimiento de transferencia del panel de seguimiento.  
  
-   Con el teclado: seleccione una traza de transferencia y use “Seguir transferencia” en el menú **Actividad** o presione “F11”  
  
> [!NOTE]
>  En muchos casos, cuando la actividad A se transfiere a la actividad B, la actividad A espera hasta que la actividad B se vuelva a transferir a la actividad A.Esto significa que la actividad A no tiene ningún seguimiento registrado durante el período en el que se estaba haciendo un seguimiento activo de la actividad A.Sin embargo, también es posible que la actividad A no espere y continúe registrando los seguimientos.También es posible que la actividad B no se transfiera de nuevo a la actividad A.Por consiguiente, las transferencias de actividad siguen siendo diferentes de las llamadas a funciones en este sentido.Es más fácil entender las transferencias de actividad en la vista de gráfico.  
  
#### Pasar a la transferencia siguiente o anterior  
 Cuando analice la actividad actual, o las actividades seleccionadas cuando se han seleccionado varias actividades, puede que desee buscar rápidamente las actividades a las que transfiere.“Pasar a la siguiente transferencia” le permite buscar la siguiente traza de transferencia en la actividad.En cuanto haya encontrado la traza de transferencia, puede usar “Seguir transferencia" para ir a la actividad siguiente.  
  
-   Pasar a la transferencia siguiente: use el menú **Actividad** o presione “Ctrl \+ F10”.  
  
-   Pasar a la transferencia anterior: use el menú **Actividad** o presione “Ctrl \+ F9”.  
  
#### Navegar en la vista del gráfico  
 Aunque navegar por el panel de actividad y el panel de traza sea similar a depurar, usar la vista del **Gráfico** proporciona una experiencia de navegación mucho mejor.Vea la sección “Vista de gráfico” para obtener más información.  
  
### Cargar archivos de seguimiento grandes  
 Algunos archivos de seguimiento pueden ser muy grandes.Por ejemplo, si habilita la traza en nivel “detallado”, el archivo de seguimiento resultante que vaya a ejecutarse unos minutos puede ser fácilmente de cientos de megabytes o incluso mayor, según la velocidad de red y el modelo de comunicación.  
  
 Abrir un archivo de seguimiento muy grande en el visor de seguimiento de servicio puede repercutir negativamente en el rendimiento del sistema.La velocidad de carga y el tiempo de respuesta después de haber terminado la carga pueden ser lentos.La velocidad real difiere de vez en cuando, según su configuración del hardware.En la mayoría de los PC, cargar un archivo de seguimiento de más de 200 MB repercute seriamente en el rendimiento.Y en el caso de archivos de seguimiento de más de 1 GB, la herramienta puede agotar toda la memoria disponible o no responder durante bastante tiempo.  
  
 Para evitar una carga y tiempo de respuesta lentos al analizar archivos de seguimiento grandes, el visor de seguimiento de servicio cuenta con una característica llamada “carga parcial”, con la cual se cargan partes pequeñas del seguimiento de una en una.Por ejemplo, puede darse el caso de que tenga un archivo de seguimiento de más de un 1 GB y que esté ejecutándose durante varios días en el servidor.Cuando hayan ocurrido algunos errores y desee analizar el seguimiento, no es necesario abrir todo el archivo de seguimiento.En su lugar, puede cargar los seguimientos pertenecientes al período de tiempo en el que se puede haber producido el error.Dado que el área es menor, la herramienta de visor de seguimiento de servicio puede cargar el archivo más rápido, e identificar así los errores utilizando un conjunto menor de datos.  
  
#### Habilitar la carga parcial  
 No necesita habilitar manualmente la carga parcial.Si el tamaño total de los archivos de seguimiento que intenta cargar supera los 40 MB, el visor de seguimiento de servicio muestra automáticamente un diálogo de carga parcial para que usted seleccione la parte que desea cargar.  
  
> [!NOTE]
>  Dado que puede que los seguimientos no se distribuyan de manera uniforme en el intervalo de tiempo, la longitud del período de tiempo que especifique en la barra de herramientas de carga parcial puede que no sea proporcional al tamaño de carga que se muestra.El tamaño de carga real puede ser menor que el tamaño estimado en el diálogo de carga parcial.  
  
#### Ajustar la carga parcial  
 Después de haber cargado parcialmente el archivo de seguimiento, puede cambiar el conjunto de datos que se está cargando.Puede hacer esto ajustando la barra de herramientas de carga parcial en la parte superior del visor.  
  
1.  Mueva la barra de herramientas con el mouse o escriba la hora de inicio y finalización.  
  
2.  Haga clic en el botón **Ajustar**.  
  
## Introducción a los iconos de seguimiento  
 A continuación, se muestra una lista de los iconos que la herramienta Visor de seguimiento de servicios usa en las vistas de **Actividad** y del **Gráfico**, así como en el panel **Seguimiento** para representar elementos diferentes.  
  
> [!NOTE]
>  Algunos seguimientos que no están categorizados \(por ejemplo, “se cierra un mensaje”\) no tienen ningún icono.  
  
### Seguimientos de actividad  
  
|Icono|Descripción|  
|-----------|-----------------|  
|![Seguimiento de advertencia](../../../docs/framework/wcf/media/7457c4ed-8383-4ac7-bada-bcb27409da58.gif "7457c4ed\-8383\-4ac7\-bada\-bcb27409da58")|Traza de advertencia: traza que se emite en el nivel de advertencia|  
|![Seguimiento de errores](../../../docs/framework/wcf/media/7d908807-4967-4f6d-9226-d52125db69ca.gif "7d908807\-4967\-4f6d\-9226\-d52125db69ca")|Seguimiento de error: un seguimiento que se emite en el nivel de error.|  
|![Seguimiento de inicio de actividad:](../../../docs/framework/wcf/media/8a728f91-5f80-4a95-afe8-0b6acd6e0317.gif "8a728f91\-5f80\-4a95\-afe8\-0b6acd6e0317")|Seguimiento de inicio de actividad: un seguimiento que marca el principio de una actividad.Contiene el nombre de la actividad.Como diseñador o programador de aplicaciones, debería definir un seguimiento de inicio de actividad por id. de actividad, por proceso o subproceso.<br /><br /> Si el id. de actividad se propaga por los orígenes de traza para la correlación de seguimiento, puede ver varios inicios para el mismo id. de actividad \(uno por origen de traza\).Se emite la traza de inicio si ActivityTracing está habilitado para el origen de traza.|  
|![Seguimiento de detención de actividad](../../../docs/framework/wcf/media/a0493e95-653e-4af8-84a4-4d09a400bc31.gif "a0493e95\-653e\-4af8\-84a4\-4d09a400bc31")|Detener traza de actividad: una traza que marca el fin de una actividad..Contiene el nombre de la actividad.Como diseñador o programador de aplicaciones, debe definir una traza de detención por identificador de actividad por origen de traza.Ningún seguimiento de un origen de traza determinado aparece después del fin de actividad emitido por ese origen de traza, excepto si la granularidad de tiempo del seguimiento no es lo bastante pequeña.Cuando eso pasa, se pueden intercalar dos seguimientos con la misma hora, incluyendo uno de fin, al mostrarlos.Si el id. de actividad se propaga por los orígenes de traza para la correlación de seguimiento, puede ver varios finales para el mismo id. de actividad \(uno por origen de traza\).Se emite la traza de detención si ActivityTracing está habilitado para el origen de traza.|  
|![Seguimiento de suspensión de actividad](../../../docs/framework/wcf/media/6f7f4191-df2b-4592-8998-8379769e2d32.gif "6f7f4191\-df2b\-4592\-8998\-8379769e2d32")|Seguimiento de suspensión de actividad: un seguimiento que marca la hora que se pausa una actividad.No se emite ningún rastro en una actividad suspendida hasta que se reanuda la actividad.Una actividad suspendida denota que no se está efectuando ningún procesamiento en esa actividad en el área del origen de traza.Los seguimientos de suspensión\/reanudación son útiles para perfilar.Se emite el seguimiento de suspensión si ActivityTracing está habilitado para el origen de traza.|  
|![Seguimiento de reanudación de actividad](../../../docs/framework/wcf/media/1060d9d2-c9c8-4e0a-9988-cdc2f7030f17.gif "1060d9d2\-c9c8\-4e0a\-9988\-cdc2f7030f17")|Seguimiento de reanudación de actividad: un seguimiento que marca la hora a la que se reanuda una actividad una vez suspendida.Se pueden volver a emitir seguimientos en esa actividad.Los seguimientos de suspensión\/reanudación son útiles para perfilar.Se emite el seguimiento de reanudación si ActivityTracing está habilitado para el origen de traza.|  
|![Transferir](../../../docs/framework/wcf/media/b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5.gif "b2d9850e\-f362\-4ae5\-bb8d\-9f6f3ca036a5")|Transferencia: un seguimiento que se emite cuando el flujo de control lógico se transfiere de una actividad a otra.La actividad en la que se origina la transferencia puede continuar realizando el trabajo en paralelo a la actividad a la que va la transferencia.Se emite la traza de transferencia si ActivityTracing está habilitado para el origen de traza.|  
|![Transferir desde](../../../docs/framework/wcf/media/1df215cb-b344-4f36-a20d-195999bda741.gif "1df215cb\-b344\-4f36\-a20d\-195999bda741")|Transferir de: un seguimiento que define una transferencia desde otra actividad a la actividad actual.|  
|![Transferir a](../../../docs/framework/wcf/media/74255b6e-7c47-46ef-8e53-870c76b04c3f.gif "74255b6e\-7c47\-46ef\-8e53\-870c76b04c3f")|Transferir a: un seguimiento que define una transferencia de flujo de control lógico desde la actividad actual a otra actividad.|  
  
### Seguimiento WCF  
  
|Icono|Descripción|  
|-----------|-----------------|  
|![Seguimiento de registro de mensajes](../../../docs/framework/wcf/media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994\-2476\-4260\-a0db\-98948b9af197")|Seguimiento de registro de mensajes: un seguimiento que se emite cuando la característica de registro de mensajes registra un mensaje de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] cuando el origen de traza de `System.ServiceModel.MessageLogging` está habilitado.Al hacer clic en este seguimiento, se muestra el mensaje.Hay cuatro puntos de registro configurables para un mensaje: ServiceLevelSendRequest, TransportSend, TransportReceive y ServiceLevelReceiveRequest, que también pueden ser especificados por el atributo `messageSource` en el seguimiento del registro de mensajes.|  
|![Seguimiento de mensajes recibidos](../../../docs/framework/wcf/media/de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c.gif "de4f586c\-c5dd\-41ec\-b1c3\-ac56b4dfa35c")|Seguimiento de mensaje recibido: un seguimiento que se emite cuando se recibe un mensaje [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], si el origen de traza `System.ServiceModel` está habilitado en los niveles de Información o Detallado.Este seguimiento es esencial para ver la flecha de correlación de mensaje en la vista de **Gráfico** de actividad.|  
|![Seguimiento de mensajes enviados](../../../docs/framework/wcf/media/558943c4-17cf-4c12-9405-677e995ac387.gif "558943c4\-17cf\-4c12\-9405\-677e995ac387")|Seguimiento de mensaje enviado: un seguimiento que se emite cuando se envía un mensaje [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], si el origen de traza `System.ServiceModel` está habilitado en los niveles de Información o Detallado.Este seguimiento es esencial para ver la flecha de correlación de mensaje en la vista de **Gráfico** de actividad.|  
  
### Actividades  
  
|Icono|Descripción|  
|-----------|-----------------|  
|![Actividad](../../../docs/framework/wcf/media/wcfc-defaultactivityc.gif "wcfc\_defaultActivityc")|Actividad: indica que la actividad actual es una actividad genérica.|  
|![Actividad raíz](../../../docs/framework/wcf/media/5dc8e0eb-1c32-4076-8c66-594935beaee9.gif "5dc8e0eb\-1c32\-4076\-8c66\-594935beaee9")|Actividad raíz: indica la actividad raíz de un proceso.|  
  
### Actividades WCF  
  
|Icono|Descripción|  
|-----------|-----------------|  
|![Actividad del entorno](../../../docs/framework/wcf/media/29fa00ac-cf78-46e5-822d-56222fff61d1.gif "29fa00ac\-cf78\-46e5\-822d\-56222fff61d1")|Actividad de entorno: una actividad que crea, abre o cierra un host o un cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Los errores que se han producido durante estas fases aparecerán en esta actividad.|  
|![Actividad de escucha](../../../docs/framework/wcf/media/d7b135f6-ec7d-45d7-9913-037ab30e4c26.gif "d7b135f6\-ec7d\-45d7\-9913\-037ab30e4c26")|Actividad de escucha: una actividad que registra los seguimientos relacionados con un agente de escucha.Dentro de esta actividad, podemos ver información del agente de escucha y solicitudes de conexión.|  
|![Actividad de recepción de bytes](../../../docs/framework/wcf/media/2f628580-b80f-45a7-925b-616c96426c0e.gif "2f628580\-b80f\-45a7\-925b\-616c96426c0e")|Actividad de recepción de bytes: agrupa todos los seguimientos relacionados con la recepción de bytes de entrada en una conexión entre dos extremos.Esta actividad es esencial para ponerse en correlación con actividades de transporte que propagan su id. de actividad como http.sys.En esta actividad aparecerán errores de conexión tales como interrupciones.|  
|![Actividad de procesamiento de mensajes](../../../docs/framework/wcf/media/wcfc-executionactivityiconc.GIF "wcfc\_ExecutionActivityIconc")|Actividad de procesamiento de mensajes: una actividad que agrupa los seguimientos relacionados con crear un mensaje [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].En esta actividad aparecerán errores debidos a una envoltura no válida o a un mensaje incorrecto.Dentro de esta actividad, podemos inspeccionar los encabezados del mensaje para ver si un id. de actividad se propagó a partir del autor de la llamada.Si esto es verdad, cuando transferimos a la actividad de procesamiento de acción \(el icono siguiente\), también podemos asignar a esa actividad el id. de actividad propagado para la correlación entre el autor de la llamada y los seguimientos del destinatario.|  
|![Seguimiento de registro de mensajes](../../../docs/framework/wcf/media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994\-2476\-4260\-a0db\-98948b9af197")|Actividad de procesamiento de acción: actividad que agrupa todas las trazas relacionadas con una solicitud de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a través de dos extremos.Si `propagateActivity` está establecido en `true` en los dos extremos de la configuración, se combinan todos los seguimientos de ambos extremos en una actividad para la correlación directa.Tal actividad contendrá los errores debidos al procesamiento de seguridad o transporte, extendiéndose al límite del código de usuario y de vuelta \(si existe una respuesta\).|  
|![Actividad de procesamiento de mensajes](../../../docs/framework/wcf/media/wcfc-executionactivityiconc.GIF "wcfc\_ExecutionActivityIconc")|Actividad de ejecución de código de usuario: una actividad que agrupa seguimientos de código de usuario para procesar una solicitud.|  
  
## Solución de problemas  
 Si no tiene el permiso para escribir en el registro, obtendrá el mensaje de error siguiente que "El visor de seguimiento de servicio de Microsoft no está registrado en el sistema" al utilizar el comando "`svctraceviewer /register`" para registrar la herramienta.Si ocurre esto, debe iniciar una sesión con una cuenta que tenga acceso de escritura al registro.  
  
 Además, las herramienta del visor de seguimiento de servicio escribe algunos valores \(por ejemplo, filtros personalizados y opciones de filtro\) en el archivo SvcTraceViewer.exe.settings de su carpeta de ensamblado.Si no tiene permiso de lectura para el archivo, puede iniciar la herramienta pero no puede cargar los valores.  
  
 Si obtiene el mensaje de error "Se ha producido un error desconocido al procesar uno o más seguimientos" al abrir el archivo .etl, quiere decir que el formato del archivo .etl no es válido.  
  
 Si se abre un registro de seguimiento creado utilizando un sistema operativo árabe, puede observar que el filtro horario no funciona.Por ejemplo, el año 2005 corresponde al año 1427 en el calendario árabe.Sin embargo, el intervalo temporal admitido por el filtro de la herramienta del visor de seguimiento de servicio no admite una fecha anterior a 1752.Esto puede hacer que no pueda seleccionar una fecha correcta en el filtro.Para resolver este problema, puede crear un filtro personalizado \(**Ver\/Filtros personalizados**\) utilizando una expresión XPath para incluir un intervalo temporal concreto.  
  
## Vea también  
 [Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas](../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)   
 [Configurar seguimiento](../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)   
 [Activity Tracing and Propagation for End\-To\-End Trace Correlation](http://msdn.microsoft.com/es-es/2c11a905-64f8-47b5-bae5-a74fc666137e)