---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: 58eb2a9fd9017aaf9966644180936f5871e086d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613901"
---
# <a name="serviceauthorizationbehavior"></a>ServiceAuthorizationBehavior
ServiceAuthorizationBehavior  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ServiceAuthorizationBehavior no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ServiceAuthorizationBehavior tiene las propiedades siguientes:  
  
### <a name="impersonatecallerforalloperations"></a>ImpersonateCallerForAllOperations  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Un valor que controla si el servicio intenta suplantar mediante las credenciales proporcionadas por el mensaje entrante.  
  
### <a name="principalpermissionmode"></a>principalPermissionMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El nombre de entidad de seguridad usado para llevar a cabo las operaciones en el servidor.  
  
### <a name="roleprovider"></a>RoleProvider  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Nombre del proveedor de funciones de ASP.NET.  
  
### <a name="serviceauthorizationmanager"></a>ServiceAuthorizationManager  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El administrador de autorización utilizado para la autorización personalizada.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
