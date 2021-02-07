---
description: 'Más información acerca de: 1146-FlowchartSwitchCase'
title: 1146 - FlowchartSwitchCase
ms.date: 03/30/2017
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
ms.openlocfilehash: f6e9b33f9c068b51695d3ac46cda51fb6d9f8b3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667075"
---
# <a name="1146---flowchartswitchcase"></a>1146 - FlowchartSwitchCase

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1146|  
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
