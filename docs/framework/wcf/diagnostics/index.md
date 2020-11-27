---
title: Administración y diagnóstico
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, diagnostics
- Windows Communication Foundation, administration
- diagnostics [WCF]
- WCF, diagnostics
- administration [WCF]
- WCF, administration
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
ms.openlocfilehash: 703724c3040f2508f011e002c22fa45dd3197884
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285569"
---
# <a name="administration-and-diagnostics"></a>Administración y diagnóstico

Windows Communication Foundation (WCF) proporciona un amplio conjunto de funcionalidades que pueden ayudarle a supervisar las diferentes fases de la vida de una aplicación. Por ejemplo, puede usar la configuración para configurar servicios y clientes en la implementación. WCF incluye un gran conjunto de contadores de rendimiento para ayudarle a medir el rendimiento de la aplicación. WCF también expone datos de inspección de un servicio en tiempo de ejecución a través de un proveedor de WCF Instrumental de administración de Windows (WMI). Cuando la aplicación experimenta un error o comienza a actuar incorrectamente, puede utilizar el Registro de eventos para ver si algo significativo ha sucedido. También puede utilizar el registro y seguimiento de mensajes para ver qué eventos están pasando de un extremo a otro en su aplicación. Estas características ayudan a los desarrolladores y profesionales de ti a solucionar problemas de una aplicación WCF cuando no se comporta correctamente.  
  
> [!NOTE]
> Si recibe errores sin información de detalle específica, debe habilitar el `includeExceptionDetailInFaults` atributo del [\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md) elemento de configuración. Esto indica a WCF que envíe detalles de la excepción a los clientes, lo que le permite detectar muchos problemas comunes sin necesidad de un diagnóstico más avanzado. Para obtener más información, consulte [envío y recepción de errores](../sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Características de diagnóstico proporcionadas por WCF  

 WCF proporciona las siguientes funcionalidades de diagnóstico:  
  
- El seguimiento de un extremo a otro proporciona datos de instrumentación para solucionar problemas de una aplicación sin usar un depurador. WCF genera seguimientos para los hitos del proceso, así como los mensajes de error. Esto puede incluir abrir un generador de canales o el envío y recepción de mensajes por parte un host de servicio. Se puede habilitar el seguimiento para una aplicación en ejecución para supervisar su progreso. Para obtener más información, vea el tema de [seguimiento](./tracing/index.md) . Para entender cómo puede usar el seguimiento para depurar la aplicación, consulte el tema [uso del seguimiento para solucionar problemas de la aplicación](./tracing/using-tracing-to-troubleshoot-your-application.md) .  
  
- El registro de mensajes le permite ver el aspecto de los mensajes antes y después de la transmisión. Para obtener más información, vea el tema [registro de mensajes](message-logging.md) .  
  
- El seguimiento de eventos escribe los eventos en el Registro de eventos para poder ver cualquier problema importante. Puede usar a continuación el Visor de eventos para examinar cualquier anormalidad. Para obtener más información, vea el tema [registro de eventos](./event-logging/index.md) .  
  
- Los contadores de rendimiento expuestos a través del Monitor de rendimiento le permiten supervisar el estado de su aplicación y del sistema. Para obtener más información, vea el tema [contadores de rendimiento](./performance-counters/index.md) .  
  
- El espacio de nombres <xref:System.ServiceModel.Configuration> le permite cargar archivos de configuración y establecer un punto de conexión de servicio o cliente. Puede utilizar el modelo de objetos para crear scripts con cambios para muchas aplicaciones cuando se deben implementar actualizaciones en muchos equipos. Como alternativa, puede usar la [herramienta editor de configuración (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) para editar las opciones de configuración mediante un asistente de GUI. Para obtener más información, consulte el tema [configuración de la aplicación](configuring-your-application.md) .  
  
- WMI le permite averiguar qué servicios está realizando escuchas en un equipo y los enlaces que se están usando. Para obtener más información, consulte el tema [uso de instrumental de administración de Windows para diagnósticos](./wmi/index.md) .  
  
 WCF también proporciona varias herramientas de GUI y de línea de comandos que facilitan la creación, implementación y administración de aplicaciones WCF. Para obtener más información, vea [herramientas de Windows Communication Foundation](../tools.md). Por ejemplo, puede usar la [herramienta editor de configuración (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) para crear y editar los valores de configuración de WCF mediante un asistente, en lugar de editar directamente el código XML. También puede utilizar la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) para ver, agrupar y filtrar los mensajes de seguimiento de modo que pueda diagnosticar, reparar y comprobar los problemas con los servicios WCF.  
  
## <a name="see-also"></a>Vea también

- [Configuración de su aplicación](configuring-your-application.md)
- [Desarrollo de servicios](deploying-services.md)
- [Referencia de excepciones](./exceptions-reference/index.md)
- [Registro de eventos](./event-logging/index.md)
- [Registro de mensajes](message-logging.md)
- [Herramienta del editor de configuración (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)
- [Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md)
- [Herramienta de registro ServiceModel](servicemodel-registration-tool.md)
- [Seguimiento](./tracing/index.md)
- [Uso de Instrumental de administración de Windows para diagnósticos](./wmi/index.md)
- [Contadores de rendimiento](./performance-counters/index.md)
- [Herramientas de Windows Communication Foundation](../tools.md)
