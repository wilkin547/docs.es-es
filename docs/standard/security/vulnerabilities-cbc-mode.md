---
title: Vulnerabilidad de descifrado de CBC
description: Obtenga información acerca de cómo detectar y mitigar las vulnerabilidades de tiempo con el descifrado simétrico del modo de encadenamiento de bloques de cifrado (CBC) mediante el relleno.
ms.date: 07/15/2020
author: blowdart
ms.openlocfilehash: e9bbeeefa2ef6ef90f3a752742667d30aec0a3da
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557208"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="2c8ed-103">Vulnerabilidades de temporalización con descifrado simétrico en modo CBC al usar el relleno</span><span class="sxs-lookup"><span data-stu-id="2c8ed-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="2c8ed-104">Microsoft considera que ya no es seguro descifrar los datos cifrados con el modo de encadenamiento de bloques de cifrado (CBC) del cifrado simétrico cuando se ha aplicado el relleno comprobable sin asegurar primero la integridad del texto cifrado, excepto en circunstancias muy específicas.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="2c8ed-105">Este juicio se basa en la investigación criptográfica conocida actualmente.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-105">This judgement is based on currently known cryptographic research.</span></span>

## <a name="introduction"></a><span data-ttu-id="2c8ed-106">Introducción</span><span class="sxs-lookup"><span data-stu-id="2c8ed-106">Introduction</span></span>

