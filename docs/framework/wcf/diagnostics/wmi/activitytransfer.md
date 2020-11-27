---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291120"
---
# <a name="activitytransfer"></a>ActivityTransfer

Evento de transferencia de actividad  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>Métodos  

 La clase ActivityTransfer no define ningún método.  
  
## <a name="properties"></a>Propiedades  

 La clase ActivityTransfer posee las propiedades siguientes:  
  
### <a name="activityid"></a>Identificador de actividad  
  
- Tipo de datos: objeto  
    Tipo de acceso: solo lectura  
  
- Identificador de actividad  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
- Tipo de datos: objeto  
    Tipo de acceso: solo lectura  
  
- Id. de actividad relacionada  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel.|
