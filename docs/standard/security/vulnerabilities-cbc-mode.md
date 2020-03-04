---
title: Vulnerabilidad de descifrado de CBC
description: Obtenga información acerca de cómo detectar y mitigar las vulnerabilidades de tiempo con el descifrado simétrico del modo de encadenamiento de bloques de cifrado (CBC) mediante el relleno.
ms.date: 06/12/2018
author: blowdart
ms.openlocfilehash: 4616ef9015b47ff232a17f058c7a0f1449f42e81
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159967"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Vulnerabilidades de temporalización con descifrado simétrico en modo CBC al usar el relleno

Microsoft considera que ya no es seguro descifrar los datos cifrados con el modo de encadenamiento de bloques de cifrado (CBC) del cifrado simétrico cuando se ha aplicado el relleno comprobable sin asegurar primero la integridad del texto cifrado, excepto en el caso de que sea muy específico circunstancias. Este juicio se basa en la investigación criptográfica conocida actualmente.

## <a name="introduction"></a>Introducción

Un ataque de rellenado de Oracle es un tipo de ataque contra datos cifrados que permite al atacante descifrar el contenido de los datos, sin conocer la clave.

Un Oracle hace referencia a una "información" que proporciona a un atacante información sobre si la acción que se está ejecutando es correcta o no. Imagine que juega un panel o un juego de cartas con un elemento secundario. Cuando su cara se enciende con una gran sonrisa porque considera que está a punto de hacer un buen movimiento, es un Oracle. Usted, como oponente, puede usar este Oracle para planear el siguiente paso correctamente.

El relleno es un término criptográfico específico. Algunos cifrados, que son los algoritmos que se usan para cifrar los datos, funcionan en bloques de datos donde cada bloque tiene un tamaño fijo. Si los datos que quiere cifrar no son el tamaño correcto para rellenar los bloques, los datos se rellenan hasta que lo hace. Muchas formas de relleno requieren que el relleno esté siempre presente, incluso si la entrada original era del tamaño correcto. Esto permite que el relleno se quite siempre de forma segura tras el descifrado.

Al reunir las dos cosas, una implementación de software con un relleno de Oracle revela si los datos descifrados tienen un relleno válido. Oracle podría ser algo tan sencillo como devolver un valor que diga "relleno no válido" o algo más complicado, como tomar un tiempo muy diferente para procesar un bloque válido en lugar de un bloque no válido.

Los cifrados basados en bloques tienen otra propiedad, denominada modo, que determina la relación de los datos en el primer bloque con los datos del segundo bloque, etc. Uno de los modos más usados es CBC. CBC introduce un bloque aleatorio inicial, conocido como el vector de inicialización (IV), y combina el bloque anterior con el resultado de cifrado estático para que sea tal que el cifrado del mismo mensaje con la misma clave no siempre genere la misma salida cifrada.

Un atacante puede usar un relleno de Oracle, en combinación con cómo se estructuran los datos CBC, para enviar mensajes ligeramente modificados al código que expone el Oracle y seguir enviando datos hasta que Oracle les indique que los datos son correctos. A partir de esta respuesta, el atacante puede descifrar el byte de mensaje por byte.

Las redes modernas de equipos son de una calidad tan alta que un atacante puede detectar diferencias muy pequeñas (menos de 0,1 MS) en el tiempo de ejecución de los sistemas remotos. Las aplicaciones que suponen que un descifrado correcto solo se puede producir cuando los datos no se han alterado pueden ser vulnerables a ataques de herramientas diseñadas para observar diferencias en el descifrado correcto e incorrecto. Aunque esta diferencia de tiempo puede ser más importante en algunos lenguajes o bibliotecas que otros, ahora se considera que se trata de una amenaza práctica para todos los lenguajes y bibliotecas cuando se tiene en cuenta la respuesta de la aplicación a los errores.

Este ataque se basa en la capacidad de cambiar los datos cifrados y probar el resultado con Oracle. La única manera de mitigar completamente el ataque es detectar los cambios en los datos cifrados y rechazar la realización de acciones en él. La manera estándar de hacerlo es crear una firma para los datos y validar esa firma antes de que se realicen las operaciones. La firma debe ser comprobable, no la puede crear el atacante; de lo contrario, cambiaría los datos cifrados y, a continuación, calcularía una nueva firma basada en los datos modificados. Un tipo común de la firma adecuada se conoce como código de autenticación de mensajes hash con clave (HMAC). Un HMAC difiere de una suma de comprobación en que toma una clave secreta, conocida solo por la persona que produce HMAC y a la persona que la valida. Sin la posesión de la clave, no se puede producir un HMAC correcto. Cuando reciba los datos, deberá tomar los datos cifrados, calcular de forma independiente el HMAC con la clave secreta y el recurso compartido de remitente y, a continuación, comparar el HMAC que envió con el que ha calculado. Esta comparación debe ser una hora constante; de lo contrario, se ha agregado otra Oracle que se puede detectar, lo que permite un tipo de ataque diferente.

