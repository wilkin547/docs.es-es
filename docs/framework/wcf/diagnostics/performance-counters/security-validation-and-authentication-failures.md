---
title: Errores de autenticación y validación de la seguridad
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
ms.openlocfilehash: 0f061e1e12321dbe8034d7619830f71717ca9d1f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664976"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="ec380-102">Errores de autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="ec380-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="ec380-103">Nombre del contador: Errores de autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="ec380-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="ec380-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec380-104">Description</span></span>  
 <span data-ttu-id="ec380-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="ec380-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="ec380-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ec380-106">Such problems include:</span></span>  
  
- <span data-ttu-id="ec380-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec380-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="ec380-108">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="ec380-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="ec380-109">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="ec380-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="ec380-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="ec380-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="ec380-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="ec380-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="ec380-112">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec380-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="ec380-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="ec380-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
