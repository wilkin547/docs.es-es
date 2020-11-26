---
title: 'Servicio: Llamadas de seguridad no autorizadas'
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
ms.openlocfilehash: 32b0a62ecf9364270f5580787b7e129af5ac80b2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236915"
---
# <a name="service-security-calls-not-authorized"></a>Servicio: Llamadas de seguridad no autorizadas

Nombre de contenedor: llamadas de seguridad no autorizadas.  
  
## <a name="description"></a>Descripción  

 Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`. Indica que el mensaje entrante es de un usuario válido y que está debidamente protegido, pero dicho usuario no está autorizado a realizar tareas específicas.
