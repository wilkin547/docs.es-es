---
title: Generar claves para cifrado y descifrado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET Framework], keys
- symmetric keys
- asymmetric keys [.NET Framework]
- cryptography [.NET Framework], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0b40e09a9a2c534d3376fa6930d8166591873a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="a4823-102">Generar claves para cifrado y descifrado</span><span class="sxs-lookup"><span data-stu-id="a4823-102">Generating Keys for Encryption and Decryption</span></span>
<span data-ttu-id="a4823-103">La creación y administración de claves es una parte importante del proceso criptográfico.</span><span class="sxs-lookup"><span data-stu-id="a4823-103">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="a4823-104">Los algoritmos simétricos requieren la creación de una clave y un IV (Initialization Vector, vector de inicialización).</span><span class="sxs-lookup"><span data-stu-id="a4823-104">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="a4823-105">La clave debe mantenerse en secreto y a salvo de quienes no deban descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="a4823-105">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="a4823-106">No es necesario que el vector de inicialización sea secreto, pero debe cambiarse para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="a4823-106">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="a4823-107">Los algoritmos asimétricos requieren la creación de una clave pública y una clave privada.</span><span class="sxs-lookup"><span data-stu-id="a4823-107">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="a4823-108">La clave pública puede revelarse a cualquiera, mientras que la privada debe conocerla sólo la parte que descifrará los datos cifrados con la clave pública.</span><span class="sxs-lookup"><span data-stu-id="a4823-108">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="a4823-109">En esta sección se describe cómo generar y administrar claves para algoritmos simétricos y asimétricos.</span><span class="sxs-lookup"><span data-stu-id="a4823-109">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="a4823-110">Claves simétricas</span><span class="sxs-lookup"><span data-stu-id="a4823-110">Symmetric Keys</span></span>  
 <span data-ttu-id="a4823-111">Las clases de cifrado simétrico que proporciona .NET Framework requieren una clave y un nuevo vector de inicialización (IV) para cifrar y descifrar datos.</span><span class="sxs-lookup"><span data-stu-id="a4823-111">The symmetric encryption classes supplied by the .NET Framework require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="a4823-112">Siempre que cree una nueva instancia de una de las clases criptográficas simétricas administradas utilizando el constructor predeterminado, se crean automáticamente una clave y un vector de inicialización nuevos.</span><span class="sxs-lookup"><span data-stu-id="a4823-112">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the default constructor, a new key and IV are automatically created.</span></span> <span data-ttu-id="a4823-113">Cualquier persona a la que permita descifrar sus datos debe poseer la misma clave y el mismo IV, y utilizar el mismo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="a4823-113">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="a4823-114">Normalmente, debe crearse una nueva clave y vector de inicialización para cada sesión, y ni la clave ni el vector deberían almacenarse para utilizarlos en una sesión posterior.</span><span class="sxs-lookup"><span data-stu-id="a4823-114">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="a4823-115">Para comunicar una clave simétrica y un IV a una parte remota, la clave simétrica normalmente se cifra usando cifrado asimétrico.</span><span class="sxs-lookup"><span data-stu-id="a4823-115">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="a4823-116">El envío de la clave a través de una red insegura sin cifrarla resulta peligroso, ya que quien intercepte la clave y el IV podrá descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="a4823-116">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span> <span data-ttu-id="a4823-117">Para obtener más información sobre el intercambio de datos mediante el cifrado, vea [Crear un esquema criptográfico](../../../docs/standard/security/creating-a-cryptographic-scheme.md).</span><span class="sxs-lookup"><span data-stu-id="a4823-117">For more information about exchanging data by using encryption, see [Creating a Cryptographic Scheme](../../../docs/standard/security/creating-a-cryptographic-scheme.md).</span></span>  
  
 <span data-ttu-id="a4823-118">En el ejemplo siguiente se muestra la creación de una nueva instancia de la clase <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> que implementa el algoritmo TripleDES.</span><span class="sxs-lookup"><span data-stu-id="a4823-118">The following example shows the creation of a new instance of the <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> class that implements the TripleDES algorithm.</span></span>  
  
```vb  
Dim TDES As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
```  
  
```csharp  
TripleDESCryptoServiceProvider TDES = new TripleDESCryptoServiceProvider();  
```  
  
 <span data-ttu-id="a4823-119">Cuando se ejecuta el código anterior, se genera una nueva clave y un IV, y se colocan en las propiedades **Key** e **IV** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a4823-119">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="a4823-120">En ocasiones tendrá que generar varias claves.</span><span class="sxs-lookup"><span data-stu-id="a4823-120">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="a4823-121">En este caso, puede crear una nueva instancia de una clase que implemente un algoritmo simétrico y después crear una nueva clave e IV mediante una llamada a los métodos **GenerateKey** y **GenerateIV** .</span><span class="sxs-lookup"><span data-stu-id="a4823-121">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="a4823-122">En el ejemplo de código siguiente se ilustra cómo crear nuevas claves y vectores de inicialización una vez creada una nueva instancia de la clase criptográfica asimétrica.</span><span class="sxs-lookup"><span data-stu-id="a4823-122">The following code example illustrates how to create new keys and IVs after a new instance of the asymmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim TDES As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
