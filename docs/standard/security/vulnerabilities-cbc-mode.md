---
title: Vulnerabilidad de descifrado CBC
description: Aprenda a detectar y mitigar vulnerabilidades de temporización con el descifrado simétrico en modo Cipher-Block-Chaining (CBC) mediante relleno.
ms.date: 06/12/2018
author: blowdart
ms.openlocfilehash: 47520ea4c9c7d0ef4d79378c93c6ce1f2ba7dd6d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186092"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Vulnerabilidades de temporalización con descifrado simétrico en modo CBC al usar el relleno

Microsoft cree que ya no es seguro descifrar los datos cifrados con el modo Cipher-Block-Chaining (CBC) de cifrado simétrico cuando se ha aplicado relleno verificable sin garantizar primero la integridad del texto cifrado, excepto para muy específicos Circunstancias. Este juicio se basa en la investigación criptográfica actualmente conocida.

## <a name="introduction"></a>Introducción

Un ataque de oráculo de relleno es un tipo de ataque contra datos cifrados que permite al atacante descifrar el contenido de los datos, sin conocer la clave.

Un oráculo hace referencia a un "tell" que proporciona a un atacante información sobre si la acción que está ejecutando es correcta o no. Imagínese jugar un juego de mesa o de cartas con un niño. Cuando su cara se ilumina con una gran sonrisa porque piensan que están a punto de hacer un buen movimiento, eso es un oráculo. Usted, como el oponente, puede utilizar este oráculo para planificar su próximo movimiento apropiadamente.

El relleno es un término criptográfico específico. Algunos cifrados, que son los algoritmos utilizados para cifrar los datos, funcionan en bloques de datos donde cada bloque tiene un tamaño fijo. Si los datos que desea cifrar no son del tamaño adecuado para rellenar los bloques, los datos se rellenan hasta que lo hacen. Muchas formas de relleno requieren que el relleno esté siempre presente, incluso si la entrada original era del tamaño correcto. Esto permite que el relleno siempre se elimine de forma segura al descifrar.

Al poner las dos cosas juntas, una implementación de software con un oráculo de relleno revela si los datos descifrados tienen un relleno válido. El oráculo podría ser algo tan simple como devolver un valor que dice "Relleno no válido" o algo más complicado como tomar un tiempo mediblemente diferente para procesar un bloque válido en lugar de un bloque no válido.

Los cifrados basados en bloques tienen otra propiedad, denominada modo, que determina la relación de datos del primer bloque con los datos del segundo bloque, etc. Uno de los modos más utilizados es CBC. CBC introduce un bloque aleatorio inicial, conocido como vector de inicialización (IV), y combina el bloque anterior con el resultado del cifrado estático para que sea de tal manera que cifrar el mismo mensaje con la misma clave no siempre produce la misma salida cifrada.

Un atacante puede usar un oráculo de relleno, en combinación con cómo se estructuran los datos de CBC, para enviar mensajes ligeramente modificados al código que expone el oráculo y seguir enviando datos hasta que el oráculo les diga que los datos son correctos. A partir de esta respuesta, el atacante puede descifrar el mensaje byte a byte.

Las redes informáticas modernas son de tan alta calidad que un atacante puede detectar diferencias muy pequeñas (menos de 0,1 ms) en el tiempo de ejecución en sistemas remotos.Las aplicaciones que asumen que un descifrado correcto solo puede ocurrir cuando los datos no se manipulan pueden ser vulnerables a ataques de herramientas diseñadas para observar diferencias en el descifrado exitoso y sin éxito. Si bien esta diferencia de tiempo puede ser más significativa en algunos idiomas o bibliotecas que en otros, ahora se cree que se trata de una amenaza práctica para todos los lenguajes y bibliotecas cuando se tiene en cuenta la respuesta de la aplicación al error.

Este ataque se basa en la capacidad de cambiar los datos cifrados y probar el resultado con el oráculo. La única manera de mitigar completamente el ataque es detectar cambios en los datos cifrados y negarse a realizar cualquier acción en él. La forma estándar de hacerlo es crear una firma para los datos y validar esa firma antes de realizar cualquier operación. La firma debe ser verificable, no puede ser creada por el atacante, de lo contrario cambiarían los datos cifrados y, a continuación, calcularían una nueva firma en función de los datos modificados. Un tipo común de firma adecuada se conoce como código de autenticación de mensajes hash con clave (HMAC). Un HMAC difiere de una suma de comprobación en que toma una clave secreta, conocida sólo por la persona que produce el HMAC y por la persona que lo valida. Sin la posesión de la llave, no se puede producir un HMAC correcto. Cuando reciba los datos, tomaría los datos cifrados, calcularía de forma independiente el HMAC con la clave secreta que usted y el remitente comparten y, a continuación, compararía el HMAC que enviaron con el que calculó. Esta comparación debe ser tiempo constante, de lo contrario ha agregado otro oráculo detectable, lo que permite un tipo diferente de ataque.

