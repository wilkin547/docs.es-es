---
title: Vulnerabilidades de control de tiempo con descifrado simétrico modo CBC mediante el relleno
description: Obtenga información acerca de cómo detectar y mitigar vulnerabilidades de control de tiempo con descifrado simétrico modo de encadenamiento de bloques de cifrado (CBC), mediante el relleno.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: a07acbb943c430f6e26bec44f55a5c84306da513
ms.sourcegitcommit: 73a662360bbe2f43c19aca1fbcc2565025c60cd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2018
ms.locfileid: "35327462"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="3db12-103">Vulnerabilidades de control de tiempo con descifrado simétrico modo CBC mediante el relleno</span><span class="sxs-lookup"><span data-stu-id="3db12-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="3db12-104">Microsoft, en función de la investigación criptográfica detectada, cree que, salvo circunstancias muy específicas, ya no es seguro descifrar los datos cifrados con el modo de encadenamiento de bloques de cifrado (CBC) del cifrado simétrico cuando ha relleno comprobable se aplican sin primera asegura la integridad del texto cifrado.</span><span class="sxs-lookup"><span data-stu-id="3db12-104">Microsoft, based on currently known cryptographic research, believes that, except for very specific circumstances, it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext.</span></span>

## <a name="introduction"></a><span data-ttu-id="3db12-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="3db12-105">Introduction</span></span>

