---
description: 'Más información acerca de: 1040-InArgumentBound'
title: 1040 - InArgumentBound
ms.date: 03/30/2017
ms.assetid: 7dfaad1b-36c0-4575-84c1-31d63b0eaf5d
ms.openlocfilehash: f604a2503bcaf407a9a690b5a681208815fd245a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667803"
---
# <a name="1040---inargumentbound"></a>1040 - InArgumentBound

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1040|  
|Palabras clave|WFActivities|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que un argumento In se ha enlazado.  
  
## <a name="message"></a>Message  

 El argumento '%1' en la actividad '%2', DisplayName: '%3', InstanceId: '%4' se ha enlazado con el valor: %5.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InArgument|xs:string|Nombre de InArgument.|  
|Actividad|xs:string|El nombre de tipo de la actividad.|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|InstanceId|xs:string|La identificación de instancia de la actividad.|  
|Value|xs:string|El valor enlazó al InArgument.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