TDES.GenerateIV()  
TDES.GenerateKey()  
```  
  
```csharp  
TripleDESCryptoServiceProvider TDES = new TripleDESCryptoServiceProvider();  
TDES.GenerateIV();  
TDES.GenerateKey();  
```  
  
 <span data-ttu-id="a4823-123">Cuando se ejecuta el código anterior, se generan una clave y un IV al crear la nueva instancia de **TripleDESCryptoServiceProvider** .</span><span class="sxs-lookup"><span data-stu-id="a4823-123">When the previous code is executed, a key and IV are generated when the new instance of **TripleDESCryptoServiceProvider** is made.</span></span> <span data-ttu-id="a4823-124">Se crean otra clave e IV cuando se llama a los métodos **GenerateKey** y **GenerateIV** .</span><span class="sxs-lookup"><span data-stu-id="a4823-124">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>  
  
## <a name="asymmetric-keys"></a><span data-ttu-id="a4823-125">Claves asimétricas</span><span class="sxs-lookup"><span data-stu-id="a4823-125">Asymmetric Keys</span></span>  
 <span data-ttu-id="a4823-126">.NET Framework proporciona las clases <xref:System.Security.Cryptography.RSACryptoServiceProvider> y <xref:System.Security.Cryptography.DSACryptoServiceProvider> para el cifrado asimétrico.</span><span class="sxs-lookup"><span data-stu-id="a4823-126">The .NET Framework provides the <xref:System.Security.Cryptography.RSACryptoServiceProvider> and <xref:System.Security.Cryptography.DSACryptoServiceProvider> classes for asymmetric encryption.</span></span> <span data-ttu-id="a4823-127">Estas clases crean un par de claves pública y privada cuando utiliza el constructor predeterminado para crear una nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="a4823-127">These classes create a public/private key pair when you use the default constructor to create a new instance.</span></span> <span data-ttu-id="a4823-128">Las claves asimétricas pueden almacenarse para utilizarse en sesiones múltiples o bien generarse para una sesión únicamente.</span><span class="sxs-lookup"><span data-stu-id="a4823-128">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="a4823-129">Aunque la clave pública puede ponerse a disposición general, la clave privada debe guardarse bien.</span><span class="sxs-lookup"><span data-stu-id="a4823-129">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="a4823-130">Un par de claves pública y privada se genera siempre que se crea una nueva instancia de una clase de algoritmo asimétrico.</span><span class="sxs-lookup"><span data-stu-id="a4823-130">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="a4823-131">Una vez creada una nueva instancia de la clase, la información de la clave puede extraerse mediante uno de estos dos métodos:</span><span class="sxs-lookup"><span data-stu-id="a4823-131">After a new instance of the class is created, the key information can be extracted using one of two methods:</span></span>  
  
-   <span data-ttu-id="a4823-132">El método <xref:System.Security.Cryptography.RSA.ToXmlString%2A> , que devuelve una representación XML de la información de la clave.</span><span class="sxs-lookup"><span data-stu-id="a4823-132">The <xref:System.Security.Cryptography.RSA.ToXmlString%2A> method, which returns an XML representation of the key information.</span></span>  
  
-   <span data-ttu-id="a4823-133">Método <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> que devuelve una estructura <xref:System.Security.Cryptography.RSAParameters> que contiene la información de la clave.</span><span class="sxs-lookup"><span data-stu-id="a4823-133">The <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span>  
  
 <span data-ttu-id="a4823-134">Ambos métodos aceptan un valor booleano que indica si hay que devolver sólo la información de la clave pública o si se devuelve también la correspondiente a la clave privada.</span><span class="sxs-lookup"><span data-stu-id="a4823-134">Both methods accept a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span> <span data-ttu-id="a4823-135">El valor de una clase **RSACryptoServiceProvider** puede inicializarse con una estructura **RSAParameters** mediante el método <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="a4823-135">An **RSACryptoServiceProvider** class can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> method.</span></span>  
  
 <span data-ttu-id="a4823-136">Las claves privadas asimétricas nunca deben almacenarse literalmente o en texto sin formato en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a4823-136">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="a4823-137">Si debe almacenar una clave privada, utilice un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="a4823-137">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="a4823-138">Para más información sobre cómo almacenar una clave privada en un contenedor de claves, vea [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="a4823-138">For more on how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="a4823-139">En el siguiente ejemplo de código se crea una nueva instancia de la clase **RSACryptoServiceProvider** , se crea un par de claves pública y privada, y se guarda la información de la clave pública en una estructura **RSAParameters** .</span><span class="sxs-lookup"><span data-stu-id="a4823-139">The following code example creates a new instance of the **RSACryptoServiceProvider** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim RSA as RSACryptoServiceProvider = new RSACryptoServiceProvider()  
'Save the public key information to an RSAParameters structure.  
Dim RSAKeyInfo As RSAParameters = RSA.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
//Save the public key information to an RSAParameters structure.  
RSAParameters RSAKeyInfo = RSA.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4823-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4823-140">See Also</span></span>  
 [<span data-ttu-id="a4823-141">Cifrar datos</span><span class="sxs-lookup"><span data-stu-id="a4823-141">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)  
 [<span data-ttu-id="a4823-142">Descifrar datos</span><span class="sxs-lookup"><span data-stu-id="a4823-142">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)  
 [<span data-ttu-id="a4823-143">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="a4823-143">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="a4823-144">Almacenar claves asimétricas en un contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="a4823-144">How to: Store Asymmetric Keys in a Key Container</span></span>](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md)
