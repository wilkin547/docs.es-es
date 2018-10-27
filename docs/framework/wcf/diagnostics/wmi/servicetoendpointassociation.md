---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452714"
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation
Asigna un servicio a un punto de conexión.  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
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