<span data-ttu-id="2c8ed-107">Un ataque de rellenado de Oracle es un tipo de ataque contra datos cifrados que permite al atacante descifrar el contenido de los datos, sin conocer la clave.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="2c8ed-108">Un Oracle hace referencia a una "información" que proporciona a un atacante información sobre si la acción que se está ejecutando es correcta o no.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="2c8ed-109">Imagine que juega un panel o un juego de cartas con un elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="2c8ed-110">Cuando su cara se enciende con una gran sonrisa porque piensan que están a punto de hacer un buen movimiento, eso es un Oracle.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-110">When their face lights up with a big smile because they think they're about to make a good move, that's an oracle.</span></span> <span data-ttu-id="2c8ed-111">Usted, como oponente, puede usar este Oracle para planear el siguiente paso correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="2c8ed-112">El relleno es un término criptográfico específico.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="2c8ed-113">Algunos cifrados, que son los algoritmos que se usan para cifrar los datos, funcionan en bloques de datos donde cada bloque tiene un tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="2c8ed-114">Si los datos que quiere cifrar no son el tamaño correcto para rellenar los bloques, los datos se rellenan hasta que lo hace.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="2c8ed-115">Muchas formas de relleno requieren que el relleno esté siempre presente, incluso si la entrada original era del tamaño correcto.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="2c8ed-116">Esto permite que el relleno se quite siempre de forma segura tras el descifrado.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="2c8ed-117">Al reunir las dos cosas, una implementación de software con un relleno de Oracle revela si los datos descifrados tienen un relleno válido.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="2c8ed-118">Oracle podría ser algo tan sencillo como devolver un valor que diga "relleno no válido" o algo más complicado, como tomar un tiempo muy diferente para procesar un bloque válido en lugar de un bloque no válido.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="2c8ed-119">Los cifrados basados en bloques tienen otra propiedad, denominada modo, que determina la relación de los datos en el primer bloque con los datos del segundo bloque, etc.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="2c8ed-120">Uno de los modos más usados es CBC.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="2c8ed-121">CBC introduce un bloque aleatorio inicial, conocido como el vector de inicialización (IV), y combina el bloque anterior con el resultado de cifrado estático para que sea tal que el cifrado del mismo mensaje con la misma clave no siempre genere la misma salida cifrada.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="2c8ed-122">Un atacante puede usar un relleno de Oracle, en combinación con cómo se estructuran los datos CBC, para enviar mensajes ligeramente modificados al código que expone el Oracle y seguir enviando datos hasta que Oracle les indique que los datos son correctos.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="2c8ed-123">A partir de esta respuesta, el atacante puede descifrar el byte de mensaje por byte.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="2c8ed-124">Las redes modernas de equipos son de una calidad tan alta que un atacante puede detectar diferencias muy pequeñas (menos de 0,1 MS) en el tiempo de ejecución de los sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span><span data-ttu-id="2c8ed-125">Las aplicaciones que suponen que un descifrado correcto solo se puede producir cuando los datos no se han alterado pueden ser vulnerables a ataques de herramientas diseñadas para observar diferencias en el descifrado correcto e incorrecto.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-125"> Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="2c8ed-126">Aunque esta diferencia de tiempo puede ser más importante en algunos lenguajes o bibliotecas que otros, ahora se considera que se trata de una amenaza práctica para todos los lenguajes y bibliotecas cuando se tiene en cuenta la respuesta de la aplicación a los errores.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="2c8ed-127">Este ataque se basa en la capacidad de cambiar los datos cifrados y probar el resultado con Oracle.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="2c8ed-128">La única manera de mitigar completamente el ataque es detectar los cambios en los datos cifrados y rechazar la realización de acciones en él.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="2c8ed-129">La manera estándar de hacerlo es crear una firma para los datos y validar esa firma antes de que se realicen las operaciones.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="2c8ed-130">La firma debe ser comprobable, no la puede crear el atacante; de lo contrario, cambiaría los datos cifrados y, a continuación, calcularía una nueva firma basada en los datos modificados.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="2c8ed-131">Un tipo común de la firma adecuada se conoce como código de autenticación de mensajes hash con clave (HMAC).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="2c8ed-132">Un HMAC difiere de una suma de comprobación en que toma una clave secreta, conocida solo por la persona que produce HMAC y a la persona que la valida.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="2c8ed-133">Sin la posesión de la clave, no se puede producir un HMAC correcto.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="2c8ed-134">Cuando reciba los datos, deberá tomar los datos cifrados, calcular de forma independiente el HMAC con la clave secreta y el recurso compartido de remitente y, a continuación, comparar el HMAC que envió con el que ha calculado.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="2c8ed-135">Esta comparación debe ser una hora constante; de lo contrario, se ha agregado otra Oracle que se puede detectar, lo que permite un tipo de ataque diferente.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="2c8ed-136">En Resumen, para usar cifrados de bloques CBC rellenos de forma segura, debe combinarlos con un HMAC (u otra comprobación de integridad de los datos) que valide mediante una comparación de hora constante antes de intentar descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="2c8ed-137">Dado que todos los mensajes modificados tardan la misma cantidad de tiempo en generar una respuesta, se impide el ataque.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="2c8ed-138">Quién es vulnerable</span><span class="sxs-lookup"><span data-stu-id="2c8ed-138">Who is vulnerable</span></span>

<span data-ttu-id="2c8ed-139">Esta vulnerabilidad se aplica a las aplicaciones administradas y nativas que realizan su propio cifrado y descifrado.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="2c8ed-140">Esto incluye, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2c8ed-140">This includes, for example:</span></span>

- <span data-ttu-id="2c8ed-141">Aplicación que cifra una cookie para el descifrado posterior en el servidor.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="2c8ed-142">Aplicación de base de datos que permite a los usuarios insertar datos en una tabla cuyas columnas se descifran más adelante.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="2c8ed-143">Una aplicación de transferencia de datos que se basa en el cifrado mediante una clave compartida para proteger los datos en tránsito.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="2c8ed-144">Aplicación que cifra y descifra los mensajes "dentro" del túnel TLS.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="2c8ed-145">Tenga en cuenta que el uso de TLS por sí solo puede no protegerle en estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="2c8ed-146">Una aplicación vulnerable:</span><span class="sxs-lookup"><span data-stu-id="2c8ed-146">A vulnerable application:</span></span>

