---
title: Errores de autenticación y validación de la seguridad por segundo
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: e3db8cb20399bdff9b73a428ea2a53909da4eee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915777"
---
# <a name="security-validation-and-authentication-failures-per-second"></a>Errores de autenticación y validación de la seguridad por segundo
Nombre del contador: Validación de seguridad y errores de autenticación por segundo.  
  
## <a name="description"></a>Descripción  
 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas". Entre estos problemas se incluyen:  
  
-   No se puede leer el token de cliente en el mensaje.  
  
-   El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).  
  
-   Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).  
  
-   El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.  
  
-   Error de descifrado.  
  
-   Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.  
  
-   Errores durante el protocolo de enlace TLSNEGO/SPNEGO.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la fórmula siguiente:  
  
 (N1-N0)/((D1-D0)/F)
