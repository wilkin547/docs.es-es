---
title: ServiceAuthorizationBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: eb02a02557a88bf53ca1a8e5b30fe66d6995e545
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="serviceauthorizationbehavior"></a>ServiceAuthorizationBehavior
ServiceAuthorizationBehavior  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
 Tipo de acceso: solo lectura  
  
 Un valor que controla si el servicio intenta suplantar mediante las credenciales proporcionadas por el mensaje entrante.  
  
### <a name="principalpermissionmode"></a>principalPermissionMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre de entidad de seguridad usado para llevar a cabo las operaciones en el servidor.  
  
### <a name="roleprovider"></a>RoleProvider  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre del proveedor de funciones de ASP.NET.  
  
### <a name="serviceauthorizationmanager"></a>ServiceAuthorizationManager  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El administrador de autorización utilizado para la autorización personalizada.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
