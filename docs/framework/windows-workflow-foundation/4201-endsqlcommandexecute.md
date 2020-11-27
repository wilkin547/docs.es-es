---
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 0d6326889077e36ad49aa6267ae7285849c6818d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275871"
---
# <a name="4201---endsqlcommandexecute"></a>4201 - EndSqlCommandExecute

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|4201|  
|Palabras clave|WFInstanceStore|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que un comando SQL ha terminado de ejecutarse.  
  
## <a name="message"></a>Message  

 Ejecución de comando SQL final: %1  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|SqlCommand|xs:string|El comando SQL que se ejecutó.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