- <span data-ttu-id="2c8ed-147">Descifra los datos mediante el modo de cifrado CBC con un modo de relleno comprobable, como PKCS # 7 o ANSI X. 923.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="2c8ed-148">Realiza el descifrado sin tener que realizar una comprobación de integridad de datos (a través de un MAC o una firma digital asimétrica).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="2c8ed-149">Esto también se aplica a las aplicaciones compiladas sobre abstracciones en la parte superior de estos primitivos, como la estructura EnvelopedData de la sintaxis de mensajes de cifrado (PKCS # 7/CMS).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="2c8ed-150">Áreas relacionadas de preocupación</span><span class="sxs-lookup"><span data-stu-id="2c8ed-150">Related areas of concern</span></span>

<span data-ttu-id="2c8ed-151">La investigación ha llevado a Microsoft a preocuparse por los mensajes CBC que se rellenan con el relleno ISO 10126-equivalente cuando el mensaje tiene una estructura de pie de página bien conocida o predecible.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="2c8ed-152">Por ejemplo, el contenido está preparado bajo las reglas de la recomendación de cifrado y la recomendación de procesamiento de XML de W3C (xmlenc, EncryptedXml).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="2c8ed-153">Aunque la guía del W3C para firmar el mensaje, el cifrado se consideró adecuado en el momento en que Microsoft ahora recomienda realizar siempre el cifrado y luego el signo.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="2c8ed-154">Los desarrolladores de aplicaciones siempre deben ser conscientes de comprobar la aplicabilidad de una clave de firma asimétrica, ya que no hay ninguna relación de confianza inherente entre una clave asimétrica y un mensaje arbitrario.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="2c8ed-155">Detalles</span><span class="sxs-lookup"><span data-stu-id="2c8ed-155">Details</span></span>

<span data-ttu-id="2c8ed-156">Históricamente, se ha dado el consenso de que es importante cifrar y autenticar datos importantes mediante el uso de medios como las firmas HMAC o RSA.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="2c8ed-157">Sin embargo, se han realizado instrucciones menos claras sobre cómo secuenciar las operaciones de cifrado y autenticación.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="2c8ed-158">Debido a la vulnerabilidad que se detalla en este artículo, la guía de Microsoft es ahora para usar siempre el paradigma "cifrar y luego firmar".</span><span class="sxs-lookup"><span data-stu-id="2c8ed-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="2c8ed-159">Es decir, primero debe cifrar los datos mediante una clave simétrica y, a continuación, calcular una firma MAC o asimétrica a través del texto cifrado (datos cifrados).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="2c8ed-160">Al descifrar los datos, realice la ejecución inversa.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="2c8ed-161">En primer lugar, confirme el MAC o la firma del texto cifrado y, a continuación, descifre.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="2c8ed-162">Se sabe que existe una clase de vulnerabilidades conocidas como "los ataques de rellenado de Oracle" durante más de 10 años.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="2c8ed-163">Estas vulnerabilidades permiten que un atacante descifre los datos cifrados mediante algoritmos de bloques simétricos, como AES y 3DES, y no use más de 4096 intentos por bloque de datos.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="2c8ed-164">Estas vulnerabilidades hacen uso del hecho de que los cifrados de bloques se usan con mayor frecuencia con datos de relleno comprobables al final.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="2c8ed-165">Se encontró que, si un atacante puede alterar el texto cifrado y averiguar si la manipulación produjo un error en el formato del relleno al final, el atacante puede descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="2c8ed-166">Inicialmente, los ataques prácticos se basaban en servicios que devolverían códigos de error diferentes en función de si el relleno era válido, como la vulnerabilidad ASP.NET [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span></span> <span data-ttu-id="2c8ed-167">Sin embargo, ahora Microsoft considera que es práctico realizar ataques similares usando solo las diferencias de tiempo entre el procesamiento de relleno válido y no válido.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="2c8ed-168">Siempre que el esquema de cifrado emplee una firma y que la comprobación de la firma se realice con un tiempo de ejecución fijo para una longitud de datos determinada (con independencia del contenido), la integridad de los datos se puede comprobar sin emitir ninguna información a un atacante a través de un [canal secundario](https://en.wikipedia.org/wiki/Side-channel_attack).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="2c8ed-169">Como la comprobación de la integridad rechaza los mensajes alterados, se mitiga la amenaza de rellenado de Oracle.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="2c8ed-170">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="2c8ed-170">Guidance</span></span>

