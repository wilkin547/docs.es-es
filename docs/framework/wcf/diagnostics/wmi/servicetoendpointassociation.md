---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 6e20556541b1aa48e7dfc6a8cde97e1bc477457e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273950"
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation

Asigna un servicio a un extremo.  
  
## <a name="syntax"></a>Syntax  
  
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
  
 El servicio asociado con el extremo.  
  
### <a name="ref"></a>ref  

 Tipo de datos: punto de conexión  
  
 Tipo de acceso: solo lectura  
Calificadores: clave  
  
 El punto de conexión asociado con el servicio.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|
