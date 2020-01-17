---
title: 'punto de conexión: errores por segundo en la validación de seguridad y en la autenticación'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: fb882c7cbfd86e1949798df9c0b7514182c1b8f6
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163532"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="12eef-102">punto de conexión: errores por segundo en la validación de seguridad y en la autenticación</span><span class="sxs-lookup"><span data-stu-id="12eef-102">Endpoint: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="12eef-103">Nombre del contador: validación de la seguridad y errores de autenticación por segundo</span><span class="sxs-lookup"><span data-stu-id="12eef-103">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="12eef-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="12eef-104">Description</span></span>  
 <span data-ttu-id="12eef-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="12eef-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="12eef-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="12eef-106">Such problems include:</span></span>  
  
- <span data-ttu-id="12eef-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="12eef-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="12eef-108">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="12eef-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="12eef-109">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="12eef-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="12eef-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="12eef-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="12eef-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="12eef-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="12eef-112">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="12eef-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="12eef-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="12eef-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="12eef-114">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cuyo valor se calcula mediante la siguiente fórmula:</span><span class="sxs-lookup"><span data-stu-id="12eef-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="12eef-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="12eef-115">(N1-N0)/((D1-D0)/F)</span></span>
