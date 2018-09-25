---
title: 'punto de conexión: Errores en la autenticación y validación de la seguridad'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
author: BrucePerlerMS
ms.openlocfilehash: f7cd2268eefa0176ab71a3d5d3bc82c178664742
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075101"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="ae477-102">punto de conexión: Errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="ae477-102">Endpoint: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="ae477-103">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="ae477-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="ae477-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae477-104">Description</span></span>  
 <span data-ttu-id="ae477-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="ae477-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="ae477-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ae477-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="ae477-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ae477-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="ae477-108">Error al autenticar el token del cliente (contraseña errónea).</span><span class="sxs-lookup"><span data-stu-id="ae477-108">Client token has failed authentication (bad password).</span></span>  
  
-   <span data-ttu-id="ae477-109">Error en la comprobación de la firma (mensaje manipulado).</span><span class="sxs-lookup"><span data-stu-id="ae477-109">Signature verification has failed (the message has been tampered).</span></span>  
  
-   <span data-ttu-id="ae477-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="ae477-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="ae477-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="ae477-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="ae477-112">Faltan algunos elementos necesarios (marca de tiempo o bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ae477-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="ae477-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="ae477-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
