---
title: TraceListener
ms.date: 03/30/2017
ms.assetid: c2c0b595-a384-4eb3-b94d-1b3be7cc7a5c
ms.openlocfilehash: 1bd15aafc85e5553a4b4acef6901beb9a0f1745e
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50033355"
---
# <a name="tracelistener"></a>TraceListener
TraceListener  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
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
