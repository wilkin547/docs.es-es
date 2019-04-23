---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: 51555e3357b8c33a53261c4894d97798b0a05656
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59972841"
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
