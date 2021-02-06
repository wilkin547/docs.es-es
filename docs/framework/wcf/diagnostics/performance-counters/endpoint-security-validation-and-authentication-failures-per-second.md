---
description: 'Más información acerca de: punto de conexión: errores de autenticación y validación de seguridad por segundo'
title: 'punto de conexión: errores por segundo en la validación de seguridad y en la autenticación'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: aa5ccc4049dc81a7c2d545cfc70e9078ac72d87a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655440"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a>punto de conexión: errores por segundo en la validación de seguridad y en la autenticación

Nombre del contador: validación de la seguridad y errores de autenticación por segundo  
  
## <a name="description"></a>Descripción  

 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas". Entre estos problemas se incluyen:  
  
- No se puede leer el token de cliente en el mensaje.  
  
- El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).  
  
- Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).  
  
- El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.  
  
- Error de descifrado.  
  
- Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.  
  
- Errores durante el protocolo de enlace TLSNEGO/SPNEGO.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula:  
  
 (N1-N0)/((D1-D0)/F)
