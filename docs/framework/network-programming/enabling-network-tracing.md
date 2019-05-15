---
title: Habilitación del seguimiento de red
ms.date: 03/30/2017
helpviewer_keywords:
- trace destinations
- sending traces to log file
- trace listeners, network tracing
- network tracing, enabling
- CLR Debugger
- default listeners
- logs, trace
- destination for tracing output
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
ms.openlocfilehash: 5145b013db1a86ef1b3128ab1c4495dddaaaf987
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624634"
---
# <a name="enabling-network-tracing"></a>Habilitación del seguimiento de red
El seguimiento de red proporciona acceso a información sobre las invocaciones de métodos y el tráfico de red generado por una aplicación administrada. Para habilitar el seguimiento de red en la aplicación tiene que realizar las tareas siguientes:  
  
- Compilar el código con el seguimiento habilitado. Vea [Cómo: Compile Conditionally with Trace and Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) (Cómo: Compilar de forma condicional con Trace y Debug) para más información sobre los modificadores del compilador necesarios para habilitar el seguimiento.  
  
- Especificar un destino para la salida del seguimiento.  
  
- Configurar el comportamiento del seguimiento de red. Vea [Cómo: Configurar el seguimiento de red](../../../docs/framework/network-programming/how-to-configure-network-tracing.md) para obtener información detallada.  
  
 Los destinos de seguimiento más comunes, que también se conocen como agentes de escucha de seguimiento, son el agente de escucha predeterminado y el archivo de registro.  
  
 Si no se especifica un agente de escucha de seguimiento, el seguimiento usa el agente de escucha predeterminado. Puede ver los mensajes enviados al agente de escucha predeterminado si ejecuta el código en un depurador administrado habilitado para código, como CLR Debugger, que se distribuye con .NET Framework SDK, o DBwin32.exe, incluido en Windows SDK. Si se usa CLR Debugger, los mensajes de seguimiento aparecen en la ventana **Resultados**.  
  
 Si prefiere usar un archivo para recibir los seguimientos, puede especificar un archivo de registro mediante los valores de configuración, como se muestra en el ejemplo siguiente. (Para una descripción general de los archivos de configuración, vea [Archivos de configuración](../../../docs/framework/configure-apps/index.md)).  
  
 Para enviar los seguimientos a un archivo de registro, agregue el siguiente nodo al nodo `<system.diagnostics>` del archivo de configuración adecuado (aplicación o equipo). Puede cambiar el nombre del archivo (trace.log) de modo que satisfaga sus necesidades.  
  
```xml  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## <a name="see-also"></a>Vea también

- [Interpretación del seguimiento de red](../../../docs/framework/network-programming/interpreting-network-tracing.md)
- [Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)](../../../docs/framework/network-programming/network-tracing.md)
- [Seguimiento e instrumentación de aplicaciones](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
