---
description: 'Más información sobre: errores de autenticación y validación de seguridad'
title: Errores de autenticación y validación de la seguridad
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
ms.openlocfilehash: 1de74a277c3b63d304be35baac9117ec613e3c7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803391"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="abe10-103">Errores de autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="abe10-103">Security Validation and Authentication Failures</span></span>

<span data-ttu-id="abe10-104">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="abe10-104">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="abe10-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="abe10-105">Description</span></span>  

 <span data-ttu-id="abe10-106">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="abe10-106">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="abe10-107">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="abe10-107">Such problems include:</span></span>  
  
- <span data-ttu-id="abe10-108">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="abe10-108">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="abe10-109">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="abe10-109">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="abe10-110">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="abe10-110">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="abe10-111">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="abe10-111">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="abe10-112">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="abe10-112">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="abe10-113">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="abe10-113">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="abe10-114">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="abe10-114">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