En Resumen, para usar cifrados de bloques CBC rellenos de forma segura, debe combinarlos con un HMAC (u otra comprobación de integridad de los datos) que valide mediante una comparación de hora constante antes de intentar descifrar los datos. Dado que todos los mensajes modificados tardan la misma cantidad de tiempo en generar una respuesta, se impide el ataque.

## <a name="who-is-vulnerable"></a>Quién es vulnerable

Esta vulnerabilidad se aplica a las aplicaciones administradas y nativas que realizan su propio cifrado y descifrado. Esto incluye, por ejemplo:

- Aplicación que cifra una cookie para el descifrado posterior en el servidor.
- Aplicación de base de datos que permite a los usuarios insertar datos en una tabla cuyas columnas se descifran más adelante.
- Una aplicación de transferencia de datos que se basa en el cifrado mediante una clave compartida para proteger los datos en tránsito.
- Aplicación que cifra y descifra los mensajes "dentro" del túnel TLS.

Tenga en cuenta que el uso de TLS por sí solo puede no protegerle en estos escenarios.

Una aplicación vulnerable:

- Descifra los datos mediante el modo de cifrado CBC con un modo de relleno comprobable, como PKCS # 7 o ANSI X. 923.
- Realiza el descifrado sin tener que realizar una comprobación de integridad de datos (a través de un MAC o una firma digital asimétrica).