<span data-ttu-id="3db12-106">Un ataque de oracle de relleno es un tipo de ataque contra los datos cifrados que permite que el atacante descifrar el contenido de los datos, sin conocer la clave.</span><span class="sxs-lookup"><span data-stu-id="3db12-106">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="3db12-107">Oracle hace referencia a un "indicar" que proporciona información atacante sobre si es correcta la acción que está ejecutando o no.</span><span class="sxs-lookup"><span data-stu-id="3db12-107">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="3db12-108">Imagine un tablero de juego o la tarjeta de juego con un elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="3db12-108">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="3db12-109">Cuando su cara ilumina con una gran sonrisa porque considera que es el usuario va a realizar un buen movimiento, que es una de oracle.</span><span class="sxs-lookup"><span data-stu-id="3db12-109">When her face lights up with a big smile because she thinks she's about to make a good move, that's an oracle.</span></span> <span data-ttu-id="3db12-110">Como el adversario, puede usar este oracle para planear el cambio siguiente adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="3db12-110">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="3db12-111">El relleno es un término cifrado específico.</span><span class="sxs-lookup"><span data-stu-id="3db12-111">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="3db12-112">Algunos cifrados, que son los algoritmos utilizados para cifrar los datos, trabajar en bloques de datos donde cada bloque tiene un tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="3db12-112">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="3db12-113">Si los datos que desea cifrar no tiene el tamaño correcto para rellenar los bloques, los datos se rellenan hasta que lo hace.</span><span class="sxs-lookup"><span data-stu-id="3db12-113">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="3db12-114">Muchas formas de relleno requieren ese relleno para que siempre esté presente, incluso si la entrada original era del tamaño adecuado.</span><span class="sxs-lookup"><span data-stu-id="3db12-114">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="3db12-115">Esto permite que el relleno a siempre eliminarse tras el descifrado.</span><span class="sxs-lookup"><span data-stu-id="3db12-115">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="3db12-116">Montar las dos cosas, una implementación de software con un relleno de oracle revela si los datos descifrados tienen relleno válido.</span><span class="sxs-lookup"><span data-stu-id="3db12-116">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="3db12-117">Oracle podría ser algo tan sencillo como devolver un valor que indica "Relleno no válido" o algo más complicado como realizar mejorará en gran medida en otro momento para procesar un bloque válido en lugar de un bloque no válido.</span><span class="sxs-lookup"><span data-stu-id="3db12-117">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="3db12-118">Basado en bloques cifrados otra propiedad, el modo, que determina la relación de datos en el primer bloque a los datos del segundo bloque, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="3db12-118">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="3db12-119">Uno de los modos de usados más frecuente es CBC.</span><span class="sxs-lookup"><span data-stu-id="3db12-119">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="3db12-120">El cifrado CBC presenta un bloque aleatorio inicial, conocido como el Vector de inicialización (IV) y combina el bloque anterior con el resultado de cifrado estático para que sea de modo que cifra el mismo mensaje con la misma clave no genera siempre el mismo resultado cifrado.</span><span class="sxs-lookup"><span data-stu-id="3db12-120">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="3db12-121">Un atacante puede usar un relleno oracle, en combinación con cómo está estructuradas datos CBC, para enviar mensajes ligeramente modificados en el código que expone el oracle y continúe enviando datos hasta que el de oracle que les informa de los datos son correctos.</span><span class="sxs-lookup"><span data-stu-id="3db12-121">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="3db12-122">De esta respuesta, el atacante puede descifrar el mensaje byte a byte.</span><span class="sxs-lookup"><span data-stu-id="3db12-122">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="3db12-123">Las redes de equipos modernos son de este tipo de alta calidad que un atacante puede detectar muy pequeños (menos de 0,1 ms) de las diferencias en la ejecución de tiempo en sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="3db12-123">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span> <span data-ttu-id="3db12-124">Las aplicaciones que se asume que el descifrado correcto sólo puede ocurrir cuando los datos no se ha alterado pueden ser vulnerables a ataques desde herramientas diseñadas para observar las diferencias en el descifrado correcta e incorrecta.</span><span class="sxs-lookup"><span data-stu-id="3db12-124">Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="3db12-125">Aunque esta diferencia de tiempo puede ser más importante en algunos idiomas o bibliotecas que otros, ahora se considera que esto es una amenaza para la práctica para todos los lenguajes y las bibliotecas al tener en cuenta la respuesta de la aplicación a un error.</span><span class="sxs-lookup"><span data-stu-id="3db12-125">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="3db12-126">Este ataque se basa en la capacidad de cambiar los datos cifrados y probar el resultado con el de oracle.</span><span class="sxs-lookup"><span data-stu-id="3db12-126">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="3db12-127">La única manera de mitigar los ataques de totalmente consiste en detectar cambios en los datos cifrados y no realizar ninguna acción en él.</span><span class="sxs-lookup"><span data-stu-id="3db12-127">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="3db12-128">La manera estándar de hacerlo consiste en crear una firma para los datos y validar esa firma antes de que se llevan a cabo ninguna operación.</span><span class="sxs-lookup"><span data-stu-id="3db12-128">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="3db12-129">Se debe poder verificar la firma, no se puede crear por el atacante, en caso contrario, se podría cambiar los datos cifrados y calcular una firma nueva en función de los datos modificados.</span><span class="sxs-lookup"><span data-stu-id="3db12-129">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="3db12-130">Un tipo común de firma adecuada se conoce como un código de autenticación de mensajes de hash con claves (HMAC).</span><span class="sxs-lookup"><span data-stu-id="3db12-130">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="3db12-131">Un HMAC difiere de una suma de comprobación en que tiene una clave secreta, conocidos únicamente a la persona que produce el HMAC y a la persona validarla.</span><span class="sxs-lookup"><span data-stu-id="3db12-131">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="3db12-132">Sin la posesión de la clave, no se puede producir un HMAC correcto.</span><span class="sxs-lookup"><span data-stu-id="3db12-132">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="3db12-133">Cuando reciba los datos, se obtienen los datos cifrados, por separado el HMAC con la clave secreta de proceso y el recurso compartido de remitente y comparar calcula el HMAC envían con el.</span><span class="sxs-lookup"><span data-stu-id="3db12-133">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="3db12-134">Esta comparación debe ser un tiempo constante, en caso contrario, ha agregado otra oracle detectable, lo que permite un tipo diferente de ataque.</span><span class="sxs-lookup"><span data-stu-id="3db12-134">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="3db12-135">En resumen usar rellena los cifrados de bloques de cifrado CBC con seguridad, debe combinar con un HMAC (u otra comprobación de integridad de datos) que se valida mediante una comparación de tiempo constante antes de intentar para descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="3db12-135">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="3db12-136">Puesto que todos los mensajes modificados toman la misma cantidad de tiempo para generar una respuesta, se impide el ataque.</span><span class="sxs-lookup"><span data-stu-id="3db12-136">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="3db12-137">¿Quién es vulnerable</span><span class="sxs-lookup"><span data-stu-id="3db12-137">Who is vulnerable</span></span>

