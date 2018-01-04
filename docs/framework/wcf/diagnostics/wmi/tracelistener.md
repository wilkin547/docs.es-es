---
title: TraceListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2c0b595-a384-4eb3-b94d-1b3be7cc7a5c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 842201c0d3a36c69dea1e947f38eb0430533ea24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="tracelistener"></a>TraceListener
TraceListener  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class TraceListener  
{  
  string Name;  
  TraceListenerArgument TraceListenerArguments[];  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase TraceListener no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase TraceListener tiene las propiedades siguientes:  
  
### <a name="name"></a>Name  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre del agente de escucha de seguimiento.  
  
### <a name="tracelistenerarguments"></a>TraceListenerArgument  
 Tipo de datos: Matriz de TraceListenerArgument  
  
 Tipo de acceso: solo lectura  
  
 Los argumentos del agente de escucha de seguimiento.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|
