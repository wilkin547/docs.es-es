---
title: "Habilitaci&#243;n del seguimiento de red | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "destinos de seguimiento"
  - "envío de seguimiento al archivo de registro"
  - "agentes de escucha de seguimiento, seguimiento de red"
  - "seguimiento de red, habilitar"
  - "CLR Debugger"
  - "agentes de escucha predeterminados"
  - "registros, seguimiento"
  - "destino para la salida de seguimiento"
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Habilitaci&#243;n del seguimiento de red
La traza de la red proporciona acceso a información sobre las invocaciones de método y el tráfico de red generado por una aplicación administrada.  Debe completar las tareas siguientes para habilitar la traza de la red en su aplicación:  
  
-   Compile el código con la traza habilitada.  Vea [How to: Compile Conditionally with Trace and Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) para obtener más información sobre el compilador necesarios para habilitar la traza.  
  
-   Especifique un destino para el resultado de la traza.  
  
-   Configure el comportamiento de la traza de la red.  Vea [Cómo: Configurar la traza de la red](../../../docs/framework/network-programming/how-to-configure-network-tracing.md) para obtener información detallada.  
  
 El más común seguimiento los destinos, también denominados agentes de escucha, es el agente de escucha predeterminado y el archivo de registro.  
  
 La traza utiliza el agente de escucha predeterminado si no especifica un agente de escucha.  Puede ver los mensajes enviados al agente de escucha predeterminado ejecutando el código en un depurador código\- habilitado administrado como el depurador CLR enviado con .NET Framework SDK, o DBwin32.exe enviado con Windows SDK.  Mediante el depurador CLR, los mensajes de traza aparecen en la ventana de **Resultado** .  
  
 Si prefiere utilizar un archivo para recibir trazas, puede especificar un archivo de registro mediante opciones de configuración, como se muestra en el ejemplo siguiente.  \(Para obtener una descripción general de archivos de configuración, vea [archivos de configuración](../../../docs/framework/configure-apps/index.md).\)  
  
 Para enviar un seguimiento en un archivo de registro, agregue el siguiente nodo al nodo de `<system.diagnostics>` del archivo de configuración adecuado \(aplicación o equipo\).  Puede cambiar el nombre del archivo \(trace.log\) para satisfacer sus necesidades.  
  
```  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## Vea también  
 [Interpretar el seguimiento de red](../../../docs/framework/network-programming/interpreting-network-tracing.md)   
 [Traza de la red en .NET Framework](../../../docs/framework/network-programming/network-tracing.md)   
 [Introduction to Instrumentation and Tracing](http://msdn.microsoft.com/es-es/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)