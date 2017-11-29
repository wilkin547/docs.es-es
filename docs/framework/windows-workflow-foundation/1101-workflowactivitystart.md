---
title: 1101 - WorkflowActivityStart
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 831cd386-b9b5-47a9-9690-aff6292ff348
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d89b6f41838ee89b503746be4020b93db0ac96e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1101---workflowactivitystart"></a>1101 - WorkflowActivityStart
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1101|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que la actividad de flujo de trabajo se ha iniciado.  
  
## <a name="message"></a>Mensaje  
 Id. de WorkflowInstance: '%1' actividad E2E  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|Identificación de instancia del flujo de trabajo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
