---
title: 'Servicio: Llamadas de seguridad no autorizadas'
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
author: BrucePerlerMS
ms.openlocfilehash: f90ed5746c8b798e55b7e300ba7ff63bbafdcac4
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035888"
---
# <a name="service-security-calls-not-authorized"></a>Servicio: Llamadas de seguridad no autorizadas
Nombre de contenedor: llamadas de seguridad no autorizadas.  
  
## <a name="description"></a>Descripción  
 Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`. Indica que el mensaje entrante es de un usuario válido y que está debidamente protegido, pero dicho usuario no está autorizado a realizar tareas específicas.
