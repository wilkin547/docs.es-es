---
description: 'Más información acerca de: ServiceToEndpointAssociation'
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 1ae2ce2bcc0b3494b00fffa750f3ca46d26fe08f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715345"
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation

Asigna un servicio a un extremo.  
  
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
