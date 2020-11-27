---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: c3174e70d42385923674a3db5f696a0f64eda29f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295370"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a>CoordinatorRecoveryLogEntryCorrupt

ID.: 139  
  
 Gravedad: error  
  
 Categoría: TransactionBridge  
  
## <a name="description"></a>Descripción  

 Este evento indica que una entrada del registro de recuperación de coordinador estaba dañada y no se pudo deserializar. Se pueden producir pérdidas de datos como resultado de este error. El evento detalla una lista de id. de transacción, datos de recuperación (codificados con Base64), excepción, nombre de proceso e id. de proceso.  
  
## <a name="see-also"></a>Vea también

- [Registro de eventos](index.md)
- [Referencia general de eventos](events-general-reference.md)
