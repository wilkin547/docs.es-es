---
title: 1146 - FlowchartSwitchCase
ms.date: 03/30/2017
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
ms.openlocfilehash: 9f4e3af664ed30634e4b56f16cd6caf2366c3674
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923908"
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
  
## <a name="message"></a>Mensaje  
 Flowchart '%1'/FlowSwitch - Se seleccionó el caso '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Diagrama de flujo|xs:string|El nombre para mostrar del diagrama de flujo.|  
|Caso|xs:string|Caso de roles que seleccionó.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
