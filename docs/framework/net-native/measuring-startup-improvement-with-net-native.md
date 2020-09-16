---
title: Medir la mejora del inicio con .NET Native
ms.date: 03/30/2017
ms.assetid: c4d25b24-9c1a-4b3e-9705-97ba0d6c0289
ms.openlocfilehash: 5d20fa77ee299065ced406bf8cd531b8c54b6c33
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540893"
---
# <a name="measuring-startup-improvement-with-net-native"></a>Medir la mejora del inicio con .NET Native
.NET Native mejora significativamente el tiempo de inicio de las aplicaciones. Esta mejora es especialmente palpable en los dispositivos portátiles de baja potencia y con aplicaciones complejas. Este tema sirve de introducción a la instrumentación básica necesaria para medir esta mejora de inicio.  
  
 Para facilitar las investigaciones de rendimiento, .NET Framework y Windows usan un marco de trabajo de eventos llamado Seguimiento de eventos para Windows (ETW), que permite que la aplicación avise a las herramientas cuando se produzcan eventos. Luego, puede usar una herramienta denominada PerfView para ver y analizar los eventos ETW fácilmente. En este tema se explican los procedimientos para:  
  
- Usar la clase <xref:System.Diagnostics.Tracing.EventSource> para emitir eventos.  
  
- Usar PerfView para recopilar esos eventos.  
  
- Usar PerfView para mostrar esos eventos.  
  
## <a name="using-eventsource-to-emit-events"></a>Usar EventSource para emitir eventos  
 <xref:System.Diagnostics.Tracing.EventSource> proporciona una clase base desde la que se puede crear un proveedor de eventos personalizado. Generalmente, se crea una subclase de <xref:System.Diagnostics.Tracing.EventSource> y se ajustan los métodos `Write*` con los métodos de evento propios. Se suele usar un patrón singleton para cada <xref:System.Diagnostics.Tracing.EventSource>.  
  
 Por ejemplo, la clase en el siguiente ejemplo se puede usar para medir dos características de rendimiento:  
  
- El tiempo transcurrido hasta que se llamó al constructor de clase `App`.  
  
