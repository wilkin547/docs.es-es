---
title: ServiceAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d948d1c77fc3f188694062ca9dcb3058f408c45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
