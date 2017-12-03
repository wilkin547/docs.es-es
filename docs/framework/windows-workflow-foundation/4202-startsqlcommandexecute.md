---
title: 4202 - StartSqlCommandExecute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d54660ed7f278b1f82fac81c31b8a30e20a2e7d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="4202---startsqlcommandexecute"></a>4202 - StartSqlCommandExecute
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|4202|  
|Palabras clave|WFInstanceStore|  
|Nivel|Detallado|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que se está ejecutando un comando SQL.  
  
## <a name="message"></a>Mensaje  
 Ejecución de comando SQL inicial: %1  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|SqlCommand|xs:string|El comando SQL que se ejecutó.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
