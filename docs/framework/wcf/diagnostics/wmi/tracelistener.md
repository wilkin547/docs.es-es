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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c0bba558a7b0c727dd971960ab3f9120a6aaada
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
