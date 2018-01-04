---
title: "Administración y diagnóstico"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, diagnostics
- Windows Communication Foundation, administration
- diagnostics [WCF]
- WCF, diagnostics
- administration [WCF]
- WCF, administration
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d26386a0669c92b1b21559474c8f5f61862e6de7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="administration-and-diagnostics"></a>Administración y diagnóstico
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporciona un conjunto enriquecido de funcionalidades que pueden ayudarle a supervisar las diferentes fases de la vida de una aplicación. Por ejemplo, puede usar la configuración para configurar servicios y clientes en la implementación. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluye un conjunto grande de contadores de rendimiento para ayudarle a calibrar el rendimiento de su aplicación. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también expone datos de la inspección de un servicio en el tiempo de ejecución a través de un proveedor del Instrumental de administración de Windows (WMI) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Cuando la aplicación experimenta un error o comienza a actuar incorrectamente, puede utilizar el Registro de eventos para ver si algo significativo ha sucedido. También puede utilizar el registro y seguimiento de mensajes para ver qué eventos están pasando de un extremo a otro en su aplicación. Estas características ayudan a los programadores y a profesionales de TI a solucionar problemas de una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cuando estas no se comportan correctamente.  
  
> [!NOTE]
>  Si recibe errores sin información de detalle específico, debe habilitar la `includeExceptionDetailInFaults` atributo de la [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) elemento de configuración. De este modo se indica a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que envíe detalles de la excepción a los clientes, lo que permite detectar muchos problemas habituales sin tener que realizar un diagnóstico más avanzado. Para obtener más información, consulte [enviar y recibir errores](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Características de diagnóstico proporcionadas por WCF  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona las siguientes funcionalidades de diagnosis:  
  
-   El seguimiento de un extremo a otro proporciona datos de instrumentación para solucionar problemas de una aplicación sin usar un depurador. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera seguimientos para los hitos del proceso, así como mensajes de error. Esto puede incluir abrir un generador de canales o el envío y recepción de mensajes por parte un host de servicio. Se puede habilitar el seguimiento para una aplicación en ejecución para supervisar su progreso. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]el [seguimiento](../../../../docs/framework/wcf/diagnostics/tracing/index.md) tema. Para comprender cómo puede utilizar el seguimiento para depurar su aplicación, consulte el [utilizando el seguimiento para solucionar problemas de la aplicación](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) tema.  
  
-   El registro de mensajes le permite ver el aspecto de los mensajes antes y después de la transmisión. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]el [registro de mensajes](../../../../docs/framework/wcf/diagnostics/message-logging.md) tema.  
  
-   El seguimiento de eventos escribe los eventos en el Registro de eventos para poder ver cualquier problema importante. Puede usar a continuación el Visor de eventos para examinar cualquier anormalidad. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]el [un registro de eventos](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) tema.  
  
-   Los contadores de rendimiento expuestos a través del Monitor de rendimiento le permiten supervisar el estado de su aplicación y del sistema. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]el [contadores de rendimiento](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) tema.  
  
-   El espacio de nombres <xref:System.ServiceModel.Configuration> le permite cargar archivos de configuración y establecer un extremo de servicio o cliente. Puede utilizar el modelo de objetos para crear scripts con cambios para muchas aplicaciones cuando se deben implementar actualizaciones en muchos equipos. Como alternativa, puede usar el [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) para editar los valores de configuración mediante un asistente de interfaz gráfica de usuario. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]el [configuración de la aplicación](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) tema.  
  
-   WMI le permite averiguar qué servicios está realizando escuchas en un equipo y los enlaces que se están usando. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]el [utilizando Windows Management Instrumentation para diagnósticos](../../../../docs/framework/wcf/diagnostics/wmi/index.md) tema.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también proporciona varias herramientas de línea de comandos y GUI para facilitar la creación, implementación y administración de aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Herramientas de Windows Communication Foundation](../../../../docs/framework/wcf/tools.md). Por ejemplo, puede usar el [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) para crear y editar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] opciones de configuración mediante un asistente, en lugar de editar el XML directamente. También puede usar el [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) para ver, agrupar y filtrar los mensajes de seguimiento de modo que pueda diagnosticar, reparar y comprobar los problemas con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicios.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de su aplicación](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)  
 [Implementación de servicios](../../../../docs/framework/wcf/diagnostics/deploying-services.md)  
 [Referencia de excepciones](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)  
 [Registro de eventos](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [Registro de mensajes](../../../../docs/framework/wcf/diagnostics/message-logging.md)  
 [Herramienta del editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [Herramienta de registro ServiceModel](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)  
 [Traza](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Utilización del Instrumental de administración de Windows (WMI) para diagnósticos](../../../../docs/framework/wcf/diagnostics/wmi/index.md)  
 [Contadores de rendimiento](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)  
 [Herramientas de Windows Communication Foundation](../../../../docs/framework/wcf/tools.md)
