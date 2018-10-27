---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192244"
---
# <a name="serviceappdomain"></a>ServiceAppDomain
Asigna un servicio a un dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
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
