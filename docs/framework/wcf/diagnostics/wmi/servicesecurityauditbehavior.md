---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979139"
---
# <a name="servicesecurityauditbehavior"></a>ServiceSecurityAuditBehavior
ServiceSecurityAuditBehavior  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ServiceSecurityAuditBehavior no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ServiceSecurityAuditBehavior tiene las propiedades siguientes:  
  
### <a name="auditloglocation"></a>AuditLogLocation  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 La ubicación del registro de auditoría.  
  
### <a name="messageauthenticationauditlevel"></a>MessageAuthenticationAuditLevel  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El tipo de nivel de autenticación de mensajes que se usa para registrar eventos de auditoría.  
  
### <a name="serviceauthorizationauditlevel"></a>ServiceAuthorizationAuditLevel  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Los tipos de eventos de autorización que se graban en el registro de auditoría.  
  
### <a name="suppressauditfailure"></a>SuppressAuditFailure  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Un valor booleano que especifica el comportamiento para suprimir errores al escribir en el registro de auditoría.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
