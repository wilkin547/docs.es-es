---
title: 'punto de conexión: Errores en la autenticación y validación de la seguridad'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
ms.openlocfilehash: a9a4758b26c744c55af200aee22a7e90c5a5cf57
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256474"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="20446-102">punto de conexión: Errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="20446-102">Endpoint: Security Validation and Authentication Failures</span></span>

<span data-ttu-id="20446-103">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="20446-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="20446-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="20446-104">Description</span></span>  

 <span data-ttu-id="20446-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="20446-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="20446-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="20446-106">Such problems include:</span></span>  
  
- <span data-ttu-id="20446-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="20446-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="20446-108">Error al autenticar el token del cliente (contraseña errónea).</span><span class="sxs-lookup"><span data-stu-id="20446-108">Client token has failed authentication (bad password).</span></span>  
  
- <span data-ttu-id="20446-109">Error en la comprobación de la firma (mensaje manipulado).</span><span class="sxs-lookup"><span data-stu-id="20446-109">Signature verification has failed (the message has been tampered).</span></span>  
  
- <span data-ttu-id="20446-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="20446-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="20446-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="20446-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="20446-112">Faltan algunos elementos necesarios (marca de tiempo o bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="20446-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="20446-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="20446-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
