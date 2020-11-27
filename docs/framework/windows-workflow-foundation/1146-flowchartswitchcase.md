---
title: 1146 - FlowchartSwitchCase
ms.date: 03/30/2017
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
ms.openlocfilehash: 9636e5371440229ced965cf125ffb2ce4e314f72
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286115"
---
# <a name="1146---flowchartswitchcase"></a>1146 - FlowchartSwitchCase

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|1146|  
|Palabras clave|WFActivities|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica qué caso se ha seleccionado en un modificador de diagrama de flujo.  
  
## <a name="message"></a>Message  

 Flowchart '%1'/FlowSwitch - Se seleccionó el caso '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Diagrama de flujo|xs:string|El nombre para mostrar del diagrama de flujo.|  
|Caso|xs:string|Caso de roles que seleccionó.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
