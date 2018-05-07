---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: aef0a0da9d107b92d9d3017968d5554205a6fd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="serviceappdomain"></a>ServiceAppDomain
Asigna un servicio a un dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ServiceAppDomain no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ServiceAppDomain posee las siguientes propiedades:  
  
### <a name="ref"></a>ref  
 Tipo de datos: servicio  
Calificadores: clave  
  
 Tipo de acceso: solo lectura  
  
 Servicio de este dominio de aplicación.  
  
### <a name="ref"></a>ref  
 Tipo de datos: AppDomainInfo  
Calificadores: clave  
  
 Tipo de acceso: solo lectura  
  
 Contiene propiedades del dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|
