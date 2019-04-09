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
ms.openlocfilehash: 351d133215343e07e849ad1045eba601dd8cce56
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092285"
---
# <a name="administration-and-diagnostics"></a>Administración y diagnóstico
Windows Communication Foundation (WCF) proporciona un amplio conjunto de funcionalidades que pueden ayudarle a supervisar las distintas fases del ciclo de vida de la aplicación. Por ejemplo, puede usar la configuración para configurar servicios y clientes en la implementación. WCF incluye un conjunto grande de contadores de rendimiento para ayudarle a calibrar el rendimiento de su aplicación. WCF también expone datos de inspección de un servicio en tiempo de ejecución a través de un proveedor de Instrumental de administración de Windows (WMI) de WCF. Cuando la aplicación experimenta un error o comienza a actuar incorrectamente, puede utilizar el Registro de eventos para ver si algo significativo ha sucedido. También puede utilizar el registro y seguimiento de mensajes para ver qué eventos están pasando de un extremo a otro en su aplicación. Estas características ayudan a los desarrolladores y profesionales de TI a solucionar problemas de aplicaciones WCF cuando no se comporta correctamente.  
  
> [!NOTE]
>  Si recibe errores sin información detallada específica, debe habilitar la `includeExceptionDetailInFaults` atributo de la [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) elemento de configuración. Esto indica a WCF para enviar los detalles de la excepción a los clientes, lo que permite detectar muchos problemas habituales sin necesidad de realizar un diagnóstico más avanzado. Para obtener más información, consulte [Sending and Receiving Faults](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Características de diagnóstico proporcionadas por WCF  
 WCF proporciona las siguientes funcionalidades de diagnóstico:  
  
-   El seguimiento de un extremo a otro proporciona datos de instrumentación para solucionar problemas de una aplicación sin usar un depurador. WCF genera seguimientos para los hitos del proceso, así como los mensajes de error. Esto puede incluir abrir un generador de canales o el envío y recepción de mensajes por parte un host de servicio. Se puede habilitar el seguimiento para una aplicación en ejecución para supervisar su progreso. Para obtener más información, consulte el [seguimiento](../../../../docs/framework/wcf/diagnostics/tracing/index.md) tema. Para comprender cómo puede utilizar el seguimiento para depurar la aplicación, consulte el [utilizando seguimiento de la solución de problemas de la aplicación](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) tema.  
  
-   El registro de mensajes le permite ver el aspecto de los mensajes antes y después de la transmisión. Para obtener más información, consulte el [registro de mensajes](../../../../docs/framework/wcf/diagnostics/message-logging.md) tema.  
  
-   El seguimiento de eventos escribe los eventos en el Registro de eventos para poder ver cualquier problema importante. Puede usar a continuación el Visor de eventos para examinar cualquier anormalidad. Para obtener más información, consulte el [Event Logging](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) tema.  
  
-   Los contadores de rendimiento expuestos a través del Monitor de rendimiento le permiten supervisar el estado de su aplicación y del sistema. Para obtener más información, consulte el [los contadores de rendimiento](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) tema.  
  
-   El espacio de nombres <xref:System.ServiceModel.Configuration> le permite cargar archivos de configuración y establecer un punto de conexión de servicio o cliente. Puede utilizar el modelo de objetos para crear scripts con cambios para muchas aplicaciones cuando se deben implementar actualizaciones en muchos equipos. Como alternativa, puede usar el [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) para editar los valores de configuración mediante un asistente GUI. Para obtener más información, consulte el [configuración de la aplicación](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) tema.  
  
-   WMI le permite averiguar qué servicios está realizando escuchas en un equipo y los enlaces que se están usando. Para obtener más información, consulte el [utilizando Instrumental de administración de Windows para el diagnóstico](../../../../docs/framework/wcf/diagnostics/wmi/index.md) tema.  
  
 WCF también proporciona varias herramientas de línea de comandos y GUI para que sea más fácil para que pueda crear, implementar y administrar aplicaciones de WCF. Para obtener más información, consulte [herramientas de Windows Communication Foundation](../../../../docs/framework/wcf/tools.md). Por ejemplo, puede usar el [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) para crear y editar los valores de configuración de WCF mediante un asistente, en lugar de editar XML directamente. También puede usar el [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) para ver, agrupar y filtrar los mensajes de seguimiento de modo que pueda diagnosticar, reparar y comprobar los problemas con los servicios WCF.  
  
## <a name="see-also"></a>Vea también

- [Configuración de su aplicación](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
- [Desarrollo de servicios](../../../../docs/framework/wcf/diagnostics/deploying-services.md)
- [Referencia de excepciones](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)
- [Registro de eventos](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [Registro de mensajes](../../../../docs/framework/wcf/diagnostics/message-logging.md)
- [Herramienta del editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [Herramienta de registro ServiceModel](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)
- [Traza](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Utilización del instrumental de administración de Windows (WMI) para diagnósticos](../../../../docs/framework/wcf/diagnostics/wmi/index.md)
- [Contadores de rendimiento](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
- [Herramientas de Windows Communication Foundation](../../../../docs/framework/wcf/tools.md)