Esto también se aplica a las aplicaciones compiladas sobre abstracciones en la parte superior de estos primitivos, como la estructura EnvelopedData de la sintaxis de mensajes de cifrado (PKCS # 7/CMS).

## <a name="related-areas-of-concern"></a>Áreas relacionadas de preocupación

La investigación ha llevado a Microsoft a preocuparse por los mensajes CBC que se rellenan con el relleno ISO 10126-equivalente cuando el mensaje tiene una estructura de pie de página bien conocida o predecible. Por ejemplo, el contenido está preparado bajo las reglas de la recomendación de cifrado y la recomendación de procesamiento de XML de W3C (xmlenc, EncryptedXml). Aunque la guía del W3C para firmar el mensaje, el cifrado se consideró adecuado en el momento en que Microsoft ahora recomienda realizar siempre el cifrado y luego el signo.

Los desarrolladores de aplicaciones siempre deben ser conscientes de comprobar la aplicabilidad de una clave de firma asimétrica, ya que no hay ninguna relación de confianza inherente entre una clave asimétrica y un mensaje arbitrario.

## <a name="details"></a>Detalles

Históricamente, se ha dado el consenso de que es importante cifrar y autenticar datos importantes mediante el uso de medios como las firmas HMAC o RSA. Sin embargo, se han realizado instrucciones menos claras sobre cómo secuenciar las operaciones de cifrado y autenticación. Debido a la vulnerabilidad que se detalla en este artículo, la guía de Microsoft es ahora para usar siempre el paradigma "cifrar y luego firmar". Es decir, primero debe cifrar los datos mediante una clave simétrica y, a continuación, calcular una firma MAC o asimétrica a través del texto cifrado (datos cifrados). Al descifrar los datos, realice la ejecución inversa. En primer lugar, confirme el MAC o la firma del texto cifrado y, a continuación, descifre.

Se sabe que existe una clase de vulnerabilidades conocidas como "los ataques de rellenado de Oracle" durante más de 10 años. Estas vulnerabilidades permiten que un atacante descifre los datos cifrados mediante algoritmos de bloques simétricos, como AES y 3DES, y no use más de 4096 intentos por bloque de datos. Estas vulnerabilidades hacen uso del hecho de que los cifrados de bloques se usan con mayor frecuencia con datos de relleno comprobables al final. Se encontró que, si un atacante puede alterar el texto cifrado y averiguar si la manipulación produjo un error en el formato del relleno al final, el atacante puede descifrar los datos.

Inicialmente, los ataques prácticos se basaban en servicios que devolverían códigos de error diferentes en función de si el relleno era válido, como la vulnerabilidad ASP.NET [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070). Sin embargo, ahora Microsoft considera que es práctico realizar ataques similares usando solo las diferencias de tiempo entre el procesamiento de relleno válido y no válido.

Siempre que el esquema de cifrado emplee una firma y que la comprobación de la firma se realice con un tiempo de ejecución fijo para una longitud de datos determinada (con independencia del contenido), la integridad de los datos se puede comprobar sin emitir ninguna información a un atacante a través de un [canal secundario](https://en.wikipedia.org/wiki/Side-channel_attack). Como la comprobación de la integridad rechaza los mensajes alterados, se mitiga la amenaza de rellenado de Oracle.

## <a name="guidance"></a>Orientación

En primer lugar, Microsoft recomienda que todos los datos que tengan confidencialidad se transmitan a través de la seguridad de la capa de transporte (TLS), el sucesor de Capa de sockets seguros (SSL).

A continuación, analice la aplicación para:

- Comprenda exactamente el cifrado que está realizando y el cifrado que proporcionan las plataformas y las API que está usando.
- Asegúrese de que cada uso en cada capa de un [algoritmo de cifrado de bloques](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)simétricos, como AES y 3DES, en modo CBC incorpore el uso de una comprobación de integridad de datos con clave secreta (una firma asimétrica, un HMAC, o para cambiar el modo de cifrado a un modo de [cifrado autenticado](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) como GCM o CCM).

En función de la investigación actual, se considera generalmente que cuando los pasos de cifrado y autenticación se realizan de forma independiente para los modos de cifrado no AE, la mejor opción general es autenticar el texto cifrado (cifrar y luego firmar). Sin embargo, no hay ninguna respuesta de un solo tamaño que se ajuste a la criptografía y esta generalización no es tan buena como el Consejo dirigido de un cifrado profesional.

Se recomienda que las aplicaciones que no pueden cambiar su formato de mensajería, pero que realizan descifrado CBC no autenticado intenten incorporar mitigaciones, como:

- Descifrar sin permitir que el descifrador Compruebe o quite el relleno:
  - Cualquier relleno aplicado todavía debe quitarse u omitirse, se mueve la carga a la aplicación.
  - La ventaja es que la comprobación y la eliminación del relleno se pueden incorporar en otra lógica de comprobación de datos de la aplicación. Si la comprobación de relleno y la comprobación de datos se pueden realizar en tiempo constante, se reduce la amenaza.
  - Dado que la interpretación del relleno cambia la longitud del mensaje percibido, es posible que todavía se emita información de tiempo de este enfoque.
- Cambie el modo de relleno de descifrado a ISO10126:
  - El relleno de descifrado de ISO10126 es compatible con el relleno de cifrado PKCS7 y el relleno de cifrado ANSIX923.
  - Al cambiar el modo, se reduce el relleno de los conocimientos de Oracle a 1 byte en lugar de todo el bloque. Sin embargo, si el contenido tiene un pie de página conocido, como un elemento XML de cierre, los ataques relacionados pueden seguir atacando el resto del mensaje.
  - Esto tampoco impide la recuperación de texto sin formato en situaciones en las que el atacante puede forzar el mismo texto no cifrado para que se cifre varias veces con un desplazamiento de mensaje diferente.
- Gate la evaluación de una llamada de descifrado para amortiguar la señal de temporización:
  - El cálculo del tiempo de espera debe tener un mínimo superior al máximo de tiempo que tardará la operación de descifrado en cualquier segmento de datos que contenga relleno.
  - Los cálculos de tiempo deben realizarse de acuerdo con las instrucciones de [adquisición de marcas de tiempo de alta resolución](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), no mediante el uso de <xref:System.Environment.TickCount?displayProperty=nameWithType> (sujeto a reversión/desbordamiento) o restar dos marcas de tiempo del sistema (sujetas a errores de ajuste de NTP).
  - Los cálculos de tiempo deben ser inclusivos de la operación de descifrado, incluidas todas las C++ excepciones potenciales en las aplicaciones o administradas, no solo rellenar hasta el final.
  - Si el éxito o el error se ha determinado todavía, la puerta de tiempo debe devolver un error cuando expire.
- Los servicios que realizan el descifrado no autenticado deben tener supervisión para detectar que se ha producido un desbordamiento de mensajes "no válidos".
  - Tenga en cuenta que esta señal contiene falsos positivos (datos dañados de forma legítima) y falsos negativos (repartir el ataque durante un tiempo suficientemente largo para eludir la detección).

## <a name="finding-vulnerable-code---native-applications"></a>Búsqueda de aplicaciones nativas de código vulnerable

En el caso de los programas creados en la biblioteca Cryptography: Next Generation (CNG) de Windows:

- La llamada de descifrado es [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), especificando la marca de `BCRYPT_BLOCK_PADDING`.
- El identificador de clave se ha inicializado mediante una llamada a [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) con [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) establecida en `BCRYPT_CHAIN_MODE_CBC`.
  - Como `BCRYPT_CHAIN_MODE_CBC` es el valor predeterminado, es posible que el código afectado no haya asignado ningún valor para `BCRYPT_CHAINING_MODE`.

Para programas creados en la antigua API criptográfica de Windows:

- La llamada de descifrado es [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) con `Final=TRUE`.
- El identificador de clave se ha inicializado mediante una llamada a [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) con [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) establecida en `CRYPT_MODE_CBC`.
  - Como `CRYPT_MODE_CBC` es el valor predeterminado, es posible que el código afectado no haya asignado ningún valor para `KP_MODE`.

## <a name="finding-vulnerable-code---managed-applications"></a>Búsqueda de aplicaciones administradas por código vulnerables

- La llamada de descifrado es a los métodos <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> o <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> de <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.
  - Esto incluye los siguientes tipos derivados en .NET, pero también puede incluir tipos de terceros:
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
- La propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> se estableció en <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>o <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.
  - Como <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> es el valor predeterminado, es posible que el código afectado nunca haya asignado la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>.
- La propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> se estableció en <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Como <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> es el valor predeterminado, es posible que el código afectado nunca haya asignado la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Búsqueda de código vulnerable: sintaxis de mensajes criptográficos

Un mensaje CMS EnvelopedData no autenticado cuyo contenido cifrado usa el modo CBC de AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) o RC2 (1.2.840.113549.3.2) es vulnerable, así como los mensajes que utilizan cualquier otro algoritmo de cifrado de bloques en el modo CBC.

Aunque los cifrados de secuencias no son susceptibles a esta vulnerabilidad determinada, Microsoft recomienda siempre autenticar los datos a través de la inspección del valor de ContentEncryptionAlgorithm.

En el caso de las aplicaciones administradas, se puede detectar un BLOB EnvelopedData de CMS como cualquier valor que se pase a <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.

En el caso de las aplicaciones nativas, se puede detectar un BLOB EnvelopedData de CMS como cualquier valor proporcionado a un identificador CMS a través de [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) cuyo [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) resultante sea `CMSG_ENVELOPED` y, posteriormente, el controlador CMS enviará una instrucción `CMSG_CTRL_DECRYPT` a través de [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).

## <a name="vulnerable-code-example---managed"></a>Ejemplo de código vulnerable: administrado

Este método lee una cookie y la descifra y no se ve ninguna comprobación de integridad de los datos. Por lo tanto, el usuario que lo recibió o cualquier atacante que haya obtenido el valor de cookie cifrado puede atacar el contenido de una cookie leída por este método.

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

## <a name="example-code-following-recommended-practices---managed"></a>Código de ejemplo con procedimientos recomendados: administrado

En el código de ejemplo siguiente se usa un formato de mensaje no estándar.

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

donde los identificadores de algoritmo de `cipher_algorithm_id` y `hmac_algorithm_id` son representaciones locales de la aplicación (no estándar) de esos algoritmos. Estos identificadores pueden tener sentido en otras partes del Protocolo de mensajería existente, en lugar de como una bytestream concatenada.

En este ejemplo también se usa una única clave maestra para derivar una clave de cifrado y una clave HMAC. Esto se proporciona tanto por comodidad para convertir una aplicación con una clave única en una aplicación con doble clave como para alentar el mantenimiento de las dos claves como valores diferentes. Además, garantiza que la clave HMAC y la clave de cifrado no se pueden obtener de la sincronización.

En este ejemplo no se acepta un <xref:System.IO.Stream> para el cifrado o el descifrado. El formato de datos actual dificulta el cifrado de un paso porque el valor de `hmac_tag` precede al texto cifrado. Sin embargo, se ha elegido este formato porque mantiene todos los elementos de tamaño fijo al principio para que el analizador sea más sencillo. Con este formato de datos, es posible descifrar un paso, aunque se puede llamar a un implementador para que llame a GetHashAndReset y compruebe el resultado antes de llamar a TransformFinalBlock. Si el cifrado de streaming es importante, es posible que se requiera un modo AE diferente.

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
