---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: e8b24877c2d76a3f2f90c27ae83374c7bca1328b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181165"
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
  
 Tipo de acceso: solo lectura  
  
 La ubicación del registro de auditoría.  
  
### <a name="messageauthenticationauditlevel"></a>MessageAuthenticationAuditLevel  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El tipo de nivel de autenticación de mensajes que se usa para registrar eventos de auditoría.  
  
### <a name="serviceauthorizationauditlevel"></a>ServiceAuthorizationAuditLevel  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Los tipos de eventos de autorización que se graban en el registro de auditoría.  
  
### <a name="suppressauditfailure"></a>SuppressAuditFailure  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica el comportamiento para suprimir errores al escribir en el registro de auditoría.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
