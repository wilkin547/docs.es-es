---
description: 'Más información acerca de: WSAT_TraceRecord'
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 67202c5d2910783c40b934d2da6108e6b514a728
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756882"
---
# <a name="wsat_tracerecord"></a>WSAT_TraceRecord

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
  
### <a name="activityid"></a>Identificador de actividad  

 Tipo de datos: objeto  
Tipo de acceso: solo lectura  
  
 El id. de actividad del registro de seguimiento.  
  
### <a name="eventid"></a>EventId  

 Tipo de datos: sint32  
Tipo de acceso: solo lectura  
  
 El id. de evento del registro de seguimiento.  
  
### <a name="tracerecord"></a>TraceRecord  

 Tipo de datos: cadena  
Tipo de acceso: solo lectura  
  
 Registro de seguimiento  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|
