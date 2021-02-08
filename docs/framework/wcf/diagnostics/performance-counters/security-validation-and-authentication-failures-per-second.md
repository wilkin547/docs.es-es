---
description: 'Más información sobre: errores de autenticación y validación de la seguridad por segundo'
title: Errores de autenticación y validación de la seguridad por segundo
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: 77c11e8f47b5d91ea38030841f6ca33ba0f0795c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803404"
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="5d665-103">Errores de autenticación y validación de la seguridad por segundo</span><span class="sxs-lookup"><span data-stu-id="5d665-103">Security Validation and Authentication Failures Per Second</span></span>

<span data-ttu-id="5d665-104">Nombre del contador: Errores de validación de seguridad y de autenticación por segundo</span><span class="sxs-lookup"><span data-stu-id="5d665-104">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5d665-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d665-105">Description</span></span>  

 <span data-ttu-id="5d665-106">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="5d665-106">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="5d665-107">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="5d665-107">Such problems include:</span></span>  
  
- <span data-ttu-id="5d665-108">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="5d665-108">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="5d665-109">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="5d665-109">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="5d665-110">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="5d665-110">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="5d665-111">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="5d665-111">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="5d665-112">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="5d665-112">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="5d665-113">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="5d665-113">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="5d665-114">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="5d665-114">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="5d665-115">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula:</span><span class="sxs-lookup"><span data-stu-id="5d665-115">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="5d665-116">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="5d665-116">(N1-N0)/((D1-D0)/F)</span></span>
