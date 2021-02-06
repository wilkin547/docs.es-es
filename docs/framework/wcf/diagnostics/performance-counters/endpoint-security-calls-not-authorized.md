---
description: 'Más información acerca de: punto de conexión: llamadas de seguridad no autorizadas'
title: 'punto de conexión: Llamadas de seguridad no autorizadas'
ms.date: 03/30/2017
ms.assetid: d25095ff-9ff0-4c69-a674-4e6a9fe3f4dc
ms.openlocfilehash: 258c984e8a7986594b6da6f5c2a8c030907f82ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655479"
---
# <a name="endpoint-security-calls-not-authorized"></a>punto de conexión: Llamadas de seguridad no autorizadas

Nombre de contenedor: llamadas de seguridad no autorizadas.  
  
## <a name="description"></a>Descripción  

 Este contador se incrementa cuando el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> devuelve `false`. Indica que el mensaje entrante es de un usuario válido y que está debidamente protegido, pero dicho usuario no está autorizado a realizar tareas específicas.
