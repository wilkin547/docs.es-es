---
title: Registro de eventos en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- event logging [WCF]
ms.assetid: aac0530d-f44c-45a1-bada-e30e0677b41f
ms.openlocfilehash: adff5bf2fad9f78fccbb606a5bd27f2f1dc32647
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638766"
---
# <a name="event-logging-in-wcf"></a>Registro de eventos en WCF
Windows Communication Foundation (WCF) realiza un seguimiento de eventos internos en el registro de eventos de Windows.  
  
## <a name="viewing-event-logs"></a>Ver registros de eventos  
 El registro de eventos está habilitado automáticamente de forma predeterminada y no hay ningún mecanismo para deshabilitarlo. Los eventos registrados por WCF pueden verse mediante el Visor de eventos. Para iniciar esta herramienta, haga clic en **iniciar**, haga clic en **Panel de Control**, haga doble clic en **herramientas administrativas**y, a continuación, haga doble clic en **Visor de eventos**.  
  
### <a name="application-event-log"></a>Registro de eventos de aplicación  
 El **Application Event Log** contiene la mayoría de los eventos generados por WCF. La mayoría de las entradas indican que se produjo un error en una característica determinada en el inicio de una aplicación. Ejemplos:  
  
- Registro y seguimiento de mensajes: WCF escribe un evento en el registro de eventos cuando se produce un error en el seguimiento y registro de mensajes. Sin embargo, no todos los errores de seguimiento desencadenan un evento. Para evitar que el registro de eventos que se rellena completamente con errores de seguimientos, WCF implementa un período de espera de 10 minutos para tal evento. Esto significa que si WCF escribe un error de seguimiento en el registro de eventos, no se realizará nuevamente para al menos 10 minutos.  
  
- Agente de escucha compartido: El servicio de uso compartido de puertos TCP de WCF se registra un evento cuando no se inicia.  
  
- [!INCLUDE[infocard](../../../../../includes/infocard-md.md)]: Registra los eventos cuando no se puede iniciar el servicio.  
  
- Eventos de error y graves, como errores de inicio o bloqueos  
  
- Registro de mensajes activado: Registra los eventos cuando se activa el registro de mensajes. Esto sirve para notificar al administrador que la información confidencial, específica de la aplicación puede estar registrada en encabezados del mensaje y cuerpos.  
  
- Se registra un evento cuando se establece el atributo `enableLoggingKnownPII` en el elemento de `machineSettings` del archivo `machine.config`. Este atributo especifica si se permite a cualquier aplicación que se ejecuta en el equipo registrar la información de identificación personal conocida (PII).  
  
- Si el atributo `logKnownPii` en o el archivo `app.config` o `web.config` está establecido en `true` para una aplicación concreta con el fin de activar el registro de PII, pero el atributo `enableLoggingKnownPII` del elemento `machineSettings` del archivo `machine.config` está establecido en `false`, se registra un evento. Además, si `logKnownPii` y `enableLoggingKnownPII` están establecidos en `true`, y el evento está registrado. Para obtener más información sobre estas opciones de configuración, consulte la sección de seguridad de la [Configuring Message Logging](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) tema.  
  
### <a name="security-event-log"></a>Registro de evento de seguridad  
 El **Security Event Log** contiene eventos de auditoría de seguridad que están registrados por WCF.  
  
### <a name="system-event-log"></a>Registro de eventos del sistema  
 WCF no registra nada el **registro de eventos del sistema**.  
  
### <a name="event-log-entries"></a>Entradas del registro de eventos  
 El **origen** de un evento es el nombre del ensamblado que genera la entrada del registro.  
  
 El tipo de una entrada del registro de eventos se utiliza para indicar la gravedad de un evento. Cada evento deber ser solo de un tipo, indicado por la aplicación cuando informa del evento. El Visor de eventos usa este tipo para determinar qué icono se debe mostrar en la vista de lista del registro. Para el tipo de evento diferente a una entrada del registro de eventos, vea <xref:System.Diagnostics.EventLogEntryType>.  
  
 Al hacer clic en "más información" al ver un evento en el Visor de eventos, el Visor de eventos puede enviar información a través de Internet. Para obtener más información, consulte ayuda de Visor de eventos.  
  
## <a name="see-also"></a>Vea también

- [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Referencia general de eventos](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
