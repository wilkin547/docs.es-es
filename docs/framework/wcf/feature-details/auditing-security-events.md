---
title: Auditoría de eventos de seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- auditing security events [WCF]
ms.assetid: 5633f61c-a3c9-40dd-8070-1c373b66a716
ms.openlocfilehash: 6505cc027b2983fd61ae53ca7ae43319024c74f7
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964714"
---
# <a name="auditing-security-events"></a>Auditoría de eventos de seguridad
Las aplicaciones creadas con Windows Communication Foundation (WCF) pueden registrar eventos de seguridad (correcto, error o ambos) con la característica de auditoría. Los eventos se escriben al registro de eventos del sistema de Windows y se pueden examinar utilizando el Visor de eventos.  
  
 La auditoría proporciona un método para que un administrador detecte un ataque que ya se ha producido o que está en curso. Además, auditar puede ayudar un desarrollador a depurar problemas relacionados con la seguridad. Por ejemplo, si un error en la configuración de la autorización o al comprobar la directiva niega accidentalmente el acceso a un usuario autorizado, un programador puede detectar y aislar rápidamente la causa de este error examinando el registro de eventos.  
  
 Para obtener más información sobre la seguridad de WCF, vea [información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md). Para obtener más información acerca de la programación de WCF, vea [programación básica de WCF](../../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="audit-level-and-behavior"></a>Nivel de auditoría y comportamiento  
 Existen dos niveles de auditorías de seguridad:  
  
- Nivel de autorización de servicio, en el que un llamador está autorizado.  
  
- Nivel de mensaje, en el que WCF comprueba la validez del mensaje y autentica al autor de la llamada.  
  
 Puede comprobar si ambos niveles de auditoría son correctos o erróneos, lo que se conoce como *comportamiento de auditoría*.  
  
## <a name="audit-log-location"></a>Ubicación del registro de auditoría  
 Una vez que determina el nivel y comportamiento de una auditoría, usted (o un administrador) puede especificar una ubicación para el registro de auditoría. Hay tres opciones: valor predeterminado, aplicación y seguridad. Al especificar Predeterminado, el registro real depende de qué sistema esté usando y de si el sistema permite escribir en el registro de seguridad. Para obtener más información, vea la sección "sistema operativo" más adelante en este tema.  
  
 Para escribir en el registro de seguridad es necesario el `SeAuditPrivilege`. De forma predeterminada, solo las cuentas de Sistema local y Servicio de red tienen este privilegio. Para administrar las funciones del registro de seguridad `read` y `delete` es necesario `SeSecurityPrivilege`. De forma predeterminada, solo los administradores tienen este privilegio.  
  
 En cambio, los usuarios autenticados pueden leer y escribir en el registro de aplicaciones. [!INCLUDE[wxp](../../../../includes/wxp-md.md)] escribe de forma predeterminada los eventos de auditoría en el registro de aplicaciones. El registro también puede contener datos personales que son visibles para todos los usuarios autenticados.  
  
## <a name="suppressing-audit-failures"></a>Suprimir los errores de la auditoría  
 Otra opción durante la auditoría es la de suprimir los errores de la auditoría. De forma predeterminada, un error de la auditoría no afecta a una aplicación. Si fuese necesario, sin embargo, puede establecer la opción en `false`, que hace que se produzca una excepción.  
  
## <a name="programming-auditing"></a>Programación de auditoría  
 Puede especificar el comportamiento de la auditoría mediante configuración o programación.  
  
### <a name="auditing-classes"></a>Clases de auditorías  
 La tabla siguiente describe las clases y propiedades utilizadas para programar el comportamiento de la auditoría.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>|Habilita opciones de configuración para la auditoría como un comportamiento de servicio.|  
|<xref:System.ServiceModel.AuditLogLocation>|Enumeración para especificar en qué registro escribir. Los valores posibles son Predeterminado, Aplicación y Seguridad. Si se selecciona Predeterminado, el sistema operativo determina la ubicación del registro real. Vea la sección "Elección de registro de eventos de seguridad o aplicación" más adelante en este tema.|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A>|Especifica qué tipos de eventos de autenticación de mensajes se auditan en el nivel de mensaje. Las opciones son `None`, `Failure`, `Success` y `SuccessOrFailure`.|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A>|Especifica qué tipos de eventos de autorización de servicio se auditan en el nivel de servicio. Las opciones son `None`, `Failure`, `Success` y `SuccessOrFailure`.|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A>|Especifica lo que pasa a la solicitud de cliente cuando se produce un error al auditar. Por ejemplo, cuando el servicio intenta escribir en el registro de seguridad, pero no tiene `SeAuditPrivilege`. El valor predeterminado de `true` indica que se pasan por alto los errores, y se procesa la solicitud de cliente como de costumbre.|  
  
 Para obtener un ejemplo de cómo configurar una aplicación para registrar eventos de auditoría, consulte [Cómo: auditar eventos de seguridad](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).  
  
### <a name="configuration"></a>Configuración de  
 También puede usar la configuración para especificar el comportamiento de auditoría agregando un [\<serviceSecurityAudit >](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) en el [> comportamientos de\<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md). Debe agregar el elemento bajo un [\<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) como se muestra en el código siguiente.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <behavior>  
        <!-- auditLogLocation="Application" or "Security" -->  
        <serviceSecurityAudit  
                  auditLogLocation="Application"  
                  suppressAuditFailure="true"  
                  serviceAuthorizationAuditLevel="Failure"  
                  messageAuthenticationAuditLevel="SuccessOrFailure" />   
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Si auditar está habilitado y no se especifica una `auditLogLocation`, el nombre del registro predeterminado es "Seguridad", para que la plataforma admita la escritura en el registro de seguridad; de lo contrario, el nombre será "Aplicación". Solo los sistemas operativos Windows Server 2003 y Windows Vista admiten la escritura en el registro de seguridad. Para obtener más información, vea la sección "sistema operativo" más adelante en este tema.  
  
## <a name="security-considerations"></a>Consideraciones de seguridad  
 Si un usuario malintencionado sabe que la auditoría está habilitada, el atacante puede enviar mensajes no válidos y de este modo hacer que se escriban entradas de auditoría. Si el registro de auditoría se rellena de esta manera, el sistema de auditoría falla. Para mitigar esto, establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> en `true` y use las propiedades del Visor de eventos para controlar el comportamiento de la auditoría.  
  
 Los eventos de auditoría que se escriben en el registro de aplicaciones en [!INCLUDE[wxp](../../../../includes/wxp-md.md)] puede verlos cualquier usuario autenticado.  
  
## <a name="choosing-between-application-and-security-event-logs"></a>Elegir entre registros de eventos de seguridad o aplicación  
 Las siguientes tablas proporcionan información para ayudarle a decidir si registrar en el registro de eventos de aplicación o de seguridad.  
  
#### <a name="operating-system"></a>Sistema operativo  
  
|System|Registro de aplicaciones|Registro de seguridad|  
|------------|---------------------|------------------|  
|[!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)] o posterior|admitido|No compatibles|  
|Windows Server 2003 SP1 y Windows Vista|admitido|El contexto del subproceso debe poseer `SeAuditPrivilege`|  
  
#### <a name="other-factors"></a>Otros factores  
 Además del sistema operativo, la tabla siguiente describe otros valores que controlan la habilitación de los registros.  
  
|Factor|Registro de aplicaciones|Registro de seguridad|  
|------------|---------------------|------------------|  
|Administración de la directiva de auditoría|No es aplicable.|La directiva de la autoridad de seguridad local (LSA) controla el registro de Seguridad, además de la configuración. También se ha de habilitar la categoría “Acceso a objetos de auditoría”.|  
|Experiencia de usuario predeterminada|Todos los usuarios autenticados pueden escribir en el registro de aplicaciones, por lo que no es necesario ningún paso de permiso adicional para los procesos de aplicación.|El proceso de aplicación (contexto) debe tener `SeAuditPrivilege`.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Programación básica de WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [Auditoría de eventos de seguridad](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)
- [\<serviceSecurityAudit>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)
- [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
- [Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
