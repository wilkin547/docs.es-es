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
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="e6808-103">punto de conexión: Errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="e6808-103">Endpoint: Security Validation and Authentication Failures</span></span>

<span data-ttu-id="e6808-104">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="e6808-104">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="e6808-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6808-105">Description</span></span>  

 <span data-ttu-id="e6808-106">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="e6808-106">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="e6808-107">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="e6808-107">Such problems include:</span></span>  
  
- <span data-ttu-id="e6808-108">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e6808-108">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="e6808-109">Error al autenticar el token del cliente (contraseña errónea).</span><span class="sxs-lookup"><span data-stu-id="e6808-109">Client token has failed authentication (bad password).</span></span>  
  
- <span data-ttu-id="e6808-110">Error en la comprobación de la firma (mensaje manipulado).</span><span class="sxs-lookup"><span data-stu-id="e6808-110">Signature verification has failed (the message has been tampered).</span></span>  
  
- <span data-ttu-id="e6808-111">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="e6808-111">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="e6808-112">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="e6808-112">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="e6808-113">Faltan algunos elementos necesarios (marca de tiempo o bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e6808-113">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="e6808-114">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="e6808-114">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
