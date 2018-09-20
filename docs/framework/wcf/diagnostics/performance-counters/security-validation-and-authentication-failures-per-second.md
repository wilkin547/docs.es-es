---
title: Errores de autenticación y validación de la seguridad por segundo
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4836a5076401de2f7c3112b298cdadc0e0307962
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2018
ms.locfileid: "45641064"
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="ec18e-102">Errores de autenticación y validación de la seguridad por segundo</span><span class="sxs-lookup"><span data-stu-id="ec18e-102">Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="ec18e-103">Nombre del contador: Errores de validación de seguridad y de autenticación por segundo</span><span class="sxs-lookup"><span data-stu-id="ec18e-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ec18e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec18e-104">Description</span></span>  
 <span data-ttu-id="ec18e-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="ec18e-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="ec18e-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ec18e-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="ec18e-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec18e-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="ec18e-108">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="ec18e-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="ec18e-109">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="ec18e-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="ec18e-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="ec18e-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="ec18e-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="ec18e-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="ec18e-112">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec18e-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="ec18e-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="ec18e-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="ec18e-114">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la fórmula siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec18e-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="ec18e-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="ec18e-115">(N1-N0)/((D1-D0)/F)</span></span>
