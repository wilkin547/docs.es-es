---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: dc48b8742c60714720be3cf4b22ba672f73c720a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570231"
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
