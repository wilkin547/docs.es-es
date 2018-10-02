---
title: 'punto de conexión: Errores en la autenticación y validación de la seguridad'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
author: BrucePerlerMS
ms.openlocfilehash: f7cd2268eefa0176ab71a3d5d3bc82c178664742
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862807"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a>punto de conexión: Errores en la autenticación y validación de la seguridad
Nombre del contador: errores en la autenticación y validación de la seguridad  
  
## <a name="description"></a>Descripción  
 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas". Entre estos problemas se incluyen:  
  
-   No se puede leer el token de cliente en el mensaje.  
  
-   Error al autenticar el token del cliente (contraseña errónea).  
  
-   Error en la comprobación de la firma (mensaje manipulado).  
  
-   El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.  
  
-   Error de descifrado.  
  
-   Faltan algunos elementos necesarios (marca de tiempo o bloque de datos cifrados) en el mensaje.  
  
-   Errores durante el protocolo de enlace TLSNEGO/SPNEGO.
