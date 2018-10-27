---
title: 'Servicio: Errores por segundo en la validación de seguridad y en la autenticación'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
ms.openlocfilehash: 97752fbd4ff38c40917c132fddfe3798a7ee6766
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183638"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a>Servicio: Errores por segundo en la validación de seguridad y en la autenticación
Nombre del contador: Errores de validación de seguridad y de autenticación por segundo  
  
## <a name="description"></a>Descripción  
 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas". Entre estos problemas se incluyen:  
  
-   No se puede leer el token de cliente en el mensaje.  
  
-   El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).  
  
-   Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).  
  
-   El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.  
  
-   Error de descifrado.  
  
-   Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.  
  
-   Errores durante el protocolo de enlace TLSNEGO/SPNEGO.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la fórmula siguiente,  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
