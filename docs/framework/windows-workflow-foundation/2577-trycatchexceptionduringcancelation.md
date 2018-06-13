---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: c272dd91249dfc90e6f4c38a7339919a5a6446e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510736"
---
# <a name="2577---trycatchexceptionduringcancelation"></a>2577 - TryCatchExceptionDuringCancelation
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|2577|  
|Palabras clave|WFActivities|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que una actividad secundaria de la actividad TryCatch ha producido una excepción durante la cancelación.  
  
## <a name="message"></a>Mensaje  
 Una actividad secundaria de la actividad TryCatch '%1' produjo una excepción durante la cancelación.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
