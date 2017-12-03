---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93a6a400576df84faae3cd58940462255b0073c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1002---workflowapplicationterminated"></a>1002 - WorkflowApplicationTerminated
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1002|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que una aplicación de flujo de trabajo ha finalizado en el estado Faulted con una excepción.  
  
## <a name="message"></a>Mensaje  
 WorkflowApplication Id: '%1' se terminó. Se ha completado con el estado Faulted y con una excepción.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|`xs:string`|Identificador de la aplicación del flujo de trabajo.|  
|Excepción|`xs:string`|Detalles de la excepción para la excepción|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
