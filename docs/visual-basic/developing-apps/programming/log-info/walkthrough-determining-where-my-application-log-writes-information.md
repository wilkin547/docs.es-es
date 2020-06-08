---
title: Determinar el lugar en el que My.Application.Log escribe la información
ms.date: 07/20/2015
helpviewer_keywords:
- My.Log object, output location
- output, application log location
- My.Application.Log object, output location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
ms.openlocfilehash: 00b543dbe96ca99446f6797a13b66ee62c422b93
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398284"
---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a>Tutorial: Determinar el lugar en el que My.Application.Log escribe la información (Visual Basic)

El objeto `My.Application.Log` puede escribir información en varios agentes de escucha de registro. Los agentes de escucha de registro se configuran por archivo de configuración del equipo y puede reemplazarlos una archivo de configuración de la aplicación. En este tema se describe la configuración predeterminada y cómo determinar la configuración de la aplicación.

Para obtener más información sobre las ubicaciones de salida predeterminadas, vea [Trabajar con registros de aplicaciones](working-with-application-logs.md).

### <a name="to-determine-the-listeners-for-myapplicationlog"></a>Para determinar los agentes de escucha de My.Application.Log

1. Busque el archivo de configuración del ensamblado. Si está desarrollando el ensamblado, puede acceder a app.config en Visual Studio desde el **Explorador de soluciones**. De lo contrario, el nombre del archivo de configuración es el nombre del ensamblado con ".config" anexado, que se encuentra en el mismo directorio que el ensamblado.

    > [!NOTE]
    > No todos los ensamblados tienen un archivo de configuración.

    El archivo de configuración es un archivo XML.

2. Busque la sección `<listeners>` , en la sección `<source>` con el atributo `name` el "DefaultSource", ubicada en la sección `<sources>` . La sección `<sources>` se encuentra en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .

    Si estas secciones no existen, el archivo de configuración del equipo puede configurar los agentes de escucha de registro `My.Application.Log` . En los pasos siguientes se describe cómo determinar qué define el archivo de configuración del equipo:

    1. Busque el archivo machine.config del equipo. Normalmente, se encuentra en el directorio *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG*, donde `SystemRoot` es el directorio del sistema operativo y `frameworkVersion` es la versión de .NET Framework.

        La configuración de machine.config puede reemplazarse por un archivo de configuración de la aplicación.

        Si los elementos opcionales que se enumeran a continuación no existen, puede crearlos.

    2. Busque la sección `<listeners>` , en la sección `<source>` con el atributo `name` el "DefaultSource", en la sección `<sources>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .

        Si estas secciones no existen, `My.Application.Log` solo tiene los agentes de escucha de registro predeterminados.

3. Busque los elementos <`add>` en la sección <`listeners>`.

     Estos elementos agregan los agentes de escucha de registro con nombre al origen `My.Application.Log` .

4. Busque los elementos `<add>` con los nombres de los agentes de escucha de registro en la sección `<sharedListeners>` , en la `<system.diagnostics>` sección, en la sección de nivel superior `<configuration>` .

5. Para muchos tipos de agentes de escucha compartidos, los datos de inicialización del agente de escucha incluyen una descripción de la ubicación a la que el agente de escucha dirige los datos:

    - Un agente de escucha <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> escribe en un registro de archivos, como se describe en la introducción.

    - Un agente de escucha <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> que escribe información en el registro de eventos del equipo especificado por el parámetro `initializeData` . Para ver un registro de eventos, puede usar el **Explorador de servidores** o el **Visor de eventos de Windows**. Para obtener más información, consulta [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).

    - Los agentes de escucha <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> y <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> escriben en el archivo especificado en el parámetro `initializeData` .

    - Un agente de escucha <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> escribe en la consola de línea de comandos.

    - Para obtener información sobre dónde escriben información otros tipos de agentes de escucha de registro, consulte la documentación de ese tipo.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DelimitedListTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics>
- [Trabajar con registros de aplicaciones](working-with-application-logs.md)
- [Registrar excepciones](how-to-log-exceptions.md)
- [Escribir mensajes de registro](how-to-write-log-messages.md)
- [Tutorial: Cambiar el lugar donde My.Application.Log escribe información](walkthrough-changing-where-my-application-log-writes-information.md)
- [Eventos ETW en .NET Framework](../../../../framework/performance/etw-events.md)
- [Solución de problemas: Agentes de escucha de registro](troubleshooting-log-listeners.md)
