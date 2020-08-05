---
title: Generar claves para cifrado y descifrado
description: Aprenda a crear y administrar claves simétricas y asimétricas para el cifrado y el descifrado en .NET.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET], keys
- symmetric keys
- asymmetric keys [.NET]
- cryptography [.NET], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: 7ce19dc465fb1fac22545398e0724e6b76dd7098
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556948"
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="3e362-103">Generar claves para cifrado y descifrado</span><span class="sxs-lookup"><span data-stu-id="3e362-103">Generating Keys for Encryption and Decryption</span></span>
<span data-ttu-id="3e362-104">La creación y administración de claves es una parte importante del proceso criptográfico.</span><span class="sxs-lookup"><span data-stu-id="3e362-104">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="3e362-105">Los algoritmos simétricos requieren la creación de una clave y un IV (Initialization Vector, vector de inicialización).</span><span class="sxs-lookup"><span data-stu-id="3e362-105">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="3e362-106">La clave debe mantenerse en secreto y a salvo de quienes no deban descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="3e362-106">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="3e362-107">No es necesario que el vector de inicialización sea secreto, pero debe cambiarse para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="3e362-107">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="3e362-108">Los algoritmos asimétricos requieren la creación de una clave pública y una clave privada.</span><span class="sxs-lookup"><span data-stu-id="3e362-108">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="3e362-109">La clave pública puede revelarse a cualquiera, mientras que la privada debe conocerla sólo la parte que descifrará los datos cifrados con la clave pública.</span><span class="sxs-lookup"><span data-stu-id="3e362-109">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="3e362-110">En esta sección se describe cómo generar y administrar claves para algoritmos simétricos y asimétricos.</span><span class="sxs-lookup"><span data-stu-id="3e362-110">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="3e362-111">Claves simétricas</span><span class="sxs-lookup"><span data-stu-id="3e362-111">Symmetric Keys</span></span>  
 <span data-ttu-id="3e362-112">Las clases de cifrado simétrico que proporciona .NET requieren una clave y un nuevo vector de inicialización (IV) para cifrar y descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="3e362-112">The symmetric encryption classes supplied by .NET require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="3e362-113">Siempre que cree una nueva instancia de una de las clases criptográficas simétricas administradas mediante el `Create()` método sin parámetros, se creará automáticamente una nueva clave y un IV.</span><span class="sxs-lookup"><span data-stu-id="3e362-113">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the parameterless `Create()` method, a new key and IV are automatically created.</span></span> <span data-ttu-id="3e362-114">Cualquier persona a la que permita descifrar sus datos debe poseer la misma clave y el mismo IV, y utilizar el mismo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="3e362-114">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="3e362-115">Normalmente, debe crearse una nueva clave y vector de inicialización para cada sesión, y ni la clave ni el vector deberían almacenarse para utilizarlos en una sesión posterior.</span><span class="sxs-lookup"><span data-stu-id="3e362-115">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="3e362-116">Para comunicar una clave simétrica y un IV a una parte remota, la clave simétrica normalmente se cifra usando cifrado asimétrico.</span><span class="sxs-lookup"><span data-stu-id="3e362-116">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="3e362-117">El envío de la clave a través de una red insegura sin cifrarla resulta peligroso, ya que quien intercepte la clave y el IV podrá descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="3e362-117">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span>  
  
 <span data-ttu-id="3e362-118">En el ejemplo siguiente se muestra la creación de una nueva instancia de la clase de implementación predeterminada para el <xref:System.Security.Cryptography.Aes> algoritmo.</span><span class="sxs-lookup"><span data-stu-id="3e362-118">The following example shows the creation of a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span>  
  
```vb  
Dim aes As Aes = Aes.Create()  
```  
  
```csharp  
Aes aes = Aes.Create();  
```  
  
 <span data-ttu-id="3e362-119">Cuando se ejecuta el código anterior, se genera una nueva clave y un IV, y se colocan en las propiedades **Key** e **IV** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3e362-119">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="3e362-120">En ocasiones tendrá que generar varias claves.</span><span class="sxs-lookup"><span data-stu-id="3e362-120">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="3e362-121">En este caso, puede crear una nueva instancia de una clase que implemente un algoritmo simétrico y después crear una nueva clave e IV mediante una llamada a los métodos **GenerateKey** y **GenerateIV** .</span><span class="sxs-lookup"><span data-stu-id="3e362-121">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="3e362-122">En el ejemplo de código siguiente se muestra cómo crear nuevas claves y IV después de realizar una nueva instancia de la clase criptográfica simétrica.</span><span class="sxs-lookup"><span data-stu-id="3e362-122">The following code example illustrates how to create new keys and IVs after a new instance of the symmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim aes As Aes = Aes.Create()  
