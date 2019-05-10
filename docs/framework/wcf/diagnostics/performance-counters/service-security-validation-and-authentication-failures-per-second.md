---
title: 'Servicio: Errores de autenticación y validación de la seguridad por segundo'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
ms.openlocfilehash: 2caebed85a28004ef038beee7d07c05a23da53c0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613677"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="6acfa-102">Servicio: Errores de autenticación y validación de la seguridad por segundo</span><span class="sxs-lookup"><span data-stu-id="6acfa-102">Service: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="6acfa-103">Nombre del contador: Validación de seguridad y errores de autenticación por segundo.</span><span class="sxs-lookup"><span data-stu-id="6acfa-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6acfa-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="6acfa-104">Description</span></span>  
 <span data-ttu-id="6acfa-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="6acfa-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="6acfa-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="6acfa-106">Such problems include:</span></span>  
  
- <span data-ttu-id="6acfa-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6acfa-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="6acfa-108">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="6acfa-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="6acfa-109">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="6acfa-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="6acfa-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="6acfa-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="6acfa-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="6acfa-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="6acfa-112">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6acfa-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="6acfa-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="6acfa-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="6acfa-114">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la fórmula siguiente,</span><span class="sxs-lookup"><span data-stu-id="6acfa-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula,</span></span>  
  
 <span data-ttu-id="6acfa-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="6acfa-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
