---
title: Generar claves para cifrado y descifrado
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 839a04d8a06e782582705cf0d9ad92d2e2df6af6
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2018
ms.locfileid: "45641461"
---
# <a name="generating-keys-for-encryption-and-decryption"></a>Generar claves para cifrado y descifrado
La creación y administración de claves es una parte importante del proceso criptográfico. Los algoritmos simétricos requieren la creación de una clave y un IV (Initialization Vector, vector de inicialización). La clave debe mantenerse en secreto y a salvo de quienes no deban descifrar los datos. No es necesario que el vector de inicialización sea secreto, pero debe cambiarse para cada sesión. Los algoritmos asimétricos requieren la creación de una clave pública y una clave privada. La clave pública puede revelarse a cualquiera, mientras que la privada debe conocerla sólo la parte que descifrará los datos cifrados con la clave pública. En esta sección se describe cómo generar y administrar claves para algoritmos simétricos y asimétricos.  
  
## <a name="symmetric-keys"></a>Claves simétricas  
 Las clases de cifrado simétrico que proporciona .NET Framework requieren una clave y un nuevo vector de inicialización (IV) para cifrar y descifrar datos. Siempre que cree una nueva instancia de una de las clases criptográficas simétricas administradas utilizando el constructor predeterminado, se crean automáticamente una clave y un vector de inicialización nuevos. Cualquier persona a la que permita descifrar sus datos debe poseer la misma clave y el mismo IV, y utilizar el mismo algoritmo. Normalmente, debe crearse una nueva clave y vector de inicialización para cada sesión, y ni la clave ni el vector deberían almacenarse para utilizarlos en una sesión posterior.  
  
 Para comunicar una clave simétrica y un IV a una parte remota, la clave simétrica normalmente se cifra usando cifrado asimétrico. El envío de la clave a través de una red insegura sin cifrarla resulta peligroso, ya que quien intercepte la clave y el IV podrá descifrar los datos. Para obtener más información sobre el intercambio de datos mediante el cifrado, vea [Crear un esquema criptográfico](../../../docs/standard/security/creating-a-cryptographic-scheme.md).  
  
 En el ejemplo siguiente se muestra la creación de una nueva instancia de la clase <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> que implementa el algoritmo TripleDES.  
  
```vb  
Dim TDES As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
```  
  
```csharp  
TripleDESCryptoServiceProvider TDES = new TripleDESCryptoServiceProvider();  
```  
  
 Cuando se ejecuta el código anterior, se genera una nueva clave y un IV, y se colocan en las propiedades **Key** e **IV** , respectivamente.  
  
 En ocasiones tendrá que generar varias claves. En este caso, puede crear una nueva instancia de una clase que implemente un algoritmo simétrico y después crear una nueva clave e IV mediante una llamada a los métodos **GenerateKey** y **GenerateIV** . En el ejemplo de código siguiente se ilustra cómo crear nuevas claves y vectores de inicialización una vez creada una nueva instancia de la clase criptográfica asimétrica.  
  
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
  
 Cuando se ejecuta el código anterior, se generan una clave y un IV al crear la nueva instancia de **TripleDESCryptoServiceProvider** . Se crean otra clave e IV cuando se llama a los métodos **GenerateKey** y **GenerateIV** .  
  
## <a name="asymmetric-keys"></a>Claves asimétricas  
 .NET Framework proporciona las clases <xref:System.Security.Cryptography.RSACryptoServiceProvider> y <xref:System.Security.Cryptography.DSACryptoServiceProvider> para el cifrado asimétrico. Estas clases crean un par de claves pública y privada cuando utiliza el constructor predeterminado para crear una nueva instancia. Las claves asimétricas pueden almacenarse para utilizarse en sesiones múltiples o bien generarse para una sesión únicamente. Aunque la clave pública puede ponerse a disposición general, la clave privada debe guardarse bien.  
  
 Un par de claves pública y privada se genera siempre que se crea una nueva instancia de una clase de algoritmo asimétrico. Una vez creada una nueva instancia de la clase, la información de la clave puede extraerse mediante uno de estos dos métodos:  
  
-   El método <xref:System.Security.Cryptography.RSA.ToXmlString%2A> , que devuelve una representación XML de la información de la clave.  
  
-   Método <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> que devuelve una estructura <xref:System.Security.Cryptography.RSAParameters> que contiene la información de la clave.  
  
 Ambos métodos aceptan un valor booleano que indica si hay que devolver sólo la información de la clave pública o si se devuelve también la correspondiente a la clave privada. El valor de una clase **RSACryptoServiceProvider** puede inicializarse con una estructura **RSAParameters** mediante el método <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> .  
  
 Las claves privadas asimétricas nunca deben almacenarse literalmente o en texto sin formato en el equipo local. Si debe almacenar una clave privada, utilice un contenedor de claves. Para más información sobre cómo almacenar una clave privada en un contenedor de claves, vea [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).  
  
 En el siguiente ejemplo de código se crea una nueva instancia de la clase **RSACryptoServiceProvider** , se crea un par de claves pública y privada, y se guarda la información de la clave pública en una estructura **RSAParameters** .  
  
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
  
## <a name="see-also"></a>Vea también

- [Cifrar datos](../../../docs/standard/security/encrypting-data.md)  
- [Descifrar datos](../../../docs/standard/security/decrypting-data.md)  
- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
- [Almacenar claves asimétricas en un contenedor de claves](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md)
