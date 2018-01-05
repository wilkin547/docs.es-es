---
title: "Crear un esquema criptográfico"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b0aabdc9150aea73ad9078b0e9ee92b2abd03e17
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="71d6e-102">Crear un esquema criptográfico</span><span class="sxs-lookup"><span data-stu-id="71d6e-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="71d6e-103">Los componentes criptográficos de .NET Framework se pueden combinar para crear distintos esquemas para cifrar y descifrar datos.</span><span class="sxs-lookup"><span data-stu-id="71d6e-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="71d6e-104">Un esquema criptográfico simple para cifrar y descifrar datos podría especificar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="71d6e-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1.  <span data-ttu-id="71d6e-105">Cada parte genera un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="71d6e-105">Each party generates a public/private key pair.</span></span>  
  
2.  <span data-ttu-id="71d6e-106">Las partes intercambian sus claves públicas.</span><span class="sxs-lookup"><span data-stu-id="71d6e-106">The parties exchange their public keys.</span></span>  
  
3.  <span data-ttu-id="71d6e-107">Cada parte genera una clave secreta para el cifrado TripleDES, por ejemplo, y cifra la clave recién creada con la clave pública de la otra parte.</span><span class="sxs-lookup"><span data-stu-id="71d6e-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4.  <span data-ttu-id="71d6e-108">Una parte envía los datos a la otra y combina la clave secreta de la otra con la suya propia en un determinado orden para crear una nueva clave secreta.</span><span class="sxs-lookup"><span data-stu-id="71d6e-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5.  <span data-ttu-id="71d6e-109">Después, las partes inician una conversación mediante el cifrado simétrico.</span><span class="sxs-lookup"><span data-stu-id="71d6e-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="71d6e-110">Crear un esquema criptográfico no es una tarea trivial.</span><span class="sxs-lookup"><span data-stu-id="71d6e-110">Creating a cryptographic scheme is not a trivial task.</span></span> <span data-ttu-id="71d6e-111">Para obtener más información sobre el uso de la criptografía, consulte el tema Criptografía en la documentación de Platform SDK en http://msdn.microsoft.com/library.</span><span class="sxs-lookup"><span data-stu-id="71d6e-111">For more information on using cryptography, see the Cryptography topic in the Platform SDK documentation at http://msdn.microsoft.com/library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d6e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="71d6e-112">See Also</span></span>  
 [<span data-ttu-id="71d6e-113">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="71d6e-113">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
