---
title: 'Servicio: Errores de autenticación y validación de la seguridad'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: ba8da3ae6be6bd089690359f19e153da1e0b54fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998314"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="ce742-102">Servicio: Errores de autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="ce742-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="ce742-103">Nombre del contador: Errores de autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="ce742-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="ce742-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce742-104">Description</span></span>  
 <span data-ttu-id="ce742-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="ce742-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="ce742-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ce742-106">Such problems include:</span></span>  
  
- <span data-ttu-id="ce742-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ce742-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="ce742-108">Error de autenticación en el token de cliente (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="ce742-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
- <span data-ttu-id="ce742-109">Error de comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="ce742-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
- <span data-ttu-id="ce742-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="ce742-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="ce742-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="ce742-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="ce742-112">Faltan algunos elementos obligatorios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ce742-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="ce742-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="ce742-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
