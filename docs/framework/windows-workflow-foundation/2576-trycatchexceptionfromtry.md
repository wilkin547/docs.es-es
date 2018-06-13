---
title: 2576 - TryCatchExceptionFromTry
ms.date: 03/30/2017
ms.assetid: 47e48973-b17c-4a16-8338-c84b54aa0a6e
ms.openlocfilehash: cdc48a1a08e997f7bc6a0ad6b93aa13640af9ed3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512700"
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
  
## <a name="message"></a>Mensaje  
 La actividad TryCatch '%1 ha detectado una excepción de tipo '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|Excepción|xs:string|Nombre del tipo de la excepción.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
