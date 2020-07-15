---
title: Proveedores ETW de CLR
description: 'Revise los detalles de los dos proveedores de seguimiento de eventos de Common Language Runtime (CLR) para Windows (ETW): el proveedor runtimne y el proveedor de detención.'
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, CLR providers
- CLR ETW providers
ms.assetid: 0beafad4-b2c8-47f4-b342-83411d57a51f
ms.openlocfilehash: 9f86e8334482880c4f7cb23ec93a3c826c083389
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309656"
---
# <a name="clr-etw-providers"></a>Proveedores ETW de CLR
El Common Language Runtime (CLR) tiene dos proveedores: el proveedor de runtime y el proveedor del informe detallado.  
  
 El proveedor de runtime genera eventos en función de las palabras clave (categorías de eventos) que están habilitadas. Por ejemplo, puede recopilar eventos de cargador habilitando la palabra clave `LoaderKeyword`.  
  
 Los eventos de seguimiento de eventos para Windows (ETW) se registran en un archivo que tiene una extensión. ETL, que posteriormente se puede procesar después en archivos de valores separados por comas (. csv) según sea necesario. Para más información sobre cómo convertir el archivo .etl en un archivo .csv, vea [Controlling .NET Framework Logging (Controlar el registro de .NET Framework)](controlling-logging.md).  
  
## <a name="the-runtime-provider"></a>El proveedor en tiempo de ejecución  
 El proveedor en tiempo de ejecución es el principal proveedor ETW de CLR.  
  
 El GUID del proveedor en tiempo de ejecución de CLR es e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.  
  
 Para obtener ejemplos sobre cómo registrar y ver eventos ETW de CLR con las herramientas habituales, vea [Controlling .NET Framework Logging (Controlar el registro de .NET Framework)](controlling-logging.md).  
  
 Además de utilizar las palabras clave como `LoaderKeyword`, puede que sea preciso habilitar palabras clave para registrar eventos que se generen con demasiada frecuencia. Las palabras clave `StartEnumerationKeyword` y `EndEnumerationKeyword` habilitan estos eventos y se resumen en [Palabras clave y niveles ETW de CLR](clr-etw-keywords-and-levels.md).  
  
## <a name="the-rundown-provider"></a>El proveedor de informe detallado  
 El proveedor del informe detallado debe estar activado para algunos usos específicos. Sin embargo, para la mayoría de los usuarios, el proveedor de runtime debe bastar.  
  
 El GUID del proveedor de informe detallado de CLR es A669021C-C450-4609-A035-5AF59AF4DF18.  
  
 Normalmente, el registro ETW se habilita antes de iniciar un proceso y el registro se desactiva al salir del proceso. Sin embargo, si se activa el registro ETW mientras el proceso se está ejecutando, se necesita información adicional sobre el proceso. Por ejemplo, para la resolución de símbolos es preciso registrar eventos de método para los métodos que ya estaban cargados antes de que se activara el registro.  
  
 Los eventos `DCStart` y `DCEnd` capturan el estado del proceso cuando se inició y detuvo la recolección de datos. (El estado hace referencia a información en un nivel alto, incluidos los métodos que ya estaban compilados Just-in-Time (JIT) y ensamblados que se cargaron). Estos dos eventos pueden proporcionar información sobre lo que ya ha sucedido en el proceso; por ejemplo, los métodos que se compilaron JIT, etc.  
  
 Solo los eventos con `DC`, `DCStart`, `DCEnd` o `DCInit` en sus nombres se provocan con el proveedor de informe detallado. Además, estos eventos solo se provocan con el proveedor de informe detallado.  
  
 Además de los filtros de palabras clave de eventos, el proveedor de informe detallado también admite las palabras clave `StartRundownKeyword` y `EndRundownKeyword` para proporcionar un filtrado concreto.  
  
### <a name="start-rundown"></a>Informe detallado de inicio  
 Se activa un informe detallado de inicio cuando se habilita el registro con el proveedor de informe detallado mediante la palabra clave `StartRundownKeyword`. Esto provoca el evento `DCStart` y captura el estado del sistema. Antes del inicio de la enumeración, se genera el evento `DCStartInit`. Al final de la enumeración, se provoca el evento `DCStartComplete` para notificar al controlador que la recolección de datos finalizó normalmente.  
  
