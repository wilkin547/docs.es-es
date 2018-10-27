---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194779"
---
# <a name="wsattracerecord"></a>WSAT_TraceRecord
WSAT_TraceRecord  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase WSAT_TraceRecord no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase WSAT_TraceRecord tiene las propiedades siguientes:  
  
### <a name="activityid"></a>ActivityID  
 Tipo de datos: objeto  
Tipo de acceso: solo lectura  
  
 El id. de actividad del registro de seguimiento.  
  
### <a name="eventid"></a>Id. de evento  
 Tipo de datos: sint32  
Tipo de acceso: solo lectura  
  
 El id. de evento del registro de seguimiento.  
  
### <a name="tracerecord"></a>TraceRecord  
 Tipo de datos: cadena  
Tipo de acceso: solo lectura  
  
 Registro de seguimiento  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|
