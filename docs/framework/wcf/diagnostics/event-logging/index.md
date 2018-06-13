---
title: Registro de eventos en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- event logging [WCF]
ms.assetid: aac0530d-f44c-45a1-bada-e30e0677b41f
ms.openlocfilehash: ea0e6f3dc66bf40d631077c0dce20ea46f3a6688
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804948"
---
# <a name="event-logging-in-wcf"></a>Registro de eventos en WCF
Windows Communication Foundation (WCF) realiza un seguimiento de los eventos internos en el registro de eventos de Windows.  
  
## <a name="viewing-event-logs"></a>Ver registros de eventos  
 El registro de eventos está habilitado automáticamente de forma predeterminada y no hay ningún mecanismo para deshabilitarlo. Eventos registrados por WCF se pueden ver mediante el Visor de eventos. Para iniciar esta herramienta, haga clic en **iniciar**, haga clic en **el Panel de Control**, haga doble clic en **herramientas administrativas**y, a continuación, haga doble clic en **Visor de eventos**.  
  
### <a name="application-event-log"></a>Registro de eventos de aplicación  
 El **registro de eventos de aplicación** contiene la mayoría de los eventos generados por WCF. La mayoría de las entradas indican que se produjo un error en una característica determinada en el inicio de una aplicación. Ejemplos:  
  
-   Registro y seguimiento de mensajes: WCF escribe un evento en el registro de eventos cuando se produce un error en el seguimiento y registro de mensajes. Sin embargo, no todos los errores de seguimiento desencadenan un evento. Para evitar que el registro de eventos se llena completamente con errores de seguimientos, WCF implementa un período de espera de 10 minutos para tal evento. Esto significa que si WCF escribe un error de seguimiento en el registro de eventos, no se realizará de nuevo para al menos 10 minutos.  
  
-   Agente de escucha compartido: el servicio de uso compartido de puertos WCF TCP registra un evento cuando no se inicia.  
  
-   [!INCLUDE[infocard](../../../../../includes/infocard-md.md)]: registra eventos cuando el servicio no se inicia.  
  
-   Eventos de error y graves, como errores de inicio o bloqueos  
  
-   El registro de mensajes activado: registra los eventos cuando se activa el registro de mensajes. Esto sirve para notificar al administrador que la información confidencial, específica de la aplicación puede estar registrada en encabezados del mensaje y cuerpos.  
  
-   Se registra un evento cuando se establece el atributo `enableLoggingKnownPII` en el elemento de `machineSettings` del archivo `machine.config`. Este atributo especifica si se permite a cualquier aplicación que se ejecuta en el equipo registrar la información de identificación personal conocida (PII).  
  
-   Si el atributo `logKnownPii` en o el archivo `app.config` o `web.config` está establecido en `true` para una aplicación concreta con el fin de activar el registro de PII, pero el atributo `enableLoggingKnownPII` del elemento `machineSettings` del archivo `machine.config` está establecido en `false`, se registra un evento. Además, si `logKnownPii` y `enableLoggingKnownPII` están establecidos en `true`, y el evento está registrado. Para obtener más información sobre estos valores de configuración, vea la sección de seguridad de la [configuración de registro de mensajes](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) tema.  
  
### <a name="security-event-log"></a>Registro de evento de seguridad  
 El **Security Event Log** contiene eventos de auditoría de seguridad que están registrados por WCF.  
  
### <a name="system-event-log"></a>Registro de eventos del sistema  
 WCF no registra nada el **registro de eventos de sistema**.  
  
### <a name="event-log-entries"></a>Entradas del registro de eventos  
 El **origen** de un evento es el nombre del ensamblado que genera la entrada del registro.  
  
 El tipo de una entrada del registro de eventos se utiliza para indicar la gravedad de un evento. Cada evento deber ser solo de un tipo, indicado por la aplicación cuando informa del evento. El Visor de eventos usa este tipo para determinar qué icono se debe mostrar en la vista de lista del registro. Para el tipo de evento diferente a una entrada del registro de eventos, vea <xref:System.Diagnostics.EventLogEntryType>.  
  
 Al hacer clic en "más información" cuando visualiza un evento en el Visor de eventos, el Visor de eventos puede enviar información a través de Internet. Para obtener más información, consulte ayuda de Visor de eventos.  
  
## <a name="see-also"></a>Vea también  
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Referencia general de eventos](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
