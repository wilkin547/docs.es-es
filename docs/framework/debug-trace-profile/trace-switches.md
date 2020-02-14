---
title: Modificadores de seguimiento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], trace switches
- trace switches, about trace switches
- tracing [.NET Framework], level of detail
- switches, trace
- trace switches
- trace switches, creating custom
ms.assetid: 8ab913aa-f400-4406-9436-f45bc6e54fbe
ms.openlocfilehash: c164e26c6757094b9820af14a098229ab11eb137
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217207"
---
# <a name="trace-switches"></a>Modificadores de seguimiento
Los modificadores de seguimiento permiten habilitar, deshabilitar y filtrar la salida del seguimiento. Son objetos que existen en el código y que se pueden configurar externamente mediante el archivo config. Hay tres tipos de modificadores de seguimiento en .NET Framework: la clase <xref:System.Diagnostics.BooleanSwitch> , la clase <xref:System.Diagnostics.TraceSwitch> y la clase <xref:System.Diagnostics.SourceSwitch> . La clase <xref:System.Diagnostics.BooleanSwitch> actúa como modificador para alternar que habilita o deshabilita una serie de instrucciones de seguimiento. Las clases <xref:System.Diagnostics.TraceSwitch> y <xref:System.Diagnostics.SourceSwitch> permiten habilitar un modificador de seguimiento para un nivel de seguimiento determinado para que aparezcan los mensajes de <xref:System.Diagnostics.Trace> o <xref:System.Diagnostics.TraceSource> especificados para ese nivel y todos sus niveles inferiores. Si deshabilita el modificador, los mensajes de seguimiento no aparecerán. Todas estas clases derivan de la clase abstracta (**MustInherit**) **Switch**, igual que deberían todos los modificadores desarrollados por el usuario.  
  
 Los modificadores de seguimiento pueden ser útiles para filtrar información. Por ejemplo, quizás quiera ver todos los mensajes de seguimiento de un módulo de acceso a datos, pero solo los mensajes de error del resto de la aplicación. En ese caso, usaría un modificador de seguimiento para el módulo de acceso a datos y otro para el resto de la aplicación. Se puede usar el archivo .config para configurar las opciones apropiadas de los modificadores con el fin de controlar qué tipos de mensajes de seguimiento recibe. Para más información, vea [Cómo: Crear, inicializar y configurar modificadores de seguimiento](how-to-create-initialize-and-configure-trace-switches.md).  
  
 Normalmente, una aplicación implementada se ejecuta con sus modificadores deshabilitados para que los usuarios no tengan que ver numerosos mensajes de seguimiento irrelevantes en la pantalla o que el archivo de registro se llene durante la ejecución de la aplicación. Si surge un problema durante la ejecución de la aplicación, puede detener la aplicación, habilitar los modificadores y reiniciar la aplicación. Después, se mostrarán los mensajes de seguimiento.  
  
 Para usar un modificador primero debe crear un objeto modificador a partir de una clase **BooleanSwitch** , una clase **TraceSwitch** o una clase de modificador definida por el desarrollador. Para más información sobre cómo crear modificadores definidos por el desarrollador, consulte la clase <xref:System.Diagnostics.Switch> en la referencia de .NET Framework. Después, establezca un valor de configuración que especifique cuándo se va a usar el objeto modificador. A continuación, pruebe el valor del objeto modificador en varios métodos de seguimiento **Trace** (o **Debug**).  
  
## <a name="trace-levels"></a>Niveles de seguimiento  
 Al usar **TraceSwitch**hay que tener en cuenta algunas consideraciones adicionales. Un objeto **TraceSwitch** tiene cuatro propiedades que devuelven valores **Boolean** que indican si el modificador está establecido al menos en un nivel determinado:  
  
- <xref:System.Diagnostics.TraceSwitch.TraceError%2A?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceSwitch.TraceWarning%2A?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceSwitch.TraceInfo%2A?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceSwitch.TraceVerbose%2A?displayProperty=nameWithType>  
  
 Los niveles permiten limitar la cantidad de información de seguimiento para recibir solo la información necesaria para solucionar un problema. Configure los modificadores de seguimiento en el nivel de seguimiento adecuado para especificar el nivel de detalle que quiere en la salida del seguimiento. Puede recibir mensajes de error, mensajes de advertencia, mensajes informativos, mensajes de seguimiento detallados o ningún mensaje.  
  
 Está en sus manos decidir qué tipo de mensaje asociará a cada nivel. Normalmente, el contenido de los mensajes de seguimiento depende de lo que asocie a cada nivel, pero usted determina las diferencias entre los niveles. Desea proporcionar descripciones detalladas de un problema en el nivel 3 (**Info**), por ejemplo, pero solo un número de referencia de error en el nivel 1 (**Error**). Es decisión suya qué esquema funciona mejor en su aplicación.  
  
 Estas propiedades corresponden a los valores 1 a 4 de la enumeración **TraceLevel** . En la tabla siguiente se enumeran los niveles de la enumeración **TraceLevel** y sus valores.  
  
|Valor enumerado|Valor entero|Tipo de mensaje que se muestra (o se escribe en un destino de salida especificado)|  
|----------------------|-------------------|---------------------------------------------------------------------------|  
|Off|0|None|  
|Error|1|Solo mensajes de error|  
|Advertencia|2|Mensajes de advertencia y mensajes de error|  
|Información|3|Mensajes informativos, mensajes de advertencia y mensajes de error|  
|Verbose|4|Mensajes detallados, mensajes informativos, mensajes de advertencia y mensajes de error|  
  
 Las propiedades de **TraceSwitch** indican el nivel de seguimiento máximo para el modificador. Es decir, la información de seguimiento se escribe para el nivel especificado y para todos los niveles inferiores. Por ejemplo, si **TraceInfo** es **true**, **TraceError** y **TraceWarning** también son **true** , pero **TraceVerbose** podría ser **false**.  
  
 Estas propiedades son de solo lectura. El objeto **TraceSwitch** las establece automáticamente cuando se establece la propiedad **TraceLevel** . Por ejemplo:  
  
```vb  
Dim myTraceSwitch As New TraceSwitch("SwitchOne", "The first switch")  
myTraceSwitch.Level = TraceLevel.Info  
' This message box displays true, because setting the level to  
' TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString())  
' This messagebox displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString())  
```  
  
```csharp  
System.Diagnostics.TraceSwitch myTraceSwitch =   
   new System.Diagnostics.TraceSwitch("SwitchOne", "The first switch");  
myTraceSwitch.Level = System.Diagnostics.TraceLevel.Info;  
// This message box displays true, because setting the level to   
// TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString());  
// This message box displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString());  
```  
  
## <a name="developer-defined-switches"></a>Modificadores definidos por el desarrollador  
 Además de proporcionar **BooleanSwitch** y **TraceSwitch**, puede definir sus propios modificadores heredando de la clase **Switch** y reemplazando los métodos de la clase base por métodos personalizados. Para más información sobre cómo crear modificadores definidos por el desarrollador, consulte la clase <xref:System.Diagnostics.Switch> en la referencia de .NET Framework.  
  
## <a name="see-also"></a>Consulte también

- [Agentes de escucha de seguimiento](trace-listeners.md)
- [Adición de instrucciones de seguimiento al código de la aplicación](how-to-add-trace-statements-to-application-code.md)
- [Traza e instrumentación de aplicaciones](tracing-and-instrumenting-applications.md)