<span data-ttu-id="2c8ed-171">En primer lugar, Microsoft recomienda que todos los datos que tengan confidencialidad se transmitan a través de la seguridad de la capa de transporte (TLS), el sucesor de Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="2c8ed-172">A continuación, analice la aplicación para:</span><span class="sxs-lookup"><span data-stu-id="2c8ed-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="2c8ed-173">Comprenda exactamente el cifrado que está realizando y el cifrado que proporcionan las plataformas y las API que está usando.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="2c8ed-174">Asegúrese de que cada uso en cada capa de un [algoritmo de cifrado de bloques](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)simétricos, como AES y 3DES, en modo CBC incorpore el uso de una comprobación de integridad de datos con clave secreta (una firma asimétrica, un HMAC, o para cambiar el modo de cifrado a un modo de [cifrado autenticado](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) como GCM o CCM).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="2c8ed-175">En función de la investigación actual, se considera generalmente que cuando los pasos de cifrado y autenticación se realizan de forma independiente para los modos de cifrado no AE, la mejor opción general es autenticar el texto cifrado (cifrar y luego firmar).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="2c8ed-176">Sin embargo, no hay ninguna respuesta de un solo tamaño que se ajuste a la criptografía y esta generalización no es tan buena como el Consejo dirigido de un cifrado profesional.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="2c8ed-177">Se recomienda que las aplicaciones que no pueden cambiar su formato de mensajería, pero que realizan descifrado CBC no autenticado intenten incorporar mitigaciones, como:</span><span class="sxs-lookup"><span data-stu-id="2c8ed-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="2c8ed-178">Descifrar sin permitir que el descifrador Compruebe o quite el relleno:</span><span class="sxs-lookup"><span data-stu-id="2c8ed-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="2c8ed-179">Cualquier relleno aplicado todavía debe quitarse u omitirse, se mueve la carga a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="2c8ed-180">La ventaja es que la comprobación y la eliminación del relleno se pueden incorporar en otra lógica de comprobación de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="2c8ed-181">Si la comprobación de relleno y la comprobación de datos se pueden realizar en tiempo constante, se reduce la amenaza.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="2c8ed-182">Dado que la interpretación del relleno cambia la longitud del mensaje percibido, es posible que todavía se emita información de tiempo de este enfoque.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="2c8ed-183">Cambie el modo de relleno de descifrado a ISO10126:</span><span class="sxs-lookup"><span data-stu-id="2c8ed-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="2c8ed-184">El relleno de descifrado de ISO10126 es compatible con el relleno de cifrado PKCS7 y el relleno de cifrado ANSIX923.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="2c8ed-185">Al cambiar el modo, se reduce el relleno de los conocimientos de Oracle a 1 byte en lugar de todo el bloque.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="2c8ed-186">Sin embargo, si el contenido tiene un pie de página conocido, como un elemento XML de cierre, los ataques relacionados pueden seguir atacando el resto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="2c8ed-187">Esto tampoco impide la recuperación de texto sin formato en situaciones en las que el atacante puede forzar el mismo texto no cifrado para que se cifre varias veces con un desplazamiento de mensaje diferente.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="2c8ed-188">Gate la evaluación de una llamada de descifrado para amortiguar la señal de temporización:</span><span class="sxs-lookup"><span data-stu-id="2c8ed-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="2c8ed-189">El cálculo del tiempo de espera debe tener un mínimo superior al máximo de tiempo que tardará la operación de descifrado en cualquier segmento de datos que contenga relleno.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="2c8ed-190">Los cálculos de tiempo deben realizarse de acuerdo con las instrucciones de [adquisición de marcas de tiempo de alta resolución](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), no mediante el uso de (sujeto a desactivación <xref:System.Environment.TickCount?displayProperty=nameWithType> /desbordamiento) o restar dos marcas de tiempo del sistema (sujetas a errores de ajuste de NTP).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="2c8ed-191">Los cálculos de tiempo deben ser inclusivos de la operación de descifrado, incluidas todas las excepciones potenciales en aplicaciones administradas o de C++, no solo se rellenan hasta el final.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="2c8ed-192">Si el éxito o el error se ha determinado todavía, la puerta de tiempo debe devolver un error cuando expire.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="2c8ed-193">Los servicios que realizan el descifrado no autenticado deben tener supervisión para detectar que se ha producido un desbordamiento de mensajes "no válidos".</span><span class="sxs-lookup"><span data-stu-id="2c8ed-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="2c8ed-194">Tenga en cuenta que esta señal contiene falsos positivos (datos dañados de forma legítima) y falsos negativos (repartir el ataque durante un tiempo suficientemente largo para eludir la detección).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="2c8ed-195">Búsqueda de aplicaciones nativas de código vulnerable</span><span class="sxs-lookup"><span data-stu-id="2c8ed-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="2c8ed-196">En el caso de los programas creados en la biblioteca Cryptography: Next Generation (CNG) de Windows:</span><span class="sxs-lookup"><span data-stu-id="2c8ed-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="2c8ed-197">La llamada de descifrado es [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), especificando la `BCRYPT_BLOCK_PADDING` marca.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="2c8ed-198">El identificador de clave se ha inicializado mediante una llamada a [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) con [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) establecida en `BCRYPT_CHAIN_MODE_CBC` .</span><span class="sxs-lookup"><span data-stu-id="2c8ed-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="2c8ed-199">Puesto que `BCRYPT_CHAIN_MODE_CBC` es el valor predeterminado, es posible que el código afectado no tenga asignado ningún valor para `BCRYPT_CHAINING_MODE` .</span><span class="sxs-lookup"><span data-stu-id="2c8ed-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="2c8ed-200">Para programas creados en la antigua API criptográfica de Windows:</span><span class="sxs-lookup"><span data-stu-id="2c8ed-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="2c8ed-201">La llamada de descifrado es [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) con `Final=TRUE` .</span><span class="sxs-lookup"><span data-stu-id="2c8ed-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="2c8ed-202">El identificador de clave se ha inicializado mediante una llamada a [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) con [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) establecida en `CRYPT_MODE_CBC` .</span><span class="sxs-lookup"><span data-stu-id="2c8ed-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="2c8ed-203">Puesto que `CRYPT_MODE_CBC` es el valor predeterminado, es posible que el código afectado no tenga asignado ningún valor para `KP_MODE` .</span><span class="sxs-lookup"><span data-stu-id="2c8ed-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="2c8ed-204">Búsqueda de aplicaciones administradas por código vulnerables</span><span class="sxs-lookup"><span data-stu-id="2c8ed-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="2c8ed-205">La llamada de descifrado es a <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> los <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> métodos o en <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2c8ed-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="2c8ed-206">Esto incluye los siguientes tipos derivados en .NET, pero también puede incluir tipos de terceros:</span><span class="sxs-lookup"><span data-stu-id="2c8ed-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
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
- <span data-ttu-id="2c8ed-207">La <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> propiedad se estableció en <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> , <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType> o <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2c8ed-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="2c8ed-208">Puesto que <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> es el valor predeterminado, es posible que el código afectado nunca haya asignado la <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="2c8ed-209">La <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> propiedad se estableció en<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2c8ed-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="2c8ed-210">Puesto que <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> es el valor predeterminado, es posible que el código afectado nunca haya asignado la <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="2c8ed-211">Búsqueda de código vulnerable: sintaxis de mensajes criptográficos</span><span class="sxs-lookup"><span data-stu-id="2c8ed-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="2c8ed-212">Un mensaje CMS EnvelopedData no autenticado cuyo contenido cifrado usa el modo CBC de AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) o RC2 (1.2.840.113549.3.2) es vulnerable, así como mensajes que usan cualquier otro algoritmo de cifrado de bloques en el modo CBC.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="2c8ed-213">Aunque los cifrados de secuencias no son susceptibles a esta vulnerabilidad determinada, Microsoft recomienda siempre autenticar los datos a través de la inspección del valor de ContentEncryptionAlgorithm.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="2c8ed-214">En el caso de las aplicaciones administradas, se puede detectar un BLOB EnvelopedData de CMS como cualquier valor que se pase a <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="2c8ed-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="2c8ed-215">En el caso de las aplicaciones nativas, se puede detectar un BLOB EnvelopedData de CMS como cualquier valor proporcionado a un identificador CMS a través de [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) cuyo [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) resultante es `CMSG_ENVELOPED` y/o el controlador CMS envía una `CMSG_CTRL_DECRYPT` instrucción a través de [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span><span class="sxs-lookup"><span data-stu-id="2c8ed-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="2c8ed-216">Ejemplo de código vulnerable: administrado</span><span class="sxs-lookup"><span data-stu-id="2c8ed-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="2c8ed-217">Este método lee una cookie y la descifra y no se ve ninguna comprobación de integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="2c8ed-218">Por lo tanto, el usuario que lo recibió o cualquier atacante que haya obtenido el valor de cookie cifrado puede atacar el contenido de una cookie leída por este método.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

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

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="2c8ed-219">Código de ejemplo con procedimientos recomendados: administrado</span><span class="sxs-lookup"><span data-stu-id="2c8ed-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="2c8ed-220">En el código de ejemplo siguiente se usa un formato de mensaje no estándar.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="2c8ed-221">donde los `cipher_algorithm_id` `hmac_algorithm_id` identificadores de algoritmo y son representaciones locales de la aplicación (no estándar) de esos algoritmos.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="2c8ed-222">Estos identificadores pueden tener sentido en otras partes del Protocolo de mensajería existente, en lugar de como una bytestream concatenada.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="2c8ed-223">En este ejemplo también se usa una única clave maestra para derivar una clave de cifrado y una clave HMAC.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="2c8ed-224">Esto se proporciona tanto por comodidad para convertir una aplicación con una clave única en una aplicación con doble clave como para alentar el mantenimiento de las dos claves como valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="2c8ed-225">Además, garantiza que la clave HMAC y la clave de cifrado no se pueden obtener de la sincronización.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="2c8ed-226">En este ejemplo no se acepta un <xref:System.IO.Stream> para el cifrado o descifrado.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="2c8ed-227">El formato de datos actual dificulta el cifrado de un paso porque el `hmac_tag` valor precede al texto cifrado.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="2c8ed-228">Sin embargo, se ha elegido este formato porque mantiene todos los elementos de tamaño fijo al principio para que el analizador sea más sencillo.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="2c8ed-229">Con este formato de datos, es posible descifrar un paso, aunque se puede llamar a un implementador para que llame a GetHashAndReset y compruebe el resultado antes de llamar a TransformFinalBlock.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="2c8ed-230">Si el cifrado de streaming es importante, es posible que se requiera un modo AE diferente.</span><span class="sxs-lookup"><span data-stu-id="2c8ed-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2c8ed-231">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c8ed-231">See also</span></span>

- [<span data-ttu-id="2c8ed-232">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="2c8ed-232">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="2c8ed-233">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="2c8ed-233">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="2c8ed-234">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="2c8ed-234">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="2c8ed-235">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="2c8ed-235">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