En resumen, para utilizar cifrados de bloques CBC acolchados de forma segura, debe combinarlos con un HMAC (u otra comprobación de integridad de datos) que valide mediante una comparación de tiempo constante antes de intentar descifrar los datos. Puesto que todos los mensajes alterados tardan la misma cantidad de tiempo en producir una respuesta, se evita el ataque.

## <a name="who-is-vulnerable"></a>Quién es vulnerable

Esta vulnerabilidad se aplica tanto a las aplicaciones administradas como a las nativas que realizan su propio cifrado y descifrado. Esto incluye, por ejemplo:

- Una aplicación que cifra una cookie para su posterior descifrado en el servidor.
- Una aplicación de base de datos que proporciona a los usuarios la capacidad de insertar datos en una tabla cuyas columnas se descifran más adelante.
- Una aplicación de transferencia de datos que se basa en el cifrado mediante una clave compartida para proteger los datos en tránsito.
- Una aplicación que cifra y descifra los mensajes "dentro" del túnel TLS.

Tenga en cuenta que el uso de TLS por sí solo puede no protegerle en estos escenarios.

Una aplicación vulnerable:

- Descifra los datos mediante el modo de cifrado CBC con un modo de relleno verificable, como PKCS-7 o ANSI X.923.
- Realiza el descifrado sin haber realizado una comprobación de integridad de datos (a través de un MAC o una firma digital asimétrica).

Esto también se aplica a las aplicaciones creadas sobre abstracciones sobre estos primitivos, como la estructura EnvelopedData de sintaxis de mensajes criptográficos (PKCS-7/CMS).

## <a name="related-areas-of-concern"></a>Temas de preocupación relacionados

La investigación ha llevado a Microsoft a preocuparse más por los mensajes CBC que están acolchados con relleno equivalente a ISO 10126 cuando el mensaje tiene una estructura de pie de página conocida o predecible. Por ejemplo, contenido preparado bajo las reglas de la recomendación de procesamiento y sintaxis de cifrado XML de W3C (xmlenc, EncryptedXml). Aunque la guía de W3C para firmar el mensaje y luego cifrar se consideraba adecuada en ese momento, Microsoft ahora recomienda realizar siempre el cifrado y luego firmar.

Los desarrolladores de aplicaciones siempre deben tener en cuenta la comprobación de la aplicabilidad de una clave de firma asimétrica, ya que no hay ninguna relación de confianza inherente entre una clave asimétrica y un mensaje arbitrario.

## <a name="details"></a>Detalles

Históricamente, ha habido consenso en que es importante cifrar y autenticar datos importantes, utilizando medios como firmas HMAC o RSA. Sin embargo, ha habido una guía menos clara sobre cómo secuenciar las operaciones de cifrado y autenticación. Debido a la vulnerabilidad detallada en este artículo, la guía de Microsoft es ahora usar siempre el paradigma "cifrar entonces-firmar". Es decir, primero cifre los datos mediante una clave simétrica y, a continuación, calcule una firma MAC o asimétrica sobre el texto cifrado (datos cifrados). Al descifrar datos, realice lo contrario. Primero, confirme el MAC o la firma del texto cifrado, después descifrelo.

Se sabe que existe una clase de vulnerabilidades conocidas como "ataques de oráculos de relleno" durante más de 10 años. Estas vulnerabilidades permiten a un atacante descifrar datos cifrados por algoritmos de bloques simétricos, como AES y 3DES, utilizando no más de 4096 intentos por bloque de datos. Estas vulnerabilidades hacen uso del hecho de que los cifrados de bloques se utilizan con más frecuencia con datos de relleno verificables al final. Se encontró que si un atacante puede manipular el texto cifrado y averiguar si la manipulación causó un error en el formato del relleno al final, el atacante puede descifrar los datos.

Inicialmente, los ataques prácticos se basaban en servicios que devolverían diferentes códigos de error en función de si el relleno era válido, como la vulnerabilidad ASP.NET [MS10-070.](/security-updates/SecurityBulletins/2010/ms10-070) Sin embargo, Microsoft ahora cree que es práctico llevar a cabo ataques similares utilizando solo las diferencias de tiempo entre el procesamiento de relleno válido y no válido.