- El tiempo transcurrido hasta que se llamó al constructor `MainPage`.  
  
 [!code-csharp[ProjectN_ETW#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_etw/cs/etw1.cs#1)]  
  
 Hay algunos aspectos que debemos tener en cuenta aquí. En primer lugar, un singleton se crea en `AppEventSource.Log`. Esa instancia se utilizará para todos los registros. En segundo lugar, cada método de evento tiene un <xref:System.Diagnostics.Tracing.EventAttribute>. Esto ayuda a las herramientas a asociar el índice del método <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> con el método al que se llamó en `AppEventSource`.  
  
 Observe que estos eventos son solamente ilustrativos. La mayor parte del código de la aplicación se ejecutará después de estos eventos. Conviene saber qué eventos en el código se corresponden con las interacciones de usuario, medirlos y mejorar dichas referencias. Además, los eventos en sí registran una sola instancia en el tiempo. A menudo resulta útil tener emparejados eventos de inicio y detención para cada operación. Al examinar el inicio de la aplicación, el evento de inicio suele ser el evento "Procesar/Iniciar" que el sistema operativo emite.  
  
 Por ejemplo, supongamos que va a crear un lector RSS. Algunas ubicaciones interesantes donde registrar un evento son las siguientes:  
  
- Cuando la página principal se representa por primera vez.  
  
- Cuando se deserializan casos de RSS antiguos del almacenamiento local.  
  
- Cuando la aplicación empieza a sincronizar nuevos casos.  
  
- Cuando la aplicación ha terminado de sincronizar nuevos casos.  
  
 Instrumentar una aplicación es sencillo: basta con llamar al método apropiado en la clase derivada. Usando `AppEventSource` del ejemplo anterior, una aplicación se puede instrumentar del siguiente modo:  
  
 [!code-csharp[ProjectN_ETW#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_etw/cs/etw2.cs#2)]  
  
 Cuando la aplicación esté instrumentada, estará listo para recopilar eventos.  
  
## <a name="gathering-events-with-perfview"></a>Recopilación de eventos con PerfView  
 PerfView usa eventos ETW para ayudarle a realizar todo tipo de investigaciones de rendimiento en la aplicación. También incluye una GUI de configuración que permite activar o desactivar el registro de diferentes tipos de eventos. PerfView es una herramienta gratuita y se puede descargar desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=28567). Para obtener más información, vea los [vídeos tutoriales de PerfView](https://channel9.msdn.com/Series/PerfView-Tutorial).  
  
> [!NOTE]
> PerfView no se puede usar para recopilar eventos en sistemas ARM. Para recopilar eventos en sistemas ARM, use Windows Performance Recorder (WPR). Para obtener más información, vea la [entrada de blog de Vance Morrison](/archive/blogs/vancem/collecting-etwperfview-data-on-an-windows-rt-winrt-arm-surface-device).  
  
 PerfView también se puede invocar desde la línea de comandos. Para registrar solo los eventos de su proveedor, abra una ventana de símbolo del sistema y escriba el comando:  
  
```console
perfview -KernelEvents:Process -OnlyProviders:*MyCompany-MyApp collect outputFile
```  
  
 donde:  
  
 `-KernelEvents:Process`  
 Indica que quiere saber cuándo se inicia y detiene el proceso. Necesita el evento Procesar/Iniciar de la aplicación para que se pueda restar de otros tiempos de evento.  
  
 `-OnlyProviders:*MyCompany-MyApp`  
 Desactiva otros proveedores que PerfView activa de forma predeterminada y activa el proveedor MyCompany-MyApp  (el asterisco indica que se trata de un <xref:System.Diagnostics.Tracing.EventSource>).  
  
 `collect outputFile`  
 Indica que quiere iniciar la recopilación y guardar los datos en outputFile.etl.zip.  
  
 Ejecute la aplicación después de iniciar PerfView. Hay algunas cosas que recordar cuando se ejecuta la aplicación:  
  
- Utilice una versión de lanzamiento, no una versión de depuración. Las versiones de depuración suelen contener código extra de tratamiento y comprobación de errores que puede hacer que la aplicación se ejecute más despacio de lo previsto.  
  
- La ejecución de una aplicación con un depurador adjunto influye en el rendimiento de la aplicación.  
  
- Windows usa diversas estrategias de almacenamiento en caché para acelerar los tiempos de inicio de la aplicación. Si la aplicación está almacenada actualmente en caché y no tiene que cargarse desde el disco, se iniciará más rápido. Para garantizar la coherencia, inicie y cierre la aplicación varias veces antes de medirla.  
  
 Cuando haya ejecutado la aplicación para que PerfView pueda recopilar los eventos emitidos, seleccione el botón **Detener colección**. En general, la colección se debe detener antes de cerrar la aplicación para, así, no obtener eventos extraños. Sin embargo, si se mide el rendimiento de suspensión o de apagado, conviene continuar con la colección.  
  
## <a name="displaying-the-events"></a>Visualización de eventos  
 Para ver los eventos que ya se han recopilado, use PerfView para abrir el archivo .etl o .etl.zip que ha creado y seleccione **Eventos**. ETW habrá recopilado información acerca de un gran número de eventos, incluidos los eventos de otros procesos. Para acotar la investigación, rellene los siguientes cuadros de texto en la vista de eventos:  
  
- En el cuadro **Process Filter** (Filtro de proceso), escriba el nombre de la aplicación (sin ".exe").  
  
- En el cuadro **Event Types Filter** (Filtro de tipos de evento), especifique `Process/Start | MyCompany-MyApp`. Esto establece un filtro para los eventos de MyCompany-MyApp y el evento Windows Kernel/Process/Start.  
  
 Seleccione todos los eventos que se muestran en el panel izquierdo (Ctrl+A) y presione la tecla **ENTRAR**. Ahora, debería poder ver las marcas de tiempo de cada evento. Estas marcas hacen referencia al inicio del seguimiento, por lo que debe restar la hora de cada evento de la hora de inicio del proceso para averiguar el tiempo transcurrido desde el inicio. Si usa Ctrl+clic para seleccionar dos marcas de tiempo, verá la diferencia entre ambas en la barra de estado de la parte inferior de la página. Esto hace que sea muy sencillo ver en pantalla el tiempo transcurrido entre dos eventos (incluido el inicio del proceso). Puede abrir el menú contextual de la vista y seleccionar diversas opciones de gran utilidad, como exportar a un archivo CSV o abrir Microsoft Excel para guardar o procesar los datos.  
  
 Al repetir el procedimiento para la aplicación original y la versión que creó mediante la cadena de herramientas de .NET Native, puede comparar la diferencia de rendimiento.   Normalmente, las aplicaciones .NET Native se inician más rápido que las aplicaciones nativas de non-.NET. Si le interesa seguir ahondando en este asunto, PerfView también es capaz identificar las partes del código que consumen más tiempo. Para obtener más información, vea los [tutoriales de PerfView](https://channel9.msdn.com/Series/PerfView-Tutorial) o lea la [entrada de blog de Vance Morrison](/archive/blogs/vancem/publication-of-the-perfview-performance-analysis-tool).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.Tracing.EventSource>
