---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964301"
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
