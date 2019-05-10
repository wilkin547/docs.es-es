---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 6237d65d6964a4ebca34af895158c83239641593
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662822"
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
  
### <a name="activityid"></a>ActivityID  
  
- Tipo de datos: objeto  
    Tipo de acceso: De sólo lectura  
  
- Id. de actividad  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
- Tipo de datos: objeto  
    Tipo de acceso: De sólo lectura  
  
- Id. de actividad relacionada  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel.|
