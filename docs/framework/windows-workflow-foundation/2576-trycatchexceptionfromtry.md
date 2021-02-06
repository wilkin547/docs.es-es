---
description: 'Más información acerca de: 2576-TryCatchExceptionFromTry'
title: 2576 - TryCatchExceptionFromTry
ms.date: 03/30/2017
ms.assetid: 47e48973-b17c-4a16-8338-c84b54aa0a6e
ms.openlocfilehash: 83e26726377a9f8bbedda2a310dcf4ee6928d3a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631532"
---
# <a name="2576---trycatchexceptionfromtry"></a>2576 - TryCatchExceptionFromTry

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|2576|  
|Palabras clave|WFActivities|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que la actividad TryCatch ha detectado una excepción.  
  
## <a name="message"></a>Message  

 La actividad TryCatch '%1 ha detectado una excepción de tipo '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|Excepción|xs:string|Nombre del tipo de la excepción.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
