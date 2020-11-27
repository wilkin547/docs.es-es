---
title: Errores de autenticación y validación de la seguridad
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
ms.openlocfilehash: 3bcc6111f322a3bd8169567e8f436871eb19f879
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253055"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="668e7-102">Errores de autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="668e7-102">Security Validation and Authentication Failures</span></span>

<span data-ttu-id="668e7-103">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="668e7-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="668e7-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="668e7-104">Description</span></span>  

 <span data-ttu-id="668e7-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="668e7-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="668e7-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="668e7-106">Such problems include:</span></span>  
  
- <span data-ttu-id="668e7-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="668e7-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="668e7-108">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="668e7-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="668e7-109">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="668e7-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="668e7-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="668e7-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="668e7-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="668e7-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="668e7-112">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="668e7-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="668e7-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="668e7-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
