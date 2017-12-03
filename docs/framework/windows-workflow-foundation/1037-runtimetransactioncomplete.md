---
title: 1037 - RuntimeTransactionComplete
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c8c31e0-42a9-4f46-865b-2da9ab16a0ba
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31333ddeca7a6ef555413d09864e55834ff4a2b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1037---runtimetransactioncomplete"></a>1037 - RuntimeTransactionComplete
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1037|  
|Palabras clave|WFRuntime|  
|Nivel|Detallado|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que la transacción en tiempo de ejecución se ha completado.  
  
## <a name="message"></a>Mensaje  
 La transacción en tiempo de ejecución se ha completado con el estado '%1'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Estado|xs:string|Estado de la transacción.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
