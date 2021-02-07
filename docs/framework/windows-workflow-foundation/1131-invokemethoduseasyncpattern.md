---
description: 'Más información acerca de: 1131-InvokeMethodUseAsyncPattern'
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 59d8e5e1fe7c5b038df6fce3211fd01977abc4f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667322"
---
# <a name="1131---invokemethoduseasyncpattern"></a>1131 - InvokeMethodUseAsyncPattern

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1131|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.  
  
## <a name="message"></a>Message  

 InvokeMethod '%1': el método usa el patrón asincrónico de '%2' y '%3'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Identificación y nombre para mostrar de la actividad InvokeMethod.|  
|BeginMethod|xs:string|Nombre del método de inicio.|  
|EndMethod|xs:string|Nombre del método de fin.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
