---
title: "Errores de autenticación y validación de la seguridad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c1d448d709c7ad20e9d08a291f5a38546cd93ce4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="64f0d-102">Errores de autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="64f0d-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="64f0d-103">Nombre del contador: errores en la autenticación y validación de la seguridad</span><span class="sxs-lookup"><span data-stu-id="64f0d-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="64f0d-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="64f0d-104">Description</span></span>  
 <span data-ttu-id="64f0d-105">Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="64f0d-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="64f0d-106">Entre estos problemas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="64f0d-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="64f0d-107">No se puede leer el token de cliente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="64f0d-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="64f0d-108">El token del cliente ha producido un error en la autenticación (por ejemplo, contraseña incorrecta).</span><span class="sxs-lookup"><span data-stu-id="64f0d-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="64f0d-109">Error en la comprobación de la firma (por ejemplo, el mensaje ha sido alterado).</span><span class="sxs-lookup"><span data-stu-id="64f0d-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="64f0d-110">El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="64f0d-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="64f0d-111">Error de descifrado.</span><span class="sxs-lookup"><span data-stu-id="64f0d-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="64f0d-112">Faltan algunos elementos necesarios (por ejemplo, la marca de tiempo o el bloque de datos cifrados) en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="64f0d-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="64f0d-113">Errores durante el protocolo de enlace TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="64f0d-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
