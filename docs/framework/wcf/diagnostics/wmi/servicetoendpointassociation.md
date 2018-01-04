---
title: ServiceToEndpointAssociation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da8703b80f2fbcc2f02eb64c94baf0707a1a93bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation
Asigna un servicio a un punto de conexión.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ServiceToEndpointAssociation no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ServiceToEndpointAssociation tiene las propiedades siguientes:  
  
### <a name="ref"></a>ref  
 Tipo de datos: servicio  
  
 Tipo de acceso: solo lectura  
Calificadores: clave  
  
 El servicio asociado con el punto de conexión.  
  
### <a name="ref"></a>ref  
 Tipo de datos: extremo  
  
 Tipo de acceso: solo lectura  
Calificadores: clave  
  
 El punto de conexión asociado con el servicio.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|