<span data-ttu-id="3db12-138">Esta vulnerabilidad se aplica a aplicaciones nativas y administradas que están realizando su propio cifrado y descifrado.</span><span class="sxs-lookup"><span data-stu-id="3db12-138">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="3db12-139">Esto incluye, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3db12-139">This includes, for example:</span></span>

- <span data-ttu-id="3db12-140">Una aplicación que cifra una cookie para el posterior descifrado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="3db12-140">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="3db12-141">Una aplicación de base de datos que proporciona la capacidad de los usuarios insertar datos en una tabla cuyas columnas se descifran más adelante.</span><span class="sxs-lookup"><span data-stu-id="3db12-141">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="3db12-142">Una aplicación de transferencia de datos que se basa en el cifrado mediante una clave compartida para proteger los datos en tránsito.</span><span class="sxs-lookup"><span data-stu-id="3db12-142">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="3db12-143">Una aplicación que cifra y descifra los mensajes "del túnel TSL dentro de".</span><span class="sxs-lookup"><span data-stu-id="3db12-143">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="3db12-144">Tenga en cuenta que utilizando TLS por sí sola puede no protege en estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="3db12-144">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="3db12-145">Una aplicación vulnerable:</span><span class="sxs-lookup"><span data-stu-id="3db12-145">A vulnerable application:</span></span>

- <span data-ttu-id="3db12-146">Descifra datos con el modo de cifrado CBC con un modo de relleno comprobables, como PKCS #7 o X.923 de ANSI.</span><span class="sxs-lookup"><span data-stu-id="3db12-146">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="3db12-147">Lleva a cabo el descifrado sin necesidad de realizar una comprobación de integridad de datos (a través de un equipo MAC o una firma digital asimétrica).</span><span class="sxs-lookup"><span data-stu-id="3db12-147">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="3db12-148">Esto también se aplica a las aplicaciones que se basa en abstracciones encima de estos tipos primitivos, como la estructura de sintaxis de mensajes criptográficos (PKCS #7/CMS) EnvelopedData.</span><span class="sxs-lookup"><span data-stu-id="3db12-148">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="3db12-149">Áreas problemáticas relacionadas</span><span class="sxs-lookup"><span data-stu-id="3db12-149">Related areas of concern</span></span>

<span data-ttu-id="3db12-150">Research se ha llevado a Microsoft que preocuparse más acerca de los mensajes de CBC que se rellenan con equivalentes ISO 10126 relleno cuando el mensaje tiene una estructura de pie de página conocidos o de predicción.</span><span class="sxs-lookup"><span data-stu-id="3db12-150">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="3db12-151">Por ejemplo, contenido elaborado con arreglo a las reglas de la sintaxis de cifrado de XML de W3C y la recomendación de procesamiento (xmlenc, EncryptedXml).</span><span class="sxs-lookup"><span data-stu-id="3db12-151">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="3db12-152">Mientras que las instrucciones de W3C para firmar el mensaje, a continuación, cifrar consideró apropiada en el momento, Microsoft recomienda ahora realizar siempre signo, a continuación, cifrar.</span><span class="sxs-lookup"><span data-stu-id="3db12-152">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="3db12-153">Los desarrolladores de aplicaciones siempre debe prestar atención de comprobar la aplicabilidad de una clave de firma asimétrico, ya que no existe ninguna relación de confianza inherente entre una clave asimétrica y un mensaje arbitrario.</span><span class="sxs-lookup"><span data-stu-id="3db12-153">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="3db12-154">Detalles</span><span class="sxs-lookup"><span data-stu-id="3db12-154">Details</span></span>

