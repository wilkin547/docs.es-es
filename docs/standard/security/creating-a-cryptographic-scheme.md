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
ms.openlocfilehash: 2db6d4229ac777801aff792c86fe0e5e9a1b4994
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197898"
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="2957a-102">Crear un esquema criptográfico</span><span class="sxs-lookup"><span data-stu-id="2957a-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="2957a-103">Los componentes criptográficos de .NET Framework se pueden combinar para crear distintos esquemas para cifrar y descifrar datos.</span><span class="sxs-lookup"><span data-stu-id="2957a-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="2957a-104">Un esquema criptográfico simple para cifrar y descifrar datos podría especificar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="2957a-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1.  <span data-ttu-id="2957a-105">Cada parte genera un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="2957a-105">Each party generates a public/private key pair.</span></span>  
  
2.  <span data-ttu-id="2957a-106">Las partes intercambian sus claves públicas.</span><span class="sxs-lookup"><span data-stu-id="2957a-106">The parties exchange their public keys.</span></span>  
  
3.  <span data-ttu-id="2957a-107">Cada parte genera una clave secreta para el cifrado TripleDES, por ejemplo, y cifra la clave recién creada con la clave pública de la otra parte.</span><span class="sxs-lookup"><span data-stu-id="2957a-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4.  <span data-ttu-id="2957a-108">Una parte envía los datos a la otra y combina la clave secreta de la otra con la suya propia en un determinado orden para crear una nueva clave secreta.</span><span class="sxs-lookup"><span data-stu-id="2957a-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5.  <span data-ttu-id="2957a-109">Después, las partes inician una conversación mediante el cifrado simétrico.</span><span class="sxs-lookup"><span data-stu-id="2957a-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="2957a-110">Crear un esquema criptográfico no es una tarea trivial.</span><span class="sxs-lookup"><span data-stu-id="2957a-110">Creating a cryptographic scheme is not a trivial task.</span></span> <span data-ttu-id="2957a-111">Para obtener más información sobre el uso de criptografía, vea el tema criptografía en la documentación de Platform SDK en http://msdn.microsoft.com/library.</span><span class="sxs-lookup"><span data-stu-id="2957a-111">For more information on using cryptography, see the Cryptography topic in the Platform SDK documentation at http://msdn.microsoft.com/library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2957a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2957a-112">See also</span></span>

- [<span data-ttu-id="2957a-113">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="2957a-113">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
