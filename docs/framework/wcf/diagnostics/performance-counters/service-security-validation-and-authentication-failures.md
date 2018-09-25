---
title: 'Servicio: errores en la validación de la seguridad y la autenticación'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
author: BrucePerlerMS
ms.openlocfilehash: 4c74cb1962bbc0f03ac33d8fcc7b10052bec8273
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47077297"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="a0c06-102">Servicio: errores en la validación de la seguridad y la autenticación</span><span class="sxs-lookup"><span data-stu-id="a0c06-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="a0c06-103">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="a0c06-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="a0c06-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0c06-104">Description</span></span>  
 <span data-ttu-id="a0c06-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="a0c06-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="a0c06-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="a0c06-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="a0c06-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0c06-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="a0c06-108">Error de autenticación en el token de cliente (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="a0c06-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
-   <span data-ttu-id="a0c06-109">Error de comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="a0c06-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="a0c06-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="a0c06-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="a0c06-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="a0c06-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="a0c06-112">Faltan algunos elementos obligatorios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0c06-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="a0c06-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="a0c06-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
