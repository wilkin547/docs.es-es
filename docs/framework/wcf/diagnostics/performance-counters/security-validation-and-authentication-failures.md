---
title: Errores de autenticación y validación de la seguridad
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5d7964c59f28f33d6ec7bc3ba605b84e6a201b14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474264"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="c7ec4-102">Errores de autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="c7ec4-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="c7ec4-103">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="c7ec4-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="c7ec4-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7ec4-104">Description</span></span>  
 <span data-ttu-id="c7ec4-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="c7ec4-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="c7ec4-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="c7ec4-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="c7ec4-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c7ec4-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="c7ec4-108">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="c7ec4-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="c7ec4-109">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="c7ec4-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="c7ec4-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="c7ec4-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="c7ec4-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="c7ec4-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="c7ec4-112">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c7ec4-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="c7ec4-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="c7ec4-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
