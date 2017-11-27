---
title: Controlar el registro de .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
caps.latest.revision: "40"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f996cf730acc355f3bf13287b79581d23e4e6a5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="controlling-net-framework-logging"></a>Controlar el registro de .NET Framework
Se puede utilizar el seguimiento de eventos para Windows (ETW) para registrar los eventos de Common Language Runtime (CLR). Es posible crear y ver los seguimientos mediante las siguientes herramientas:  
  
-   Las herramientas de línea de comandos [Logman](http://go.microsoft.com/fwlink/?LinkId=150916) y [Tracerpt](http://go.microsoft.com/fwlink/?LinkId=150919), que se incluyen con el sistema operativo Windows.  
  
-   Las herramientas [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) del [Kit de herramientas de rendimiento de Windows](http://msdn.microsoft.com/library/windows/hardware/hh162945.aspx). Para obtener más información sobre Xperf, vea el [blog de rendimiento de Windows](http://go.microsoft.com/fwlink/?LinkId=179509).  
  
 Para capturar información de eventos de CLR, el proveedor de CLR debe estar instalado en el equipo. Para confirmar que el proveedor está instalado, escriba `logman query providers` en el símbolo del sistema. Se muestra una lista de proveedores. Esta lista debería contener una entrada para el proveedor de CLR, del modo siguiente.  
  
```  
Provider                                 GUID  
-------------------------------------------------------------------------------  
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.  
```  
  
 Si el proveedor de CLR no aparece en la lista, puede instalarlo en Windows Vista y sistemas operativos posteriores mediante la herramienta de línea de comandos [Wevtutil](http://go.microsoft.com/fwlink/?LinkID=150915) de Windows. Abra la ventana Símbolo del sistema como administrador. Cambie del directorio del símbolo del sistema a la carpeta [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.versión de .NET>\). Esta carpeta contiene el archivo CLR-ETW.man. En el símbolo del sistema, escriba el siguiente comando para instalar el proveedor de CLR.  
  
 `wevtutil im CLR-ETW.man`  
  
## <a name="capturing-clr-etw-events"></a>Capturar eventos ETW de CLR  
 Puede usar las herramientas de línea de comandos [Logman](http://go.microsoft.com/fwlink/?LinkId=150916) y [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) para capturar eventos ETW y las herramientas [Tracerpt](http://go.microsoft.com/fwlink/?LinkId=150919) y [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) para descodificar eventos de seguimiento.  
  
 Para activar el registro, el usuario debe especificar tres cosas:  
  
-   El proveedor con el que comunicarse.  
  
-   Número de 64 bits que representa un conjunto de palabras clave. Cada palabra clave representa un conjunto de eventos que el proveedor puede activar. El número representa un conjunto combinado de palabras clave que se pueden activar.  
  
-   Un número pequeño que representa el nivel (de detalle) con que se realiza el registro. El nivel 1 es el menos detallado y el nivel 5, el más detallado. El nivel 0 es un valor predeterminado cuyo significado es específico del proveedor.  
  
#### <a name="to-capture-clr-etw-events-using-logman"></a>Para capturar eventos ETW de CLR mediante Logman  
  
1.  En el símbolo del sistema, escriba:  
  
     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`  
  
     donde:  
  
    -   El parámetro `-p` identifica el GUID del proveedor.  
  
    -   `0x1CCBD` especifica las categorías de eventos que se van a producir.  
  
    -   `0x5` establece el nivel de registro (en este caso, detallado (5)).  
  
    -   El parámetro `-ets` indica a Logman que envíe los comandos a las sesiones de seguimiento de eventos.  
  
    -   El parámetro `-ct perf` especifica que la función `QueryPerformanceCounter` se utilizará para registrar la marca de tiempo para cada evento.  
  
2.  Para dejar de registrar los eventos, escriba:  
  
     `logman stop clrevents -ets`  
  
     Este comando crea un archivo de seguimiento binario denominado clrevents.etl.  
  
#### <a name="to-capture-clr-etw-events-using-xperf"></a>Para capturar eventos ETW de CLR mediante Xperf  
  
1.  En el símbolo del sistema, escriba:  
  
     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`  
  
     donde el GUID es el GUID del proveedor de ETW de CLR y `0x1CCBD:5` realiza la traza de todo en el nivel 5 y por debajo de este (detallado).  
  
2.  Para detener el seguimiento, escriba:  
  
     `Xperf -stop clr`  
  
     Este comando crea un archivo de seguimiento denominado clrevents.etl.  
  
## <a name="viewing-clr-etw-events"></a>Ver eventos ETW de CLR  
 Utilice los comandos enumerados a continuación para ver los eventos ETW de CLR. Para obtener una descripción de los eventos, vea [Eventos ETW de CLR](../../../docs/framework/performance/clr-etw-events.md).  
  
#### <a name="to-view-clr-etw-events-using-tracerpt"></a>Para ver los eventos ETW de CLR mediante Tracerpt  
  
-   En el símbolo del sistema, escriba:  
  
     `tracerpt clrevents.etl`  
  
     Este comando crea dos archivos: dumpfile.xml y summary.txt. El archivo dumpfile.xml muestra todos los eventos y summary.txt proporciona un resumen de ellos.  
  
#### <a name="to-view-clr-etw-events-using-xperf"></a>Para ver los eventos ETW de CLR mediante Xperf  
  
-   En el símbolo del sistema, escriba:  
  
     `xperf clrevents.etl`  
  
     Este comando abre el visor de archivos ETL Xperf. En este visor, los eventos de CLR se presentan en la vista **Eventos genéricos**. Para mostrar una cuadrícula de datos de eventos clasificados por tipos, seleccione un área de tiempo en esta vista y, después, haga clic con el botón derecho del mouse y seleccione **Resumen**.  
  
#### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a>Para convertir el archivo .etl en un archivo de valores separados por comas  
  
-   En el símbolo del sistema, escriba:  
  
     `xperf -i clrevents.etl -f clrevents.csv`  
  
     Este comando hace que XPerf vuelque los eventos en un archivo de valores separados por comas (CSV) que se puede consultar. Dado que los distintos eventos tienen campos distintos, este archivo CSV contiene más de una línea de encabezado antes de los datos. El primer campo de cada línea es el tipo de evento, que indica qué encabezado se debería utilizar para determinar el resto de los campos.  
  
## <a name="see-also"></a>Vea también  
 [Kit de herramientas de rendimiento de Windows](http://go.microsoft.com/fwlink/?LinkID=161141)  
 [Eventos ETW en Common Language Runtime](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
