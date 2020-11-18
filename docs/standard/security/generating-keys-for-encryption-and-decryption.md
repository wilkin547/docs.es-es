---
title: Generar claves para cifrado y descifrado
description: Aprenda a crear y administrar claves simétricas y asimétricas para el cifrado y el descifrado en .NET.
ms.date: 07/14/2020
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
ms.openlocfilehash: aa95204a90f2aee684cdd20095d1816e890a0306
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831083"
---
# <a name="generating-keys-for-encryption-and-decryption"></a>Generar claves para cifrado y descifrado
La creación y administración de claves es una parte importante del proceso criptográfico. Los algoritmos simétricos requieren la creación de una clave y un IV (Initialization Vector, vector de inicialización). La clave debe mantenerse en secreto y a salvo de quienes no deban descifrar los datos. No es necesario que el vector de inicialización sea secreto, pero debe cambiarse para cada sesión. Los algoritmos asimétricos requieren la creación de una clave pública y una clave privada. La clave pública puede revelarse a cualquiera, mientras que la privada debe conocerla sólo la parte que descifrará los datos cifrados con la clave pública. En esta sección se describe cómo generar y administrar claves para algoritmos simétricos y asimétricos.  
  
## <a name="symmetric-keys"></a>Claves simétricas  
 Las clases de cifrado simétrico que proporciona .NET requieren una clave y un nuevo vector de inicialización (IV) para cifrar y descifrar los datos. Siempre que cree una nueva instancia de una de las clases criptográficas simétricas administradas mediante el `Create()` método sin parámetros, se creará automáticamente una nueva clave y un IV. Cualquier persona a la que permita descifrar sus datos debe poseer la misma clave y el mismo IV, y utilizar el mismo algoritmo. Normalmente, debe crearse una nueva clave y vector de inicialización para cada sesión, y ni la clave ni el vector deberían almacenarse para utilizarlos en una sesión posterior.  
  
 Para comunicar una clave simétrica y un IV a una parte remota, la clave simétrica normalmente se cifra usando cifrado asimétrico. El envío de la clave a través de una red insegura sin cifrarla resulta peligroso, ya que quien intercepte la clave y el IV podrá descifrar los datos.  
  
 En el ejemplo siguiente se muestra la creación de una nueva instancia de la clase de implementación predeterminada para el <xref:System.Security.Cryptography.Aes> algoritmo.  
  
```vb  
Dim aes As Aes = Aes.Create()  
```  
  
```csharp  
Aes aes = Aes.Create();  
```  
  
 Cuando se ejecuta el código anterior, se genera una nueva clave y un IV, y se colocan en las propiedades **Key** e **IV** , respectivamente.  
  
 En ocasiones tendrá que generar varias claves. En este caso, puede crear una nueva instancia de una clase que implemente un algoritmo simétrico y después crear una nueva clave e IV mediante una llamada a los métodos **GenerateKey** y **GenerateIV** . En el ejemplo de código siguiente se muestra cómo crear nuevas claves y IV después de realizar una nueva instancia de la clase criptográfica simétrica.  
  
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
  
 Cuando se ejecuta el código anterior, se generan una clave y un IV cuando se realiza la nueva instancia de **AES** . Se crean otra clave e IV cuando se llama a los métodos **GenerateKey** y **GenerateIV** .
  
## <a name="asymmetric-keys"></a>Claves asimétricas

 .NET proporciona la <xref:System.Security.Cryptography.RSA> clase para el cifrado asimétrico. Esta clase crea un par de claves pública y privada cuando se usa el método sin parámetros `Create()` para crear una nueva instancia. Las claves asimétricas pueden almacenarse para utilizarse en sesiones múltiples o bien generarse para una sesión únicamente. Aunque la clave pública puede ponerse a disposición general, la clave privada debe guardarse bien.  
  
 Un par de claves pública y privada se genera siempre que se crea una nueva instancia de una clase de algoritmo asimétrico. Después de crear una nueva instancia de la clase, se puede extraer la información de la clave mediante el <xref:System.Security.Cryptography.RSA.ExportParameters%2A> método, que devuelve una <xref:System.Security.Cryptography.RSAParameters> estructura que contiene la información de la clave. El método acepta un valor booleano que indica si se devuelve solo la información de clave pública o si se devuelve la información de clave pública y de clave privada.

También hay otros métodos que permiten extraer información de clave, como:

* <xref:System.Security.Cryptography.RSA.ExportRSAPublicKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.RSA.ExportRSAPrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportSubjectPublicKeyInfo%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportPkcs8PrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportEncryptedPkcs8PrivateKey%2A?displayProperty=nameWithType>

Una instancia de **RSA** se puede inicializar con el valor de una estructura **RSAParameters** mediante el <xref:System.Security.Cryptography.RSA.ImportParameters%2A> método. O bien, cree una nueva instancia de mediante el <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> método.  
  
 Las claves privadas asimétricas nunca deben almacenarse literalmente o en texto sin formato en el equipo local. Si debe almacenar una clave privada, utilice un contenedor de claves. Para obtener más información sobre cómo almacenar una clave privada en un contenedor de claves, vea [Cómo: almacenar claves asimétricas en un contenedor de claves](how-to-store-asymmetric-keys-in-a-key-container.md).  
  
 En el ejemplo de código siguiente se crea una nueva instancia de la clase **RSA** , se crea un par de claves pública y privada, y se guarda la información de clave pública en una estructura **RSAParameters** .  
  
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
  
## <a name="see-also"></a>Vea también

- [Cifrar datos](encrypting-data.md)
- [Descifrar datos](decrypting-data.md)
- [servicios criptográficos](cryptographic-services.md)
- [Procedimiento para almacenar claves asimétricas en un contenedor de claves](how-to-store-asymmetric-keys-in-a-key-container.md)
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
