---
description: 'Más información acerca de: 1041-WorkflowApplicationPersistableIdle'
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: eb004077a36ed3e78229df92a73972ed5feda665
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667764"
---
# <a name="1041---workflowapplicationpersistableidle"></a>1041 - WorkflowApplicationPersistableIdle

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1041|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que una aplicación de flujo de trabajo está inactiva y con persistencia. La aplicación de flujo de trabajo estará inactiva o se conservará.  
  
## <a name="message"></a>Message  

 WorkflowApplication ID: ' %1 ' está inactivo y es persistente.  Se realizará la siguiente acción: %2.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|xs:string|Identificador de la aplicación del flujo de trabajo.|  
|ActionTaken|xs:string|La acción que se adoptará en la aplicación de flujo de trabajo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
