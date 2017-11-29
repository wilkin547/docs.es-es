---
title: "punto de conexión: errores por segundo en la validación de seguridad y en la autenticación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c6b50aa00fe59d0ad23d5ca0b77c7b89f97a0d1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a>punto de conexión: errores por segundo en la validación de seguridad y en la autenticación
Nombre del contador: validación de la seguridad y errores de autenticación por segundo  
  
## <a name="description"></a>Descripción  
 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas". Entre estos problemas se incluyen:  
  
-   No se puede leer el token de cliente en el mensaje.  
  
-   El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).  
  
-   Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).  
  
-   El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.  
  
-   Error de descifrado.  
  
-   Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.  
  
-   Errores durante el protocolo de enlace TLSNEGO/SPNEGO.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula:  
  
 (N1-N0)/((D1-D0)/F)
