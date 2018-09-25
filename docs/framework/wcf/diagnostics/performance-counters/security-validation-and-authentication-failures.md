---
title: Errores de autenticación y validación de la seguridad
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
author: BrucePerlerMS
ms.openlocfilehash: d13e94800d71c6f567c6aab61974e42b1a3f1706
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070947"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="8ae26-102">Errores de autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="8ae26-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="8ae26-103">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="8ae26-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="8ae26-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ae26-104">Description</span></span>  
 <span data-ttu-id="8ae26-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="8ae26-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="8ae26-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="8ae26-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="8ae26-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8ae26-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="8ae26-108">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="8ae26-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="8ae26-109">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="8ae26-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="8ae26-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="8ae26-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="8ae26-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="8ae26-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="8ae26-112">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8ae26-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="8ae26-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="8ae26-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
