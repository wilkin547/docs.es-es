---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: b1e5b87b053e947432cba9f6e716f7d1ea8f013f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
