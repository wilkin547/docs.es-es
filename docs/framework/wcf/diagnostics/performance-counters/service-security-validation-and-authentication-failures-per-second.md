---
description: 'Más información acerca de: servicio: errores de autenticación y validación de seguridad por segundo'
title: 'Servicio: Errores por segundo en la validación de seguridad y en la autenticación'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
ms.openlocfilehash: 8c0baedab3335031ed1737e0e4cecff7febc2944
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759528"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="274ea-103">Servicio: Errores por segundo en la validación de seguridad y en la autenticación</span><span class="sxs-lookup"><span data-stu-id="274ea-103">Service: Security Validation and Authentication Failures Per Second</span></span>

<span data-ttu-id="274ea-104">Nombre del contador: Errores de validación de seguridad y de autenticación por segundo</span><span class="sxs-lookup"><span data-stu-id="274ea-104">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="274ea-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="274ea-105">Description</span></span>  

 <span data-ttu-id="274ea-106">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="274ea-106">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="274ea-107">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="274ea-107">Such problems include:</span></span>  
  
- <span data-ttu-id="274ea-108">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="274ea-108">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="274ea-109">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="274ea-109">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="274ea-110">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="274ea-110">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="274ea-111">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="274ea-111">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="274ea-112">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="274ea-112">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="274ea-113">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="274ea-113">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="274ea-114">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="274ea-114">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="274ea-115">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula:</span><span class="sxs-lookup"><span data-stu-id="274ea-115">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula,</span></span>  
  
 <span data-ttu-id="274ea-116">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="274ea-116">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
