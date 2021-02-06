---
description: 'Más información acerca de: 3507-ServiceEndpointAdded'
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: 7de51cb8908d3bf4b450c545c1a4c0f2bdc6a453
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631481"
---
# <a name="3507---serviceendpointadded"></a>3507 - ServiceEndpointAdded

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|3507|  
|Palabras clave|WFServices|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Indica que se ha agregado un punto de conexión de servicio.  
  
## <a name="message"></a>Message  

 Se ha agregado un extremo de servicio a la dirección '%1', enlace '%2', y contrato '%3'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Dirección|xs:string|Dirección del extremo.|  
|Enlace|xs:string|El enlace del punto de conexión.|  
|Contrato|xs:string|Contrato del punto de conexión.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
