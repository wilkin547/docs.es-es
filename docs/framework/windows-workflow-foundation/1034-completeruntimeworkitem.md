---
description: 'Más información acerca de: 1034-CompleteRuntimeWorkItem'
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: dd8a9fcb2fb692ab3b69df8f07f6a96cf48fc806
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667972"
---
# <a name="1034---completeruntimeworkitem"></a>1034 - CompleteRuntimeWorkItem

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1034|  
|Palabras clave|WFRuntime|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que se ha completado un RuntimeWorkItem.  
  
## <a name="message"></a>Message  

 Se ha completado un elemento de trabajo en runtime para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Actividad|xs:string|El nombre de tipo de la actividad.|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|InstanceId|xs:string|La identificación de instancia de la actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
