---
title: 'Servicio: errores en la validación de la seguridad y la autenticación'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e160b014b7aa7586566073b800084d44be15ccaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474407"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="0dfa8-102">Servicio: errores en la validación de la seguridad y la autenticación</span><span class="sxs-lookup"><span data-stu-id="0dfa8-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="0dfa8-103">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="0dfa8-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="0dfa8-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="0dfa8-104">Description</span></span>  
 <span data-ttu-id="0dfa8-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="0dfa8-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="0dfa8-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="0dfa8-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="0dfa8-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0dfa8-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="0dfa8-108">Error de autenticación en el token de cliente (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="0dfa8-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
-   <span data-ttu-id="0dfa8-109">Error de comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="0dfa8-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="0dfa8-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="0dfa8-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="0dfa8-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="0dfa8-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="0dfa8-112">Faltan algunos elementos obligatorios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0dfa8-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="0dfa8-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="0dfa8-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
