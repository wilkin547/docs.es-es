---
description: 'Más información acerca de: punto de conexión: errores de autenticación y validación de seguridad'
title: 'punto de conexión: Errores en la autenticación y validación de la seguridad'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
ms.openlocfilehash: 9131eebcf85032c591ebf7f65e2b0e5f67ec60df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655427"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a>punto de conexión: Errores en la autenticación y validación de la seguridad

Nombre del contador: errores en la autenticación y validación de la seguridad  
  
## <a name="description"></a>Descripción  

 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas". Entre estos problemas se incluyen:  
  
- No se puede leer el token de cliente en el mensaje.  
  
- Error al autenticar el token del cliente (contraseña errónea).  
  
- Error en la comprobación de la firma (mensaje manipulado).  
  
- El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.  
  
- Error de descifrado.  
  
- Faltan algunos elementos necesarios (marca de tiempo o bloque de datos cifrados) en el mensaje.  
  
- Errores durante el protocolo de enlace TLSNEGO/SPNEGO.