### <a name="end-rundown"></a>Informe detallado de fin  
 Se activa un informe detallado de fin cuando se habilita el registro con el proveedor de informe detallado mediante la palabra clave `EndRundownKeyword`. El informe detallado de fin deja de generar perfiles en un proceso que continúa ejecutándose. Los eventos `DCEnd` capturan el estado del sistema al detener la generación de perfiles.  
  
 Antes del inicio de la enumeración, se genera el evento `DCEndInit`. Al final de la enumeración, se provoca el evento `DCEndComplete` para notificar al consumidor que la recolección de datos finalizó normalmente. El informe detallado de inicio y de fin se utilizan principalmente para la resolución de símbolos administrados. El informe detallado de inicio puede proporcionar información de intervalos de dirección para los métodos que ya estaban compilados JIT antes de que se iniciara la sesión de generación de perfiles. El informe detallado de fin puede proporcionar información sobre intervalos de dirección de todos los métodos que se han compilado JIT cuando la generación de perfiles está a punto de desactivarse.  
  
 El informe detallado de fin no se produce automáticamente cuando se detiene una sesión de generación de perfiles. En su lugar, una herramienta que está intentando realizar una resolución de símbolos administrados tiene que invocar explícitamente una sesión de proveedor de informe detallado de CLR con la palabra clave `EndRundownKeyword` habilitada, justo antes de que se detenga la generación de perfiles.  
  
 Aunque el informe detallado de inicio o de fin pueden proporcionar ambos información de intervalos de dirección de métodos para la resolución de símbolos administrados, recomendamos utilizar la palabra clave `EndRundownKeyword` (que proporciona eventos `DCEnd`) en lugar de la palabra clave `StartRundownKeyword` (que proporciona eventos `DCStart`). El uso de `StartRundownKeyword` provoca la ejecución del informe detallado durante la sesión de generación de perfiles, lo que puede alterar el escenario de generación de perfiles.  
  
## <a name="etw-data-collection-using-runtime-and-rundown-providers"></a>Recolección de datos ETW mediante los proveedores en tiempo de ejecución y de informe detallado  
 En el siguiente ejemplo se muestra cómo utilizar el proveedor de informe detallado de CLR de una manera que permita la resolución de símbolos de procesos administrados con un impacto mínimo, sin tener en cuenta si los procesos se inician o finalizan dentro o fuera de la ventana de generación de perfiles.  
  
1. Active el registro ETW mediante el proveedor en tiempo de ejecución de CLR:  
  
    ```console
    xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:0x5 -f clr1.etl
    ```  
  
     El registro se guardará en el archivo clr1.etl.  
  
2. Para detener la generación de perfiles mientras continúa ejecutándose el proceso, inicie el proveedor de informe detallado para capturar los eventos `DCEnd`:  
  
    ```console
    xperf -start clrRundown -on A669021C-C450-4609-A035-5AF59AF4DF18:0xB8:0x5 -f clr2.etl
    ```  
  
     Esto permite a la colección de eventos `DCEnd` iniciar una sesión de informe detallado. Es posible que deba esperar entre 30 y 60 segundos para recopilar todos los eventos. El registro se guardará en el archivo clr1.et2.  
  
3. Desactive toda la generación de perfiles ETW:  
  
    ```console
    xperf -stop clrRundown
    xperf -stop clr  
    ```  
  
4. Fusione mediante combinación los perfiles para crear un archivo de registro:  
  
    ```console
    xperf -merge clr1.etl clr2.etl merged.etl  
    ```  
  
     El archivo merged.etl contendrá los eventos de las sesiones de los proveedores en tiempo de ejecución y de informe detallado.  
  
 Una herramienta puede ejecutar los pasos 2 y 3 (iniciando una sesión de informe detallado y finalizando la generación de perfiles) en lugar de desactivar la generación de perfiles de inmediato cuando un usuario solicita la detención de dicha generación. Una herramienta también puede ejecutar el paso 4.  
  
## <a name="see-also"></a>Consulte también

- [Eventos ETW en Common Language Runtime](etw-events-in-the-common-language-runtime.md)
