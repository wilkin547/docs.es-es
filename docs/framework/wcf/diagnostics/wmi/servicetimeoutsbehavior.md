---
description: 'Más información acerca de: ServiceTimeoutsBehavior'
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 147d249af0e87bc41da93a4a31355da7053caaf6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715423"
---
# <a name="servicetimeoutsbehavior"></a>ServiceTimeoutsBehavior

ServiceTimeoutsBehavior  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a>Métodos  

 La clase ServiceTimeoutsBehavior no define ningún método.  
  
## <a name="properties"></a>Propiedades  

 La clase ServiceTimeoutsBehavior tiene la siguiente propiedad:  
  
### <a name="transactiontimeout"></a>TransactionTimeout  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El período dentro del que una transacción se debe completar.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
