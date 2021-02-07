---
description: 'Más información acerca de: ActivityTransfer'
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 28f7d1c0d1056327313e7aa6be293eb325d8f265
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99758013"
---
# <a name="activitytransfer"></a>ActivityTransfer

Evento de transferencia de actividad  
  
## <a name="syntax"></a>Sintaxis  
  
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
