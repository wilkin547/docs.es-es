---
title: "punto de conexión: errores por segundo en la validación de seguridad y en la autenticación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f457a3067a4ada3ea226bf289c9c559ef5e35594
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="faeb7-102">punto de conexión: errores por segundo en la validación de seguridad y en la autenticación</span><span class="sxs-lookup"><span data-stu-id="faeb7-102">Endpoint: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="faeb7-103">Nombre del contador: validación de la seguridad y errores de autenticación por segundo</span><span class="sxs-lookup"><span data-stu-id="faeb7-103">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="faeb7-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="faeb7-104">Description</span></span>  
 <span data-ttu-id="faeb7-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="faeb7-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="faeb7-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="faeb7-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="faeb7-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="faeb7-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="faeb7-108">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="faeb7-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="faeb7-109">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="faeb7-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="faeb7-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="faeb7-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="faeb7-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="faeb7-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="faeb7-112">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="faeb7-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="faeb7-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="faeb7-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="faeb7-114">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula con la siguiente fórmula:</span><span class="sxs-lookup"><span data-stu-id="faeb7-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="faeb7-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="faeb7-115">(N1-N0)/((D1-D0)/F)</span></span>