Siempre que el esquema de cifrado emplee una firma y que la verificación de la firma se realice con un tiempo de ejecución fijo para una longitud determinada de datos (independientemente del contenido), la integridad de los datos se puede verificar sin emitir ninguna información a un atacante a través de un [canal lateral.](https://en.wikipedia.org/wiki/Side-channel_attack) Puesto que la comprobación de integridad rechaza los mensajes manipulados, se mitiga la amenaza de oráculo de relleno.

## <a name="guidance"></a>Guía

En primer lugar, Microsoft recomienda que los datos que tienen necesidades de confidencialidad se transmitan a través de Transport Layer Security (TLS), el sucesor de Secure Sockets Layer (SSL).

A continuación, analice la aplicación para:

- Entienda con precisión qué cifrado está realizando y qué cifrado proporcionan las plataformas y las API que está utilizando.
- Asegúrese de que cada uso en cada capa de un algoritmo de cifrado de [bloques](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)simétricos, como AES y 3DES, en modo CBC incorpore el uso de una comprobación de integridad de datos con clave secreta (una firma asimétrica, una HMAC, o para cambiar el modo de cifrado a un modo de [cifrado autenticado](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) como GCM o CCM).

Basado en la investigación actual, generalmente se cree que cuando los pasos de autenticación y cifrado se realizan de forma independiente para los modos de cifrado que no son AE, autenticar el texto cifrado (cifrar-entonces-signo) es la mejor opción general. Sin embargo, no hay una respuesta única correcta a la criptografía y esta generalización no es tan buena como el consejo dirigido de un criptógrafo profesional.

Se recomienda a las aplicaciones que no pueden cambiar su formato de mensajería pero realizar el descifrado CBC no autenticado que intenten incorporar mitigaciones como:

- Descifrar sin permitir que el descifrador para verificar o eliminar el relleno:
  - Cualquier relleno que se aplicó todavía debe eliminarse o ignorarse, está moviendo la carga a la aplicación.
  - La ventaja es que la verificación y eliminación de relleno se puede incorporar a otra lógica de verificación de datos de aplicación. Si la verificación de relleno y la verificación de datos se pueden hacer en tiempo constante, la amenaza se reduce.
  - Puesto que la interpretación del relleno cambia la longitud del mensaje percibida, todavía puede haber información de sincronización emitida por este enfoque.
- Cambie el modo de relleno de descifrado a ISO10126:
  - El relleno de descifrado ISO10126 es compatible con el relleno de cifrado PKCS7 y el relleno de cifrado ANSIX923.
  - Al cambiar el modo, se reduce el conocimiento del oráculo de relleno a 1 byte en lugar de a todo el bloque. Sin embargo, si el contenido tiene un pie de página conocido, como un elemento XML de cierre, los ataques relacionados pueden seguir atacando el resto del mensaje.
  - Esto tampoco impide la recuperación de texto no cifrado en situaciones en las que el atacante puede coaccionar el mismo texto sin formato para que se cifre varias veces con un desplazamiento de mensaje diferente.
- Puerta de la evaluación de una llamada de descifrado para amortiguar la señal de sincronización:
  - El cálculo del tiempo de espera debe tener un mínimo que exceda la cantidad máxima de tiempo que la operación de descifrado tardaría para cualquier segmento de datos que contenga relleno.
  - Los cálculos de tiempo deben realizarse de acuerdo con las instrucciones <xref:System.Environment.TickCount?displayProperty=nameWithType> de Adquisición de marcas de tiempo de [alta resolución,](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)no mediante el uso (sujeto a roll-over/overflow) o restando dos marcas de tiempo del sistema (sujeto a errores de ajuste NTP).
  - Los cálculos de tiempo deben incluir la operación de descifrado, incluidas todas las posibles excepciones en aplicaciones administradas o C++, no solo rellenadas al final.
  - Si el éxito o el error se ha determinado todavía, la puerta de sincronización necesita devolver el error cuando expira.
- Los servicios que realizan el descifrado no autenticado deben tener supervisión para detectar que ha llegado a través de una avalancha de mensajes "no válidos".
  - Tenga en cuenta que esta señal lleva tanto falsos positivos (datos legítimamente dañados) como falsos negativos (difundiendo el ataque durante un tiempo suficientemente largo como para evadir la detección).

## <a name="finding-vulnerable-code---native-applications"></a>Búsqueda de código vulnerable - aplicaciones nativas

Para programas creados en la biblioteca criptográfica de Windows: próxima generación (CNG):

- La llamada de descifrado es a [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), especificando la `BCRYPT_BLOCK_PADDING` marca.
- El identificador de clave se ha inicializado [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) llamando `BCRYPT_CHAIN_MODE_CBC`a [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) con BCRYPT_CHAINING_MODE establecido en .
  - Dado `BCRYPT_CHAIN_MODE_CBC` que es el valor predeterminado, es `BCRYPT_CHAINING_MODE`posible que el código afectado no haya asignado ningún valor para .

Para los programas creados con la API criptográfica de Windows anterior:

- La llamada de descifrado es `Final=TRUE`a [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) con .
- El identificador de clave se ha inicializado [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) llamando a `CRYPT_MODE_CBC` [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) con KP_MODE establecido en .
  - Dado `CRYPT_MODE_CBC` que es el valor predeterminado, es `KP_MODE`posible que el código afectado no haya asignado ningún valor para .

## <a name="finding-vulnerable-code---managed-applications"></a>Búsqueda de código vulnerable - aplicaciones administradas

- La llamada de descifrado <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> es <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>a los métodos o en .
  - Esto incluye los siguientes tipos derivados dentro de .NET, pero también puede incluir tipos de terceros:
    - <xref:System.Security.Cryptography.Aes>
    - <xref:System.Security.Cryptography.AesCng>
    - <xref:System.Security.Cryptography.AesCryptoServiceProvider>
    - <xref:System.Security.Cryptography.AesManaged>
    - <xref:System.Security.Cryptography.DES>
    - <xref:System.Security.Cryptography.DESCryptoServiceProvider>
    - <xref:System.Security.Cryptography.RC2>
    - <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
    - <xref:System.Security.Cryptography.Rijndael>
    - <xref:System.Security.Cryptography.RijndaelManaged>
    - <xref:System.Security.Cryptography.TripleDES>
    - <xref:System.Security.Cryptography.TripleDESCng>
    - <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>
- La <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> propiedad se <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>estableció <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>en , , o .
  - Dado <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> que es el valor predeterminado, <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> es posible que el código afectado nunca haya asignado la propiedad.
- La <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> propiedad se estableció en<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Dado <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> que es el valor predeterminado, <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> es posible que el código afectado nunca haya asignado la propiedad.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Búsqueda de código vulnerable: sintaxis de mensajes criptográficos

Un mensaje envuelto CMS no autenticado cuyo contenido cifrado utiliza el modo CBC de AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) o RC2 (1.2.840.113549.3.2) es vulnerables, así como mensajes que utilizan cualquier otro algoritmo de cifrado de bloques en modo CBC.

