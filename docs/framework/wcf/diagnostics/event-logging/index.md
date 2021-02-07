---
description: 'Más información acerca de: registro de eventos en WCF'
title: Registro de eventos en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- event logging [WCF]
ms.assetid: aac0530d-f44c-45a1-bada-e30e0677b41f
ms.openlocfilehash: 741e6efce9f5fffec607d511f04a400e1292b682
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99744219"
---
# <a name="event-logging-in-wcf"></a>Registro de eventos en WCF

Windows Communication Foundation (WCF) realiza un seguimiento de los eventos internos en el registro de eventos de Windows.  
  
## <a name="viewing-event-logs"></a>Ver registros de eventos  

 El registro de eventos está habilitado automáticamente de forma predeterminada y no hay ningún mecanismo para deshabilitarlo. Los eventos registrados por WCF se pueden ver mediante el Visor de eventos. Para iniciar esta herramienta, haga clic en **Inicio**, en **Panel de control**, haga doble clic en **herramientas administrativas** y, a continuación, haga doble clic en **visor de eventos**.  
  
### <a name="application-event-log"></a>Registro de eventos de aplicación  

 El **registro de eventos de aplicación** contiene la mayoría de los eventos generados por WCF. La mayoría de las entradas indican que se produjo un error en una característica determinada en el inicio de una aplicación. Algunos ejemplos son:  
  
- Registro/seguimiento de mensajes: WCF escribe un evento en el registro de eventos cuando se produce un error en el registro de seguimiento y de mensajes. Sin embargo, no todos los errores de seguimiento desencadenan un evento. Para evitar que el registro de eventos se llene completamente con errores de seguimiento, WCF implementa un período de disponibilidad de 10 minutos para este tipo de evento. Esto significa que si WCF escribe un error de seguimiento en el registro de eventos, no lo hará de nuevo durante al menos 10 minutos.  
  
- Agente de escucha compartido: el servicio de uso compartido de puertos WCF TCP registra un evento cuando no se inicia.  
  
- CardSpace: registra eventos cuando el servicio no se inicia.  
  
- Eventos de error y graves, como errores de inicio o bloqueos  
  
- El registro de mensajes activado: registra los eventos cuando se activa el registro de mensajes. Esto sirve para notificar al administrador que la información confidencial, específica de la aplicación puede estar registrada en encabezados del mensaje y cuerpos.  
  
- Se registra un evento cuando se establece el atributo `enableLoggingKnownPII` en el elemento de `machineSettings` del archivo `machine.config`. Este atributo especifica si se permite a cualquier aplicación que se ejecuta en el equipo registrar la información de identificación personal conocida (PII).  
  
- Si el atributo `logKnownPii` en o el archivo `app.config` o `web.config` está establecido en `true` para una aplicación concreta con el fin de activar el registro de PII, pero el atributo `enableLoggingKnownPII` del elemento `machineSettings` del archivo `machine.config` está establecido en `false`, se registra un evento. Además, si `logKnownPii` y `enableLoggingKnownPII` están establecidos en `true`, y el evento está registrado. Para obtener más información sobre estas opciones de configuración, consulte la sección seguridad del tema [configuración del registro de mensajes](../configuring-message-logging.md) .  
  
### <a name="security-event-log"></a>Registro de evento de seguridad  

 El **registro de eventos de seguridad** contiene eventos de auditoría de seguridad registrados por WCF.  
  
### <a name="system-event-log"></a>Registro de eventos del sistema  

 WCF no registra nada en el **registro de eventos del sistema**.  
  
### <a name="event-log-entries"></a>Entradas del registro de eventos  

 El **origen** de un evento es el nombre del ensamblado que genera la entrada de registro.  
  
 El tipo de una entrada del registro de eventos se utiliza para indicar la gravedad de un evento. Cada evento deber ser solo de un tipo, indicado por la aplicación cuando informa del evento. El Visor de eventos usa este tipo para determinar qué icono se debe mostrar en la vista de lista del registro. Para el tipo de evento diferente a una entrada del registro de eventos, vea <xref:System.Diagnostics.EventLogEntryType>.  
  
 Al hacer clic en "más información" al ver un evento en el Visor de eventos, el Visor de eventos puede enviar información a través de Internet. Para obtener más información, consulte ayuda de Visor de eventos.  
  
## <a name="see-also"></a>Vea también

- [Administración y diagnóstico](../index.md)
- [Referencia general de eventos](events-general-reference.md)
