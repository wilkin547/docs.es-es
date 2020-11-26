---
title: 'Servicio: errores en la validación de la seguridad y la autenticación'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: d89419d7d579d29a1c57370d61eefb8b26333a40
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236863"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="49a7a-102">Servicio: errores en la validación de la seguridad y la autenticación</span><span class="sxs-lookup"><span data-stu-id="49a7a-102">Service: Security Validation and Authentication Failures</span></span>

<span data-ttu-id="49a7a-103">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="49a7a-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="49a7a-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="49a7a-104">Description</span></span>  

 <span data-ttu-id="49a7a-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="49a7a-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="49a7a-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="49a7a-106">Such problems include:</span></span>  
  
- <span data-ttu-id="49a7a-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="49a7a-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="49a7a-108">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="49a7a-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="49a7a-109">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="49a7a-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="49a7a-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="49a7a-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="49a7a-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="49a7a-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="49a7a-112">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="49a7a-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="49a7a-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="49a7a-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