Aunque los cifrados de secuencia sin vulnerabilidad a esta vulnerabilidad en particular, Microsoft recomienda autenticar siempre los datos sobre la inspección del valor ContentEncryptionAlgorithm.

Para las aplicaciones administradas, se puede detectar un blob EndData de CMS como cualquier valor que se pasa a <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.

Para aplicaciones nativas, un blob EndData de CMS se puede detectar como cualquier `CMSG_ENVELOPED` valor proporcionado a un identificador de `CMSG_CTRL_DECRYPT` CMS a través de [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) cuyo [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) resultante es y/o el identificador cmS se envía más adelante una instrucción a través de [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).

## <a name="vulnerable-code-example---managed"></a>Ejemplo de código vulnerable - administrado

Este método lee una cookie y la descifra y no hay ninguna comprobación de integridad de datos visible. Por lo tanto, el contenido de una cookie que es leído por este método puede ser atacado por el usuario que la recibió, o por cualquier atacante que haya obtenido el valor de cookie cifrado.

```csharp
private byte[] DecryptCookie(string cookieName)
{
    HttpCookie cookie = Request.Cookies[cookieName];

    if (cookie == null)
    {
        return null;
    }

    using (ICryptoTransform decryptor = _aes.CreateDecryptor())
    using (MemoryStream memoryStream = new MemoryStream())
    using (CryptoStream cryptoStream =
        new CryptoStream(memoryStream, decryptor, CryptoStreamMode.Write))
    {
        byte[] readCookie = Convert.FromBase64String(cookie.Value);
        cryptoStream.Write(readCookie, 0, readCookie.Length);
        cryptoStream.FlushFinalBlock();
        return memoryStream.ToArray();
    }
}
```

