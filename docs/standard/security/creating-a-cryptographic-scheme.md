---
title: Crear un esquema criptográfico
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51d07fadcf359c2b44f22ca9868d0f12e24b80c5
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873129"
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="49276-102">Crear un esquema criptográfico</span><span class="sxs-lookup"><span data-stu-id="49276-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="49276-103">Los componentes criptográficos de .NET Framework se pueden combinar para crear distintos esquemas para cifrar y descifrar datos.</span><span class="sxs-lookup"><span data-stu-id="49276-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="49276-104">Un esquema criptográfico simple para cifrar y descifrar datos podría especificar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="49276-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1.  <span data-ttu-id="49276-105">Cada parte genera un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="49276-105">Each party generates a public/private key pair.</span></span>  
  
2.  <span data-ttu-id="49276-106">Las partes intercambian sus claves públicas.</span><span class="sxs-lookup"><span data-stu-id="49276-106">The parties exchange their public keys.</span></span>  
  
3.  <span data-ttu-id="49276-107">Cada parte genera una clave secreta para el cifrado TripleDES, por ejemplo, y cifra la clave recién creada con la clave pública de la otra parte.</span><span class="sxs-lookup"><span data-stu-id="49276-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4.  <span data-ttu-id="49276-108">Una parte envía los datos a la otra y combina la clave secreta de la otra con la suya propia en un determinado orden para crear una nueva clave secreta.</span><span class="sxs-lookup"><span data-stu-id="49276-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5.  <span data-ttu-id="49276-109">Después, las partes inician una conversación mediante el cifrado simétrico.</span><span class="sxs-lookup"><span data-stu-id="49276-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="49276-110">Crear un esquema criptográfico no es una tarea trivial.</span><span class="sxs-lookup"><span data-stu-id="49276-110">Creating a cryptographic scheme is not a trivial task.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="49276-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="49276-111">See also</span></span>

- [<span data-ttu-id="49276-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="49276-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
