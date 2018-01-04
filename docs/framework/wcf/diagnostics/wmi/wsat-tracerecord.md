---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d24f74d4086a5499d3bfd4ef6183d377528acc21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wsattracerecord"></a>WSAT_TraceRecord
WSAT_TraceRecord  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