## <a name="example-code-following-recommended-practices---managed"></a>Ejemplo de código que sigue a las prácticas recomendadas - administrado

El siguiente código de ejemplo utiliza un formato de mensaje no estándar de

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

donde `cipher_algorithm_id` los `hmac_algorithm_id` identificadores de algoritmo y los identificadores de algoritmo son representaciones locales de la aplicación (no estándar) de esos algoritmos. Estos identificadores pueden tener sentido en otras partes del protocolo de mensajería existente en lugar de como una secuencia de bytes concatenada desnuda.

Este ejemplo también utiliza una sola clave maestra para derivar una clave de cifrado y una clave HMAC. Esto se proporciona tanto como una comodidad para convertir una aplicación con clave escote en una aplicación de doble clave, y para fomentar mantener las dos claves como valores diferentes. Además, garantiza que la clave HMAC y la clave de cifrado no pueden salir de la sincronización.

Este ejemplo no acepta <xref:System.IO.Stream> un para cifrado o descifrado. El formato de datos actual dificulta el cifrado de una pasada porque el `hmac_tag` valor precede al texto cifrado. Sin embargo, este formato se eligió porque mantiene todos los elementos de tamaño fijo al principio para mantener el analizador más simple. Con este formato de datos, el descifrado de una sola pasada es posible, aunque se advierte a un implementador que llame a GetHashAndReset y compruebe el resultado antes de llamar a TransformFinalBlock. Si el cifrado de streaming es importante, puede ser necesario un modo AE diferente.

