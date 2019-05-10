---
title: 'Punto de conexión: Errores de autenticación y validación de la seguridad por segundo'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: a6d76a0d11c52d20aebd44a85862c802cc0a68f7
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912480"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a>Punto de conexión: Errores de autenticación y validación de la seguridad por segundo
Nombre del contador: Errores de autenticación y validación de la seguridad por segundo  
  
## <a name="description"></a>Descripción  
 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas". Entre estos problemas se incluyen:  
  
- No se puede leer el token de cliente en el mensaje.  
  
- El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).  
  
- Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).  
  
- El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.  
  
- Error de descifrado.  
  
- Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.  
  
- Errores durante el protocolo de enlace TLSNEGO/SPNEGO.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la fórmula siguiente:  
  
 (N1-N0)/((D1-D0)/F)
