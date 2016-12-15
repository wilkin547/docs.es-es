---
title: "Tutorial: Determinar el lugar en el que My.Application.Log escribe la informaci&#243;n (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Log (objeto), ubicación de salida"
  - "salida, ubicación del registro de aplicaciones"
  - "My.Application.Log (objeto), ubicación de salida"
  - "registros de eventos, determinar la ubicación de salida"
  - "registros de eventos de aplicación, ubicación de salida"
  - "aplicaciones [Visual Basic], ubicación de salida"
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tutorial: Determinar el lugar en el que My.Application.Log escribe la informaci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El objeto `My.Application.Log` puede escribir información en varios agentes de escucha de registro. Los agentes de escucha de registro se configuran por archivo de configuración del equipo y puede reemplazarlos una archivo de configuración de la aplicación. En este tema se describe la configuración predeterminada y cómo determinar la configuración de la aplicación.  
  
 Para más información sobre las ubicaciones de salida predeterminadas, vea [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
### Para determinar los agentes de escucha de My.Application.Log  
  
1.  Busque el archivo de configuración del ensamblado. Si está desarrollando el ensamblado, puede acceder a app.config en [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] desde el **Explorador de soluciones**. De lo contrario, el nombre del archivo de configuración es el nombre del ensamblado con ".config" anexado, que se encuentra en el mismo directorio que el ensamblado.  
  
    > [!NOTE]
    >  No todos los ensamblados tienen un archivo de configuración.  
  
     El archivo de configuración es un archivo XML.  
  
2.  Busque la sección `<listeners>`, en la sección `<source>` con el atributo `name` el "DefaultSource", ubicada en la sección `<sources>`. La sección `<sources>` se encuentra en la sección `<system.diagnostics>`, en la sección de nivel superior `<configuration>`.  
  
     Si estas secciones no existen, el archivo de configuración del equipo puede configurar los agentes de escucha de registro `My.Application.Log`. En los pasos siguientes se describe cómo determinar qué define el archivo de configuración del equipo:  
  
    1.  Busque el archivo machine.config del equipo. Normalmente, se encuentra en el directorio *SystemRoot\\Microsoft.NET\\Framework\\frameworkVersion\\CONFIG*, donde `SystemRoot` es el directorio del sistema operativo y `frameworkVersion` es la versión de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
         La configuración de machine.config puede reemplazarse por un archivo de configuración de la aplicación.  
  
         Si los elementos opcionales que se enumeran a continuación no existen, puede crearlos.  
  
    2.  Busque la sección `<listeners>`, en la sección `<source>` con el atributo `name` el "DefaultSource", en la sección `<sources>`, en la sección `<system.diagnostics>`, en la sección de nivel superior `<configuration>`.  
  
         Si estas secciones no existen, `My.Application.Log` solo tiene los agentes de escucha de registro predeterminados.  
  
3.  Busque los elementos \<`add>` en la sección \<`listeners>`.  
  
     Estos elementos agregan los agentes de escucha de registro con nombre al origen `My.Application.Log`.  
  
4.  Busque los elementos `<add>` con los nombres de los agentes de escucha de registro en la sección `<sharedListeners>`, en la `<system.diagnostics>` sección, en la sección de nivel superior `<configuration>`.  
  
5.  Para muchos tipos de agentes de escucha compartidos, los datos de inicialización del agente de escucha incluyen una descripción de la ubicación a la que el agente de escucha dirige los datos:  
  
    -   Un agente de escucha <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> escribe en un registro de archivos, como se describe en la introducción.  
  
    -   Un agente de escucha <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> que escribe información en el registro de eventos del equipo especificado por el parámetro `initializeData`. Para ver un registro de eventos, puede usar el **Explorador de servidores** o el **Visor de eventos de Windows**. Para obtener más información, consulta [ETW Events in the .NET Framework](../Topic/ETW%20Events%20in%20the%20.NET%20Framework.md).  
  
    -   Los agentes de escucha <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> y <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> escriben en el archivo especificado en el parámetro `initializeData`.  
  
    -   Un agente de escucha <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> escribe en la consola de línea de comandos.  
  
    -   Para obtener información sobre dónde escriben información otros tipos de agentes de escucha de registro, consulte la documentación de ese tipo.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 <xref:System.Diagnostics.DelimitedListTraceListener>   
 <xref:System.Diagnostics.XmlWriterTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics>   
 [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [Cómo: Escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Tutorial: Cambiar el lugar donde My.Application.Log escribe información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)   
 [ETW Events in the .NET Framework](../Topic/ETW%20Events%20in%20the%20.NET%20Framework.md)   
 [Solución de problemas: Agentes de escucha de registro](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)