```csharp
// ==++==
//
//   Copyright (c) Microsoft Corporation.  All rights reserved.
//
//   Shared under the terms of the Microsoft Public License,
//   https://opensource.org/licenses/MS-PL
//
// ==--==

using System;
using System.Diagnostics;
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;

namespace Microsoft.Examples.Cryptography
{
    public enum AeCipher : byte
    {
        Unknown,
        Aes256CbcPkcs7,
    }

    public enum AeMac : byte
    {
        Unknown,
        HMACSHA256,
        HMACSHA384,
    }

    /// <summary>
    /// Provides extension methods to make HashAlgorithm look like .NET Core's
    /// IncrementalHash
    /// </summary>
    internal static class IncrementalHashExtensions
    {
        public static void AppendData(this HashAlgorithm hash, byte[] data)
        {
            hash.TransformBlock(data, 0, data.Length, null, 0);
        }

        public static void AppendData(
            this HashAlgorithm hash,
            byte[] data,
            int offset,
            int length)
        {
            hash.TransformBlock(data, offset, length, null, 0);
        }

        public static byte[] GetHashAndReset(this HashAlgorithm hash)
        {
            hash.TransformFinalBlock(Array.Empty<byte>(), 0, 0);
            return hash.Hash;
        }
    }

    public static partial class AuthenticatedEncryption
    {
        /// <summary>
        /// Use <paramref name="masterKey"/> to derive two keys (one cipher, one HMAC)
        /// to provide authenticated encryption for <paramref name="message"/>.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="message">The message to encrypt</param>
        /// <returns>
        /// A concatenation of
        /// [cipher algorithm+chainmode+padding][mac algorithm][authtag][IV][ciphertext],
        /// suitable to be passed to <see cref="Decrypt"/>.
        /// </returns>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or bigger) value generated
        /// by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>.
        /// This implementation chooses to block deficient inputs by length, but does not
        /// make any attempt at discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase)
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Encrypt(byte[] masterKey, byte[] message)
        {
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (message == null)
                throw new ArgumentNullException(nameof(message));

            // First, choose an encryption scheme.
            AeCipher aeCipher = AeCipher.Aes256CbcPkcs7;

            // Second, choose an authentication (message integrity) scheme.
            //
            // In this example we use the master key length to change from HMACSHA256 to
            // HMACSHA384, but that is completely arbitrary. This mostly represents a
            // "cryptographic needs change over time" scenario.
            AeMac aeMac = masterKey.Length < 48 ? AeMac.HMACSHA256 : AeMac.HMACSHA384;

            // It's good to be able to identify what choices were made when a message was
            // encrypted, so that the message can later be decrypted. This allows for
            // future versions to add support for new encryption schemes, but still be
            // able to read old data. A practice known as "cryptographic agility".
            //
            // This is similar in practice to PKCS#7 messaging, but this uses a
            // private-scoped byte rather than a public-scoped Object IDentifier (OID).
            // Please note that the scheme in this example adheres to no particular
            // standard, and is unlikely to survive to a more complete implementation in
            // the .NET Framework.
            //
            // You may be well-served by prepending a version number byte to this
            // message, but may want to avoid the value 0x30 (the leading byte value for
            // DER-encoded structures such as X.509 certificates and PKCS#7 messages).
            byte[] algorithmChoices = { (byte)aeCipher, (byte)aeMac };
            byte[] iv;
            byte[] cipherText;
            byte[] tag;

            // Using our algorithm choices, open an HMAC (as an authentication tag
            // generator) and a SymmetricAlgorithm which use different keys each derived
            // from the same master key.
            //
            // A custom implementation may very well have distinctly managed secret keys
            // for the MAC and cipher, this example merely demonstrates the master to
            // derived key methodology to encourage key separation from the MAC and
            // cipher keys.
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
                using (ICryptoTransform encryptor = cipher.CreateEncryptor())
                {
                    // Since no IV was provided, a random one has been generated
                    // during the call to CreateEncryptor.
                    //
                    // But note that it only does the auto-generation once. If the cipher
                    // object were used again, a call to GenerateIV would have been
                    // required.
                    iv = cipher.IV;

                    cipherText = Transform(encryptor, message, 0, message.Length);
                }

                // The IV and ciphertest both need to be included in the MAC to prevent
                // tampering.
                //
                // By including the algorithm identifiers, we have technically moved from
                // simple Authenticated Encryption (AE) to Authenticated Encryption with
                // Additional Data (AEAD). By including the algorithm identifiers in the
                // MAC, it becomes harder for an attacker to change them as an attempt to
                // perform a downgrade attack.
                //
                // If you've added a data format version field, it can also be included
                // in the MAC to further inhibit an attacker's options for confusing the
                // data processor into believing the tampered message is valid.
                tagGenerator.AppendData(algorithmChoices);
                tagGenerator.AppendData(iv);
                tagGenerator.AppendData(cipherText);
                tag = tagGenerator.GetHashAndReset();
            }

            // Build the final result as the concatenation of everything except the keys.
            int totalLength =
                algorithmChoices.Length +
                tag.Length +
                iv.Length +
                cipherText.Length;

            byte[] output = new byte[totalLength];
            int outputOffset = 0;

            Append(algorithmChoices, output, ref outputOffset);
            Append(tag, output, ref outputOffset);
            Append(iv, output, ref outputOffset);
            Append(cipherText, output, ref outputOffset);

            Debug.Assert(outputOffset == output.Length);
            return output;
        }

        /// <summary>
        /// Reads a message produced by <see cref="Encrypt"/> after verifying it hasn't
        /// been tampered with.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="cipherText">
        /// The output of <see cref="Encrypt"/>: a concatenation of a cipher ID, mac ID,
        /// authTag, IV, and cipherText.
        /// </param>
        /// <returns>The decrypted content.</returns>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="masterKey"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="cipherText"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="CryptographicException">
        /// <paramref name="cipherText"/> identifies unknown algorithms, is not long
        /// enough, fails a data integrity check, or fails to decrypt.
        /// </exception>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or larger) value
        /// generated by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>. This implementation chooses to
        /// block deficient inputs by length, but doesn't make any attempt at
        /// discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase),
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Decrypt(byte[] masterKey, byte[] cipherText)
        {
            // This example continues the .NET practice of throwing exceptions for
            // failures. If you consider message tampering to be normal (and thus
            // "not exceptional") behavior, you may like the signature
            // bool Decrypt(byte[] messageKey, byte[] cipherText, out byte[] message)
            // better.
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (cipherText == null)
                throw new ArgumentNullException(nameof(cipherText));

            // The format of this message is assumed to be public, so there's no harm in
            // saying ahead of time that the message makes no sense.
            if (cipherText.Length < 2)
            {
                throw new CryptographicException();
            }

            // Use the message algorithm headers to determine what cipher algorithm and
            // MAC algorithm are going to be used. Since the same Key Derivation
            // Functions (KDFs) are being used in Decrypt as Encrypt, the keys are also
            // the same.
            AeCipher aeCipher = (AeCipher)cipherText[0];
            AeMac aeMac = (AeMac)cipherText[1];

            using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                int blockSizeInBytes = cipher.BlockSize / 8;
                int tagSizeInBytes = tagGenerator.HashSize / 8;
                int headerSizeInBytes = 2;
                int tagOffset = headerSizeInBytes;
                int ivOffset = tagOffset + tagSizeInBytes;
                int cipherTextOffset = ivOffset + blockSizeInBytes;
                int cipherTextLength = cipherText.Length - cipherTextOffset;
                int minLen = cipherTextOffset + blockSizeInBytes;

                // Again, the minimum length is still assumed to be public knowledge,
                // nothing has leaked out yet. The minimum length couldn't just be calculated
                // without reading the header.
                if (cipherText.Length < minLen)
                {
                    throw new CryptographicException();
                }

                // It's very important that the MAC be calculated and verified before
                // proceeding to decrypt the ciphertext, as this prevents any sort of
                // information leaking out to an attacker.
                //
                // Don't include the tag in the calculation, though.

                // First, everything before the tag (the cipher and MAC algorithm ids)
                tagGenerator.AppendData(cipherText, 0, tagOffset);

                // Skip the data before the tag and the tag, then read everything that
                // remains.
                tagGenerator.AppendData(
                    cipherText,
                    tagOffset + tagSizeInBytes,
                    cipherText.Length - tagSizeInBytes - tagOffset);

                byte[] generatedTag = tagGenerator.GetHashAndReset();

                // The time it took to get to this point has so far been a function only
                // of the length of the data, or of non-encrypted values (e.g. it could
                // take longer to prepare the *key* for the HMACSHA384 MAC than the
                // HMACSHA256 MAC, but the algorithm choice wasn't a secret).
                //
                // If the verification of the authentication tag aborts as soon as a
                // difference is found in the byte arrays then your program may be
                // acting as a timing oracle which helps an attacker to brute-force the
                // right answer for the MAC. So, it's very important that every possible
                // "no" (2^256-1 of them for HMACSHA256) be evaluated in as close to the
                // same amount of time as possible. For this, we call CryptographicEquals
                if (!CryptographicEquals(
                    generatedTag,
                    0,
                    cipherText,
                    tagOffset,
                    tagSizeInBytes))
                {
                    // Assuming every tampered message (of the same length) took the same
                    // amount of time to process, we can now safely say
                    // "this data makes no sense" without giving anything away.
                    throw new CryptographicException();
                }

                // Restore the IV into the symmetricAlgorithm instance.
                byte[] iv = new byte[blockSizeInBytes];
                Buffer.BlockCopy(cipherText, ivOffset, iv, 0, iv.Length);
                cipher.IV = iv;

                using (ICryptoTransform decryptor = cipher.CreateDecryptor())
                {
                    return Transform(
                        decryptor,
                        cipherText,
                        cipherTextOffset,
                        cipherTextLength);
                }
            }
        }

        private static byte[] Transform(
            ICryptoTransform transform,
            byte[] input,
            int inputOffset,
            int inputLength)
        {
            // Many of the implementations of ICryptoTransform report true for
            // CanTransformMultipleBlocks, and when the entire message is available in
            // one shot this saves on the allocation of the CryptoStream and the
            // intermediate structures it needs to properly chunk the message into blocks
            // (since the underlying stream won't always return the number of bytes
            // needed).
            if (transform.CanTransformMultipleBlocks)
            {
                return transform.TransformFinalBlock(input, inputOffset, inputLength);
            }

            // If our transform couldn't do multiple blocks at once, let CryptoStream
            // handle the chunking.
            using (MemoryStream messageStream = new MemoryStream())
            using (CryptoStream cryptoStream =
                new CryptoStream(messageStream, transform, CryptoStreamMode.Write))
            {
                cryptoStream.Write(input, inputOffset, inputLength);
                cryptoStream.FlushFinalBlock();
                return messageStream.ToArray();
            }
        }

        /// <summary>
        /// Open a properly configured <see cref="SymmetricAlgorithm"/> conforming to the
        /// scheme identified by <paramref name="aeCipher"/>.
        /// </summary>
        /// <param name="aeCipher">The cipher mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// A SymmetricAlgorithm object with the right key, cipher mode, and padding
        /// mode; or <c>null</c> on unknown algorithms.
        /// </returns>
        private static SymmetricAlgorithm GetCipher(AeCipher aeCipher, byte[] masterKey)
        {
            SymmetricAlgorithm symmetricAlgorithm;

            switch (aeCipher)
            {
                case AeCipher.Aes256CbcPkcs7:
                    symmetricAlgorithm = Aes.Create();
                    // While 256-bit, CBC, and PKCS7 are all the default values for these
                    // properties, being explicit helps comprehension more than it hurts
                    // performance.
                    symmetricAlgorithm.KeySize = 256;
                    symmetricAlgorithm.Mode = CipherMode.CBC;
                    symmetricAlgorithm.Padding = PaddingMode.PKCS7;
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            //
            // Since none of the symmetric encryption algorithms currently in .NET
            // support key sizes greater than 256-bit, we can use HMACSHA256 with
            // NIST SP 800-108 5.1 (Counter Mode KDF) to derive a value that is
            // no smaller than the key size, then Array.Resize to trim it down as
            // needed.

            using (HMAC hmac = new HMACSHA256(masterKey))
            {
                // i=1, Label=ASCII(cipher)
                byte[] cipherKey = hmac.ComputeHash(
                    new byte[] { 1, 99, 105, 112, 104, 101, 114 });

                // Resize the array to the desired keysize. KeySize is in bits,
                // and Array.Resize wants the length in bytes.
                Array.Resize(ref cipherKey, symmetricAlgorithm.KeySize / 8);

                symmetricAlgorithm.Key = cipherKey;
            }

            return symmetricAlgorithm;
        }

        /// <summary>
        /// Open a properly configured <see cref="HMAC"/> conforming to the scheme
        /// identified by <paramref name="aeMac"/>.
        /// </summary>
        /// <param name="aeMac">The message authentication mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// An HMAC object with the proper key, or <c>null</c> on unknown algorithms.
        /// </returns>
        private static HMAC GetMac(AeMac aeMac, byte[] masterKey)
        {
            HMAC hmac;

            switch (aeMac)
            {
                case AeMac.HMACSHA256:
                    hmac = new HMACSHA256();
                    break;
                case AeMac.HMACSHA384:
                    hmac = new HMACSHA384();
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            // Since the output size of the HMAC is the same as the ideal key size for
            // the HMAC, we can use the master key over a fixed input once to perform
            // NIST SP 800-108 5.1 (Counter Mode KDF):
            hmac.Key = masterKey;

            // i=1, Context=ASCII(MAC)
            byte[] newKey = hmac.ComputeHash(new byte[] { 1, 77, 65, 67 });

            hmac.Key = newKey;
            return hmac;
        }

        // A simple helper method to ensure that the offset (writePos) always moves
        // forward with new data.
        private static void Append(byte[] newData, byte[] combinedData, ref int writePos)
        {
            Buffer.BlockCopy(newData, 0, combinedData, writePos, newData.Length);
            writePos += newData.Length;
        }

        /// <summary>
        /// Compare the contents of two arrays in an amount of time which is only
        /// dependent on <paramref name="length"/>.
        /// </summary>
        /// <param name="a">An array to compare to <paramref name="b"/>.</param>
        /// <param name="aOffset">
        /// The starting position within <paramref name="a"/> for comparison.
        /// </param>
        /// <param name="b">An array to compare to <paramref name="a"/>.</param>
        /// <param name="bOffset">
        /// The starting position within <paramref name="b"/> for comparison.
        /// </param>
        /// <param name="length">
        /// The number of bytes to compare between <paramref name="a"/> and
        /// <paramref name="b"/>.</param>
        /// <returns>
        /// <c>true</c> if both <paramref name="a"/> and <paramref name="b"/> have
        /// sufficient length for the comparison and all of the applicable values are the
        /// same in both arrays; <c>false</c> otherwise.
        /// </returns>
        /// <remarks>
        /// An "insufficient data" <c>false</c> response can happen early, but otherwise
        /// a <c>true</c> or <c>false</c> response take the same amount of time.
        /// </remarks>
        [MethodImpl(MethodImplOptions.NoInlining | MethodImplOptions.NoOptimization)]
        private static bool CryptographicEquals(
            byte[] a,
            int aOffset,
            byte[] b,
            int bOffset,
            int length)
        {
            Debug.Assert(a != null);
            Debug.Assert(b != null);
            Debug.Assert(length >= 0);

            int result = 0;

            if (a.Length - aOffset < length || b.Length - bOffset < length)
            {
                return false;
            }

            unchecked
            {
                for (int i = 0; i < length; i++)
                {
                    // Bitwise-OR of subtraction has been found to have the most
                    // stable execution time.
                    //
                    // This cannot overflow because bytes are 1 byte in length, and
                    // result is 4 bytes.
                    // The OR propagates all set bytes, so the differences are only
                    // present in the lowest byte.
                    result = result | (a[i + aOffset] - b[i + bOffset]);
                }
            }

            return result == 0;
        }
    }
}
```
