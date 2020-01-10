---
title: Descifrar datos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET Framework], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 37194380d9f08d328f836bcb8648772348958768
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706245"
---
# <a name="decrypting-data"></a>Descifrar datos

El descifrado es la operación inversa del cifrado. Para el cifrado de clave secreta, debe conocer la clave y el IV que se usaron para cifrar los datos. Para el cifrado de clave pública, debe conocer la clave pública (si los datos se cifraron mediante la clave privada) o la clave privada (si los datos se cifran mediante la clave pública).

## <a name="symmetric-decryption"></a>Descifrado simétrico

El descifrado de los datos cifrados con algoritmos simétricos es similar al proceso usado para cifrar datos con algoritmos simétricos. La clase <xref:System.Security.Cryptography.CryptoStream> se usa con las clases de criptografía simétrica que proporciona .NET Framework para descifrar datos leídos de cualquier objeto de secuencia administrado.

En el ejemplo siguiente se muestra cómo crear una nueva instancia de la clase <xref:System.Security.Cryptography.RijndaelManaged> y usarla para realizar el descifrado en un objeto <xref:System.Security.Cryptography.CryptoStream> . En primer lugar, en este ejemplo se crea una nueva instancia de la clase **RijndaelManaged** . A continuación, se crea un objeto **CryptoStream** y se inicializa con el valor de una secuencia administrada llamada `myStream`. Después, se pasa al método **CreateDecryptor** de la clase **RijndaelManaged** la misma clave e IV que se usaron para el cifrado y, a continuación, se pasa al constructor **CryptoStream** . Por último, se pasa la enumeración **CryptoStreamMode.Read** al constructor **CryptoStream** para especificar el acceso de lectura a la secuencia.

```vb
Dim rmCrypto As New RijndaelManaged()
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateDecryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Read)
```

```csharp
RijndaelManaged rmCrypto = new RijndaelManaged();
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateDecryptor(Key, IV), CryptoStreamMode.Read);
```

En el ejemplo siguiente se muestra todo el proceso de crear una secuencia, descifrarla, leer en ella y cerrarla. Se crea un objeto <xref:System.Net.Sockets.TcpListener> que inicializa una secuencia de red cuando se realiza una conexión al objeto de escucha. A continuación, la secuencia de red se descifra usando las clases **CryptoStream** y **RijndaelManaged** . En este ejemplo se supone que los valores de la clave y del IV se transfirieron correctamente o se acordaron previamente. No se muestra el código necesario para cifrar y transferir estos valores.

```vb
Imports System.IO
Imports System.Net
Imports System.Net.Sockets
Imports System.Security.Cryptography
Imports System.Threading

Module Module1
    Sub Main()
            'The key and IV must be the same values that were used
            'to encrypt the stream.
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
        Try
            'Initialize a TCPListener on port 11000
            'using the current IP address.
            Dim tcpListen As New TcpListener(IPAddress.Any, 11000)

            'Start the listener.
            tcpListen.Start()

            'Check for a connection every five seconds.
            While Not tcpListen.Pending()
                Console.WriteLine("Still listening. Will try in 5 seconds.")

                Thread.Sleep(5000)
            End While

            'Accept the client if one is found.
            Dim tcp As TcpClient = tcpListen.AcceptTcpClient()

            'Create a network stream from the connection.
            Dim netStream As NetworkStream = tcp.GetStream()

            'Create a new instance of the RijndaelManaged class
            'and decrypt the stream.
            Dim rmCrypto As New RijndaelManaged()

            'Create an instance of the CryptoStream class, pass it the NetworkStream, and decrypt
            'it with the Rijndael class using the key and IV.
            Dim cryptStream As New CryptoStream(netStream, rmCrypto.CreateDecryptor(key, iv), CryptoStreamMode.Read)

            'Read the stream.
            Dim sReader As New StreamReader(cryptStream)

            'Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd())

            'Close the streams.
            sReader.Close()
            netStream.Close()
            tcp.Close()
            'Catch any exceptions.
        Catch
            Console.WriteLine("The Listener Failed.")
        End Try
    End Sub
End Module
```

```csharp
using System;
using System.IO;
using System.Net;
using System.Net.Sockets;
using System.Security.Cryptography;
using System.Threading;

class Class1
{
   static void Main(string[] args)
   {
      //The key and IV must be the same values that were used
      //to encrypt the stream.
      byte[] key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};
      byte[] iv = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};
      try
      {
         //Initialize a TCPListener on port 11000
         //using the current IP address.
         TcpListener tcpListen = new TcpListener(IPAddress.Any, 11000);

         //Start the listener.
         tcpListen.Start();

         //Check for a connection every five seconds.
         while(!tcpListen.Pending())
         {
            Console.WriteLine("Still listening. Will try in 5 seconds.");
            Thread.Sleep(5000);
         }

         //Accept the client if one is found.
         TcpClient tcp = tcpListen.AcceptTcpClient();

         //Create a network stream from the connection.
         NetworkStream netStream = tcp.GetStream();

         //Create a new instance of the RijndaelManaged class
         // and decrypt the stream.
         RijndaelManaged rmCrypto = new RijndaelManaged();

         //Create a CryptoStream, pass it the NetworkStream, and decrypt
         //it with the Rijndael class using the key and IV.
         CryptoStream cryptStream = new CryptoStream(netStream,
            rmCrypto.CreateDecryptor(key, iv),
            CryptoStreamMode.Read);

         //Read the stream.
         StreamReader sReader = new StreamReader(cryptStream);

         //Display the message.
         Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd());

         //Close the streams.
         sReader.Close();
         netStream.Close();
         tcp.Close();
      }
      //Catch any exceptions.
      catch
      {
         Console.WriteLine("The Listener Failed.");
      }
   }
}
```

Para que el ejemplo anterior funcione, debe realizarse una conexión cifrada con el agente de escucha. La conexión debe usar la misma clave, IV y algoritmo usados en el agente de escucha. Si se realiza esa conexión, el mensaje se descifra y se muestra en la consola.

## <a name="asymmetric-decryption"></a>Descifrado asimétrico

Normalmente, una parte (parte A) genera tanto una clave pública como privada y la almacena en memoria o en un contenedor de claves criptográficas. A continuación, la parte A envía la clave pública a otra parte (parte B). Mediante el uso de la clave pública, la parte B cifra los datos y envía los datos de vuelta a la entidad A. Después de recibir los datos, la parte A los descifra mediante la clave privada correspondiente. El descifrado será correcto solo si la parte A usa la clave privada que corresponde a la clave pública que la parte B usó para cifrar los datos.

Para obtener información sobre cómo almacenar una clave asimétrica en un contenedor de claves criptográficas seguro y cómo recuperar posteriormente la clave asimétrica, consulte [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).

En el ejemplo siguiente se muestra el descifrado de dos matrices de bytes que representan una clave simétrica y un IV. Para obtener información sobre cómo extraer la clave pública asimétrica del objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider> en un formato que se pueda enviar fácilmente a un tercero, consulte [Encrypting Data](../../../docs/standard/security/encrypting-data.md).

```vb
'Create a new instance of the RSACryptoServiceProvider class.
Dim rsa As New RSACryptoServiceProvider()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, False)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, False)
```

```csharp
//Create a new instance of the RSACryptoServiceProvider class.
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, false);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , false);
```

## <a name="see-also"></a>Vea también

- [Generar claves para cifrado y descifrado](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)
- [Cifrar datos](../../../docs/standard/security/encrypting-data.md)
- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