aes.GenerateIV()  
aes.GenerateKey()  
```  
  
```csharp  
Aes aes = Aes.Create();  
aes.GenerateIV();  
aes.GenerateKey();  
```  
  
 <span data-ttu-id="3e362-123">Cuando se ejecuta el código anterior, se generan una clave y un IV cuando se realiza la nueva instancia de **AES** .</span><span class="sxs-lookup"><span data-stu-id="3e362-123">When the preceding code is executed, a key and IV are generated when the new instance of **Aes** is made.</span></span> <span data-ttu-id="3e362-124">Se crean otra clave e IV cuando se llama a los métodos **GenerateKey** y **GenerateIV** .</span><span class="sxs-lookup"><span data-stu-id="3e362-124">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>
  
## <a name="asymmetric-keys"></a><span data-ttu-id="3e362-125">Claves asimétricas</span><span class="sxs-lookup"><span data-stu-id="3e362-125">Asymmetric Keys</span></span>

 <span data-ttu-id="3e362-126">.NET proporciona la <xref:System.Security.Cryptography.RSA> clase para el cifrado asimétrico.</span><span class="sxs-lookup"><span data-stu-id="3e362-126">.NET provides the <xref:System.Security.Cryptography.RSA> class for asymmetric encryption.</span></span> <span data-ttu-id="3e362-127">Esta clase crea un par de claves pública y privada cuando se usa el método sin parámetros `Create()` para crear una nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="3e362-127">This class creates a public/private key pair when you use the parameterless `Create()` method to create a new instance.</span></span> <span data-ttu-id="3e362-128">Las claves asimétricas pueden almacenarse para utilizarse en sesiones múltiples o bien generarse para una sesión únicamente.</span><span class="sxs-lookup"><span data-stu-id="3e362-128">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="3e362-129">Aunque la clave pública puede ponerse a disposición general, la clave privada debe guardarse bien.</span><span class="sxs-lookup"><span data-stu-id="3e362-129">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="3e362-130">Un par de claves pública y privada se genera siempre que se crea una nueva instancia de una clase de algoritmo asimétrico.</span><span class="sxs-lookup"><span data-stu-id="3e362-130">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="3e362-131">Después de crear una nueva instancia de la clase, se puede extraer la información de la clave mediante el <xref:System.Security.Cryptography.RSA.ExportParameters%2A> método, que devuelve una <xref:System.Security.Cryptography.RSAParameters> estructura que contiene la información de la clave.</span><span class="sxs-lookup"><span data-stu-id="3e362-131">After a new instance of the class is created, the key information can be extracted using the <xref:System.Security.Cryptography.RSA.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span> <span data-ttu-id="3e362-132">El método acepta un valor booleano que indica si se devuelve solo la información de clave pública o si se devuelve la información de clave pública y de clave privada.</span><span class="sxs-lookup"><span data-stu-id="3e362-132">The method accepts a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span>

<span data-ttu-id="3e362-133">También hay otros métodos que permiten extraer información de clave, como:</span><span class="sxs-lookup"><span data-stu-id="3e362-133">There are also other methods that let you extract key information, such as:</span></span>

* <xref:System.Security.Cryptography.RSA.ExportRSAPublicKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.RSA.ExportRSAPrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportSubjectPublicKeyInfo%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportPkcs8PrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportEncryptedPkcs8PrivateKey%2A?displayProperty=nameWithType>

<span data-ttu-id="3e362-134">Una instancia de **RSA** se puede inicializar con el valor de una estructura **RSAParameters** mediante el <xref:System.Security.Cryptography.RSA.ImportParameters%2A> método.</span><span class="sxs-lookup"><span data-stu-id="3e362-134">An **RSA** instance can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSA.ImportParameters%2A> method.</span></span> <span data-ttu-id="3e362-135">O bien, cree una nueva instancia de mediante el <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="3e362-135">Or create a new instance by using the <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="3e362-136">Las claves privadas asimétricas nunca deben almacenarse literalmente o en texto sin formato en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="3e362-136">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="3e362-137">Si debe almacenar una clave privada, utilice un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="3e362-137">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="3e362-138">Para obtener más información sobre cómo almacenar una clave privada en un contenedor de claves, vea [Cómo: almacenar claves asimétricas en un contenedor de claves](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="3e362-138">For more information about how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="3e362-139">En el ejemplo de código siguiente se crea una nueva instancia de la clase **RSA** , se crea un par de claves pública y privada, y se guarda la información de clave pública en una estructura **RSAParameters** .</span><span class="sxs-lookup"><span data-stu-id="3e362-139">The following code example creates a new instance of the **RSA** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSA = RSA.Create()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSA rsa = RSA.Create();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e362-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e362-140">See also</span></span>

- [<span data-ttu-id="3e362-141">Cifrar datos</span><span class="sxs-lookup"><span data-stu-id="3e362-141">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="3e362-142">Descifrar datos</span><span class="sxs-lookup"><span data-stu-id="3e362-142">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="3e362-143">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="3e362-143">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="3e362-144">Procedimiento para almacenar claves asimétricas en un contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="3e362-144">How to: Store Asymmetric Keys in a Key Container</span></span>](how-to-store-asymmetric-keys-in-a-key-container.md)
- [<span data-ttu-id="3e362-145">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="3e362-145">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="3e362-146">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="3e362-146">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
