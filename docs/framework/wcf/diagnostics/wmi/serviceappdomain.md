---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 243c9112dd9caf5c92ef77aa0f45b4b1e71a4e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273261"
---
# <a name="serviceappdomain"></a>ServiceAppDomain

Asigna un servicio a un dominio de aplicación.  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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
