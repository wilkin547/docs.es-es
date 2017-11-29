---
title: 4205 - FoundProcessingError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2235a15-dd87-439e-8cb9-8b1b89a3dacf
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 376e90de00759a88c6c938f2125653161d8e5201
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="4205---foundprocessingerror"></a>4205 - FoundProcessingError
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|4205|  
|Palabras clave|WFInstanceStore|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que comando de proveedor SQL ha generado un error.  
  
## <a name="message"></a>Mensaje  
 Error de comando: %1  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|ExceptionMessage|xs:string|El mensaje de la excepción SQL.|  
|Excepción|xs:string|Detalles de la excepción para la excepción|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
