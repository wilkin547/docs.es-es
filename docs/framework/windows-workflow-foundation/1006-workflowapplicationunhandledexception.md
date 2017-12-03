---
title: 1006 - WorkflowApplicationUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a2dad3135de6d3d96328ea039aa36906addb217
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a>1006 - WorkflowApplicationUnhandledException
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1006|  
|Palabras clave|WFRuntime|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que una aplicación de flujo de trabajo ha detectado una excepción no controlada.  
  
## <a name="message"></a>Mensaje  
 WorkflowInstance Id: '%1' ha encontrado una excepción no controlada.  La excepción que se originó desde la actividad '%2', DisplayName: '%3'.  Se realizará la acción siguiente: %4.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|El id. de instancia del flujo de trabajo.|  
|Excepción|`xs:string`|Detalles de la excepción para la excepción|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
