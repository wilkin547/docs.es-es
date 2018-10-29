---
title: Llamadas de seguridad no autorizadas
ms.date: 03/30/2017
ms.assetid: cb6acdcd-7336-42e1-9ae8-ac891336cd58
ms.openlocfilehash: 492886a8e0083e8993b68ad710229113faf79e8d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198411"
---
# <a name="security-calls-not-authorized"></a>Llamadas de seguridad no autorizadas
Nombre de contenedor: llamadas de seguridad no autorizadas.  
  
## <a name="description"></a>Descripción  
 Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`. Indica que el mensaje entrante es de un usuario válido y que está debidamente protegido, pero dicho usuario no está autorizado a realizar tareas específicas.
