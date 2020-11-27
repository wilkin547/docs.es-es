---
title: 4202 - StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: d3f27c6ed28efe9d099dcedfc676b839ae9b1dee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275845"
---
# <a name="4202---startsqlcommandexecute"></a>4202 - StartSqlCommandExecute

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|4202|  
|Palabras clave|WFInstanceStore|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que se está ejecutando un comando SQL.  
  
## <a name="message"></a>Message  

 Ejecución de comando SQL inicial: %1  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|SqlCommand|xs:string|El comando SQL que se ejecutó.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
