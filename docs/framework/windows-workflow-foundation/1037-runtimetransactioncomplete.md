---
description: 'Más información acerca de: 1037-RuntimeTransactionComplete'
title: 1037 - RuntimeTransactionComplete
ms.date: 03/30/2017
ms.assetid: 2c8c31e0-42a9-4f46-865b-2da9ab16a0ba
ms.openlocfilehash: 5784dc1b0eede5ddad0e6aae4cb79c6e859f325e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667868"
---
# <a name="1037---runtimetransactioncomplete"></a>1037 - RuntimeTransactionComplete

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1037|  
|Palabras clave|WFRuntime|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que la transacción en runtime se ha completado.  
  
## <a name="message"></a>Message  

 La transacción en runtime se ha completado con el estado '%1'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|State|xs:string|Estado de la transacción.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