<span data-ttu-id="3db12-155">Históricamente, ha habido consenso que es importante cifrar y autenticar los datos importantes, con recursos como las firmas HMAC o RSA.</span><span class="sxs-lookup"><span data-stu-id="3db12-155">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="3db12-156">Sin embargo, ha habido menos instrucciones claras sobre cómo secuenciar las operaciones de cifrado y autenticación.</span><span class="sxs-lookup"><span data-stu-id="3db12-156">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="3db12-157">Debido a la vulnerabilidad que se detallan en este artículo, instrucciones de Microsoft es ahora use siempre el paradigma "cifrar-then-sign".</span><span class="sxs-lookup"><span data-stu-id="3db12-157">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="3db12-158">Es decir, en primer lugar cifrar los datos mediante una clave simétrica, a continuación, calcular un MAC o firmas asimétricas con el texto de cifrado (datos cifrados).</span><span class="sxs-lookup"><span data-stu-id="3db12-158">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="3db12-159">Al descifrar los datos, realizar la inversa.</span><span class="sxs-lookup"><span data-stu-id="3db12-159">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="3db12-160">En primer lugar, confirme el MAC o la firma del texto cifrado, a continuación, descifrarlo.</span><span class="sxs-lookup"><span data-stu-id="3db12-160">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="3db12-161">Una clase de vulnerabilidades conocidas como "relleno ataques de oracle" famosos existiendo durante más de 10 años.</span><span class="sxs-lookup"><span data-stu-id="3db12-161">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="3db12-162">Estas vulnerabilidades permitir que un atacante descifrar los datos cifrados con algoritmos de bloques simétrico, como AES y 3DES, con no más de 4096 intentos por cada bloque de datos.</span><span class="sxs-lookup"><span data-stu-id="3db12-162">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="3db12-163">Estas vulnerabilidades hacer uso del hecho de que cifrados por bloques suelen usarse con datos comprobables relleno al final.</span><span class="sxs-lookup"><span data-stu-id="3db12-163">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="3db12-164">Se encontró que si un atacante puede alterar el texto cifrado y averiguar si la manipulación, produjo un error en el formato de la cantidad de relleno al final, el atacante puede descifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="3db12-164">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="3db12-165">Inicialmente, resulta muy prácticos ataques se basaban en los servicios que se devuelven códigos de error diferentes en función de si el relleno era válido, como la vulnerabilidad ASP.NET [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span><span class="sxs-lookup"><span data-stu-id="3db12-165">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span></span> <span data-ttu-id="3db12-166">Sin embargo, Microsoft ahora cree que es práctico realizar ataques similar con solo las diferencias de tiempo entre procesar relleno válido y no válido.</span><span class="sxs-lookup"><span data-stu-id="3db12-166">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="3db12-167">Siempre que el esquema de cifrado emplea una firma y que se realiza la comprobación de firma con un tiempo de ejecución fijo durante un período determinado de datos (independientemente del contenido), se puede comprobar la integridad de datos sin emitir ninguna información a un atacante a través de un [canal del lado](https://en.wikipedia.org/wiki/Side-channel_attack).</span><span class="sxs-lookup"><span data-stu-id="3db12-167">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="3db12-168">Puesto que la comprobación de integridad rechaza los mensajes alterados, se mitiga la amenaza de oracle de relleno.</span><span class="sxs-lookup"><span data-stu-id="3db12-168">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="3db12-169">Orientación</span><span class="sxs-lookup"><span data-stu-id="3db12-169">Guidance</span></span>

<span data-ttu-id="3db12-170">En primer lugar y ante todo, Microsoft recomienda que los datos cuya confidencialidad deben transmitirse a través del seguridad de capa de transporte (TLS), el sucesor para Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="3db12-170">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="3db12-171">A continuación, analizar la aplicación para:</span><span class="sxs-lookup"><span data-stu-id="3db12-171">Next, analyze your application to:</span></span>

- <span data-ttu-id="3db12-172">Comprender exactamente qué va a realizar el cifrado y el cifrado se proporciona con las plataformas y las API que está usando.</span><span class="sxs-lookup"><span data-stu-id="3db12-172">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="3db12-173">Estar seguro de que cada uso en cada nivel del simétrico [algoritmo de cifrado de bloques](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), como AES y 3DES en modo CBC incorporar el uso de una comprobación de integridad de datos ordenados secreto (una firma asimétrica, un HMAC, o para cambiar el modo de cifrado para un [autenticado cifrado](https://en.wikipedia.org/wiki/Authenticated_encryption) modo (AE) como GCM o CCM).</span><span class="sxs-lookup"><span data-stu-id="3db12-173">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="3db12-174">Según el estudio actual, se suele pensar que cuando los pasos de autenticación y el cifrado se realizan independientemente en modos de no AE de cifrado, el texto cifrado de autenticación (cifrar-then-inicio de sesión) es la mejor opción general.</span><span class="sxs-lookup"><span data-stu-id="3db12-174">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="3db12-175">Sin embargo, no hay ninguna respuesta correcta única a la criptografía y esta generalización no es tan buena como dirigido consejos desde un criptógrafo profesional.</span><span class="sxs-lookup"><span data-stu-id="3db12-175">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="3db12-176">Se recomienda que las aplicaciones que no pueden cambiar su formato de mensajería pero realizar el descifrado de CBC no autenticado para intentar incorporar mitigaciones como:</span><span class="sxs-lookup"><span data-stu-id="3db12-176">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="3db12-177">Descifrar sin permitir que el sistema de descifrado comprobar o quitar relleno:</span><span class="sxs-lookup"><span data-stu-id="3db12-177">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="3db12-178">Cualquier relleno que se aplicó todavía debe quitarse o pasa por alto, se mueve la carga en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3db12-178">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="3db12-179">La ventaja es que la comprobación de relleno y eliminación se pueden incorporar otra lógica de comprobación de datos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3db12-179">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="3db12-180">Si la comprobación de relleno y la comprobación de datos se pueden realizar en tiempo constante, se reduce la amenaza.</span><span class="sxs-lookup"><span data-stu-id="3db12-180">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="3db12-181">Puesto que la interpretación de la cantidad de relleno cambia la longitud del mensaje percibido, todavía puede haber información de tiempo que se genera a partir de este enfoque.</span><span class="sxs-lookup"><span data-stu-id="3db12-181">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="3db12-182">Cambiar el modo de relleno de descifrado para ISO10126:</span><span class="sxs-lookup"><span data-stu-id="3db12-182">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="3db12-183">Relleno de ISO10126 descifrado es compatible con relleno de cifrado PKCS7 y relleno de cifrado ANSIX923.</span><span class="sxs-lookup"><span data-stu-id="3db12-183">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="3db12-184">Cambiar el modo, reduce el conocimiento de oracle de relleno a 1 bytes en lugar de todo el bloque.</span><span class="sxs-lookup"><span data-stu-id="3db12-184">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="3db12-185">Sin embargo, si el contenido tiene un pie de página conocido como un elemento XML, cierre ataques relacionados pueden seguir atacar el resto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3db12-185">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="3db12-186">También esto no evita que recuperación de texto simple en situaciones donde el atacante puede forzar el mismo texto no van a cifrar varias veces con un desplazamiento de mensajes diferente.</span><span class="sxs-lookup"><span data-stu-id="3db12-186">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="3db12-187">Puerta de la evaluación de una llamada de descifrado para disminuir la señal de control de tiempo:</span><span class="sxs-lookup"><span data-stu-id="3db12-187">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="3db12-188">El cálculo de tiempo de espera debe tener un mínimo que superan la cantidad máxima de tiempo que tardaría la operación de descifrado para cualquier segmento de datos que contiene el relleno.</span><span class="sxs-lookup"><span data-stu-id="3db12-188">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="3db12-189">Cálculos de tiempo deben realizarse según las instrucciones de [adquirir marcas de tiempo de alta resolución](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), no mediante <xref:System.Environment.TickCount?displayProperty=nameWithType> (de acuerdo con tirar over/desbordamiento) o restar dos marcas de tiempo de sistema (regularizar NTP errores).</span><span class="sxs-lookup"><span data-stu-id="3db12-189">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="3db12-190">Cálculos de tiempo deben ser favorecer la operación de descifrado, incluidas todas las excepciones posibles en administrado o aplicaciones de C++, no solo se rellena al final.</span><span class="sxs-lookup"><span data-stu-id="3db12-190">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="3db12-191">Si se realizó correctamente o no se ha determinado, la puerta de tiempo necesita devolver errores cuando expire.</span><span class="sxs-lookup"><span data-stu-id="3db12-191">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="3db12-192">Servicios que se va a realizar el descifrado no autenticado deben disponiendo de supervisión en su lugar para detectar que una avalancha de mensajes "no válidos" ha llegado a través de.</span><span class="sxs-lookup"><span data-stu-id="3db12-192">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="3db12-193">Tenga en cuenta que esta señal lleva (datos dañados legítimamente) de falsos positivos y falsos negativos (que se propagan a los ataques durante un período suficientemente largo para eludir la detección).</span><span class="sxs-lookup"><span data-stu-id="3db12-193">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="3db12-194">Buscar código vulnerable: aplicaciones nativas</span><span class="sxs-lookup"><span data-stu-id="3db12-194">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="3db12-195">Para los programas que se basa en la criptografía de Windows: biblioteca de próxima generación (CNG):</span><span class="sxs-lookup"><span data-stu-id="3db12-195">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="3db12-196">La llamada de descifrado es a [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx), especificando la `BCRYPT_BLOCK_PADDING` marca.</span><span class="sxs-lookup"><span data-stu-id="3db12-196">The decryption call is to [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="3db12-197">El identificador de clave se ha inicializado mediante una llamada a [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) con [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) establecido en `BCRYPT_CHAIN_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="3db12-197">The key handle has been initialized by calling [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) with [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="3db12-198">Puesto que `BCRYPT_CHAIN_MODE_CBC` es el valor predeterminado, afectado código no ha asignado ningún valor para `BCRYPT_CHAINING_MODE`.</span><span class="sxs-lookup"><span data-stu-id="3db12-198">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="3db12-199">Para programas que se basa en la API criptográfica de Windows anteriores:</span><span class="sxs-lookup"><span data-stu-id="3db12-199">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="3db12-200">La llamada de descifrado es a [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) con `Final=TRUE`.</span><span class="sxs-lookup"><span data-stu-id="3db12-200">The decryption call is to [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) with `Final=TRUE`.</span></span>
- <span data-ttu-id="3db12-201">El identificador de clave se ha inicializado mediante una llamada a [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) con [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) establecido en `CRYPT_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="3db12-201">The key handle has been initialized by calling [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) with [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="3db12-202">Puesto que `CRYPT_MODE_CBC` es el valor predeterminado, afectado código no ha asignado ningún valor para `KP_MODE`.</span><span class="sxs-lookup"><span data-stu-id="3db12-202">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="3db12-203">Buscar código vulnerable: aplicaciones administradas</span><span class="sxs-lookup"><span data-stu-id="3db12-203">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="3db12-204">La llamada de descifrado es a la <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> o <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> métodos en <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3db12-204">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="3db12-205">Esto incluye los siguientes tipos derivados en .NET, pero también puede incluir tipos de aplicaciones de terceros:</span><span class="sxs-lookup"><span data-stu-id="3db12-205">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
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
- <span data-ttu-id="3db12-206">El <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> propiedad se estableció en <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, o <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3db12-206">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="3db12-207">Puesto que <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> es el valor predeterminado, afectado código nunca haya asignado el <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3db12-207">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="3db12-208">El <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> propiedad se estableció en <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3db12-208">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="3db12-209">Puesto que <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> es el valor predeterminado, afectado código nunca haya asignado el <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3db12-209">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="3db12-210">Buscar código vulnerable: sintaxis de cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="3db12-210">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="3db12-211">Un mensaje no autenticado de CMS EnvelopedData cuyo contenido cifrado usa el modo CBC de AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) o RC2 (1.2.840.113549.3.2) es vulnerable, así como los mensajes utilizando otros algoritmos de cifrado de bloque en modo CBC.</span><span class="sxs-lookup"><span data-stu-id="3db12-211">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="3db12-212">Mientras cifrados de flujos no son susceptibles de sufrir esta vulnerabilidad, Microsoft recomienda autenticar siempre los datos a través de inspeccionar el valor de ContentEncryptionAlgorithm.</span><span class="sxs-lookup"><span data-stu-id="3db12-212">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="3db12-213">Para las aplicaciones administradas, un EnvelopedData CMS blob puede ser detectado como cualquier valor que se pasa a <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="3db12-213">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="3db12-214">Para aplicaciones nativas, se puede detectar un blob de CMS EnvelopedData como los valores proporcionados a un identificador CMS a través de [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) cuyo resultante [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) es `CMSG_ENVELOPED` o es el identificador CMS posteriormente se envían un `CMSG_CTRL_DECRYPT` instrucciones a través de [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx).</span><span class="sxs-lookup"><span data-stu-id="3db12-214">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) whose resulting [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="3db12-215">Ejemplo de código vulnerable - administrado</span><span class="sxs-lookup"><span data-stu-id="3db12-215">Vulnerable code example - managed</span></span>

<span data-ttu-id="3db12-216">Este método lee una cookie y descifra y ninguna comprobación de integridad de datos está visible.</span><span class="sxs-lookup"><span data-stu-id="3db12-216">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="3db12-217">Por lo tanto, el contenido de una cookie que se lee por este método puede ser atacado por el usuario que ha recibido o por cualquier atacante que haya obtenido el valor de cookie cifrada.</span><span class="sxs-lookup"><span data-stu-id="3db12-217">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

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

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="3db12-218">Recomendada - administrados de siguientes de código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3db12-218">Example code following recommended practices - managed</span></span>

<span data-ttu-id="3db12-219">El siguiente código de ejemplo utiliza un formato de mensaje no estándar</span><span class="sxs-lookup"><span data-stu-id="3db12-219">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="3db12-220">donde la `cipher_algorithm_id` y `hmac_algorithm_id` identificadores de algoritmo son representaciones de (no estándar) local de la aplicación de los algoritmos.</span><span class="sxs-lookup"><span data-stu-id="3db12-220">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="3db12-221">Estos identificadores pueden tener sentido en otras partes de su protocolo de mensajería existente en lugar de como una secuencia de bytes concatenados.</span><span class="sxs-lookup"><span data-stu-id="3db12-221">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="3db12-222">Este ejemplo también utiliza una única clave maestra para derivar una clave de cifrado y una clave HMAC.</span><span class="sxs-lookup"><span data-stu-id="3db12-222">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="3db12-223">Se proporciona como una comodidad para activar una aplicación ordenados individualmente en una aplicación ordenados dual y animar a mantener las dos claves diferentes como valores.</span><span class="sxs-lookup"><span data-stu-id="3db12-223">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="3db12-224">Más garantiza que la clave HMAC y la clave de cifrado no se pueden sacar partido de sincronización.</span><span class="sxs-lookup"><span data-stu-id="3db12-224">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="3db12-225">Este ejemplo no acepta un <xref:System.IO.Stream> para cifrado o descifrado.</span><span class="sxs-lookup"><span data-stu-id="3db12-225">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="3db12-226">La actual datos formato hace que sea un paso cifrar difícil porque la `hmac_tag` valor precede el texto cifrado.</span><span class="sxs-lookup"><span data-stu-id="3db12-226">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="3db12-227">Sin embargo, este formato se ha elegido porque mantiene todos los elementos de tamaño fijo en el principio para que sea más sencillo el analizador.</span><span class="sxs-lookup"><span data-stu-id="3db12-227">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="3db12-228">Con este formato de datos, descifrado de un paso es posible, aunque se advierte un implementador para llamar a GetHashAndReset y comprobar el resultado antes de llamar a TransformFinalBlock.</span><span class="sxs-lookup"><span data-stu-id="3db12-228">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="3db12-229">Si el cifrado de transmisión por secuencias es importante, puede requerirse un modo AE diferente.</span><span class="sxs-lookup"><span data-stu-id="3db12-229">If streaming encryption is important, then a different AE mode may be required.</span></span>

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
