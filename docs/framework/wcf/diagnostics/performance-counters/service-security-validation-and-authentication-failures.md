---
description: 'Más información acerca de: servicio: errores de autenticación y validación de seguridad'
title: 'Servicio: errores en la validación de la seguridad y la autenticación'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: 8938c74e706526a02bf2ea5885951d067d6ebae9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759489"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="49691-103">Servicio: errores en la validación de la seguridad y la autenticación</span><span class="sxs-lookup"><span data-stu-id="49691-103">Service: Security Validation and Authentication Failures</span></span>

<span data-ttu-id="49691-104">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="49691-104">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="49691-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="49691-105">Description</span></span>  

 <span data-ttu-id="49691-106">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="49691-106">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="49691-107">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="49691-107">Such problems include:</span></span>  
  
- <span data-ttu-id="49691-108">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="49691-108">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="49691-109">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="49691-109">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="49691-110">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="49691-110">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="49691-111">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="49691-111">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="49691-112">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="49691-112">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="49691-113">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="49691-113">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="49691-114">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="49691-114">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
