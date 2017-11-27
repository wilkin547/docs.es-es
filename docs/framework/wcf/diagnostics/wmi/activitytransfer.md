---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acbc346da940caf933868a03295744132bda4733
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="activitytransfer"></a>ActivityTransfer
Evento de transferencia de actividad  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
-   Tipo de datos: objeto  
    Tipo de acceso: solo lectura  
  
-   Id. de actividad  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
-   Tipo de datos: objeto  
    Tipo de acceso: solo lectura  
  
-   Id. de actividad relacionada  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel.|
