---
title: servicios criptográficos
description: Información general de los métodos de cifrado y prácticas compatibles con .NET.
ms.date: 07/14/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography [.NET]
- pattern of derived class inheritance
- digital signatures
- asymmetric cryptographic algorithms
- digital signatures, public-key systems
- public keys
- decryption [.NET]
- private keys
- MAC algorithms
- cryptographic algorithms
- private keys, overview
- encryption [.NET]
- security [.NET], encryption
- cryptographic services
- symmetric cryptographic algorithms
- hash
- message authentication codes
- derived class inheritance
- cryptography [.NET], about
- random number generation
ms.assetid: f96284bc-7b73-44b5-ac59-fac613ad09f8
ms.openlocfilehash: 651231dcc41926307e3a46b67c80ba3df1fb25e9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549985"
---
# <a name="cryptographic-services"></a>servicios criptográficos

Las redes públicas como Internet no proporcionan un medio de comunicación segura entre entidades. La comunicación en esas redes es susceptible de que terceras personas, sin autorización, tengan acceso a ella o la modifiquen. La criptografía ayuda a proteger los datos para que no puedan ser vistos, proporciona mecanismos para la detección de datos modificados y facilita un medio de comunicación seguro en canales que, de otra forma, no serían seguros. Por ejemplo, los datos pueden cifrarse con un algoritmo criptográfico y transmitirse en un estado cifrado a una tercera persona, que posteriormente los descifrará. Si un tercero intercepta los datos cifrados, le resultará difícil descifrarlos.

En .NET, las clases del <xref:System.Security.Cryptography> espacio de nombres administran muchos detalles de la criptografía. Algunos son contenedores para implementaciones de sistema operativo, mientras que otros son simplemente implementaciones administradas. No necesita ser un experto en criptografía para utilizar estas clases. Cuando crea una nueva instancia de una de las clases de algoritmos de cifrado, se generan automáticamente claves para facilitar el uso y las propiedades predeterminadas son lo más seguras posible.

En esta información general se proporciona una sinopsis de los métodos y prácticas de cifrado compatibles con .NET, incluidos los manifiestos de ClickOnce.

## <a name="cryptographic-primitives"></a>Primitivos criptográficos

En una situación típica donde se usa la criptografía, dos partes (Alicia y Roberto) se comunican a través de un canal que no es seguro. Ambos desean garantizar que su comunicación no la comprenda nadie que pueda estar escuchando. Además, como Alicia y Roberto se encuentran en ubicaciones remotas, Alicia quiere asegurarse de que la información que recibe de Roberto no la modificó nadie durante la transmisión. Por último, debe asegurarse también de que la información proviene realmente de Roberto y no de alguien que lo suplanta.

La criptografía se utiliza para lograr los objetivos siguientes:

- Confidencialidad: para ayudar a proteger la identidad de un usuario o evitar que se lean sus datos.

- Integridad de los datos: para ayudar a evitar su alteración.

- Autenticación: para garantizar que los datos provienen de una parte concreta.

- Sin rechazo: para evitar que una determinada parte niegue que envió un mensaje.

Para alcanzar estos objetivos, se puede usar una combinación de algoritmos y prácticas conocidas como primitivas criptográficas para crear un esquema criptográfico. En la tabla siguiente se enumeran las primitivas criptográficas y su uso.

|Primitiva criptográfica|Use|
|-----------------------------|---------|
|Cifrado de clave secreta (criptografía simétrica)|Realiza la transformación de los datos para impedir que terceros los lean. Este tipo de cifrado utiliza una clave secreta compartida para cifrar y descifrar los datos.|
|Cifrado de clave pública (criptografía asimétrica)|Realiza la transformación de los datos para impedir que terceros los lean. Este tipo de cifrado utiliza un par de claves pública y privada para cifrar y descifrar los datos.|
|Firmas criptográficas|Ayuda a comprobar que los datos se originan en una parte específica mediante la creación de una firma digital única para esa parte. En este proceso también se usan funciones hash.|
|Valores hash criptográficos|Asigna datos de cualquier longitud a una secuencia de bytes de longitud fija. Los valores hash son únicos estadísticamente; el valor hash de una secuencia de dos bytes distinta no será el mismo.|

## <a name="secret-key-encryption"></a>Cifrado de clave secreta

Los algoritmos de cifrado de clave secreta utilizan una clave secreta única para cifrar y descifrar datos. Debe asegurarse de que agentes no autorizados no obtienen acceso a la clave, ya que cualquier persona que tenga la clave podría utilizarla para descifrar los datos o cifrar sus propios datos y alegar que provienen de usted.

El cifrado de clave secreta también se denomina cifrado simétrico puesto que se utiliza la misma clave para el cifrado y el descifrado. Los algoritmos de cifrado de clave secreta son muy rápidos (comparados con los de clave pública) y resultan adecuados para realizar transformaciones criptográficas en grandes flujos de datos. Los algoritmos de cifrado asimétricos, como RSA, están limitados matemáticamente respecto al volumen de datos que pueden cifrar. Los algoritmos de cifrado simétricos no suelen tener estos problemas.

El tipo de algoritmo de clave secreta denominado cifrado de bloques se utiliza para cifrar un bloque de datos cada vez. Los cifrados de bloques, como Estándar de cifrado de datos (DES), TripleDES y Estándar de cifrado avanzado (CA), transforman criptográficamente un bloque de entrada de *n* bytes en un bloque de salida de bytes cifrados. Si desea cifrar o descifrar una secuencia de bytes, debe hacerlo bloque a bloque. Dado que *n* es pequeño (8 bytes para DES y TripleDES y 16 bytes [valor predeterminado], 24 bytes o 32 bytes para AES), los valores mayores que *n* deben cifrarse bloque a bloque. Los valores que son menores que *n* tienen que ampliarse hasta *n* para que se puedan procesar.

Una forma sencilla de cifrado de bloques es el modo Electronic Codebook (ECB). El modo ECB no se considera un modo seguro porque no utiliza un vector de inicialización para iniciar el primer bloque de texto simple. Para una clave secreta *k*determinada, un cifrado de bloques simple que no utiliza un vector de inicialización codificará el mismo bloque de entrada de texto simple en el mismo bloque de salida de texto cifrado. Por tanto, si hay bloques duplicados dentro la secuencia de texto simple de entrada, habrá bloques duplicados en la secuencia de texto cifrado de salida. Estos bloques de salida duplicados podrían alertar a los usuarios sin autorización sobre la posibilidad de que se haya utilizado un cifrado débil en los algoritmos y los posibles modos de ataque. El modo de cifrado ECB es por tanto bastante vulnerable al análisis, y en última instancia, a la detección de claves.

Las clases de cifrado de bloques que se proporcionan en la biblioteca de clases base utilizan un modo de encadenamiento predeterminado denominado encadenamiento de bloques de cifrado (CBC), aunque este valor puede cambiarse, si así se desea.

El cifrado CBC subsana los problemas asociados con el cifrado ECB utilizando un vector de inicialización (IV) para cifrar el primer bloque de texto simple. Cada uno de los bloques de texto simple siguientes se somete a una operación OR exclusiva bit a bit (`XOR`) con el bloque de texto cifrado anterior antes de cifrarse. Cada bloque de texto cifrado depende por tanto de todos los bloques anteriores. Cuando se utiliza este sistema, los encabezados de los mensajes comunes que un usuario no autorizado podría conocer no pueden utilizarse para aplicar técnicas de ingeniería inversa en una clave.

Un modo de comprometer los datos cifrados con un cifrado CBC consiste en realizar una búsqueda exhaustiva de todas las claves posibles. En función del tamaño de la clave utilizada para realizar el cifrado, este tipo de búsqueda llevará mucho tiempo aunque se utilicen los equipos más rápidos, y, por lo tanto, no es factible. Los tamaños de clave mayores son más difíciles de descifrar. Aunque el cifrado no garantiza totalmente que un adversario no recupere los datos cifrados, aumenta considerablemente la dificultad. Si se tardan tres meses en realizar una búsqueda exhaustiva para recuperar datos que solo son relevantes durante varios días, este método de búsqueda resulta poco práctico.

La desventaja del cifrado de clave secreta es que presupone que dos partes acuerdan una clave y un vector de inicialización, y que se comunican sus valores. El vector de inicialización no se considera secreto y se transmite como texto simple con el mensaje. Sin embargo, la clave debe mantenerse en secreto a salvo de usuarios no autorizados. Debido a estos problemas, el cifrado de clave secreta a menudo se utiliza junto con el cifrado de clave pública para comunicar en privado los valores de la clave y el vector de inicialización.

Supongamos que Alicia y Roberto son dos personas que desean comunicarse a través de un canal que no es seguro. Ellos podrían utilizar el cifrado de clave secreta del modo siguiente: Alicia y Roberto están de acuerdo en utilizar un algoritmo determinado (AES, por ejemplo) con una clave y un vector de inicialización determinados. Alice redacta un mensaje y crea una secuencia de red (quizás una canalización con nombre o correo electrónico de red) en la que se va a enviar el mensaje. A continuación, cifra el texto utilizando la clave y el vector de inicialización y envía el mensaje cifrado y el vector de inicialización a Roberto a través de intranet. Roberto recibe el texto cifrado y lo descifra utilizando el vector de inicialización y la clave acordada anteriormente. Si se intercepta la transmisión, el interceptor no puede recuperar el mensaje original porque no conoce la clave. En este caso, solo debe mantenerse en secreto la clave. En un ejemplo real, Alicia o Roberto genera una clave secreta y utiliza el cifrado (asimétrico) de clave pública para transferir la clave (simétrica) secreta a la otra parte. Para obtener más información sobre el cifrado de clave pública, vea la sección siguiente.

.NET proporciona las siguientes clases que implementan algoritmos de cifrado de clave secreta:

- <xref:System.Security.Cryptography.Aes>

- <xref:System.Security.Cryptography.HMACSHA256>, <xref:System.Security.Cryptography.HMACSHA384> y <xref:System.Security.Cryptography.HMACSHA512>. (Técnicamente, son algoritmos de clave secreta, ya que representan códigos de autenticación de mensajes que se calculan mediante una función hash criptográfica combinada con una clave secreta. Vea [valores hash](#hash-values)más adelante en este artículo).

## <a name="public-key-encryption"></a>Cifrado de clave pública

El cifrado de clave pública utiliza una clave privada que debe mantenerse en secreto y a salvo de los usuarios no autorizados, así como una clave pública que puede comunicarse. La clave pública y la clave privada están vinculadas matemáticamente; los datos cifrados con la clave pública solo pueden descifrarse con la clave privada y los datos firmados con la clave privada solo pueden comprobarse con la clave pública. La clave pública está a disposición de cualquier persona y se utiliza para cifrar los datos que se envían a quien guarda la clave privada. Los algoritmos criptográficos de clave pública también se conocen como algoritmos asimétricos porque se necesita una clave para cifrar los datos y otra para descifrarlos. Una regla criptográfica básica prohíbe la reutilización de claves; además, las dos claves deben ser únicas en cada sesión de comunicación. Sin embargo, en la práctica, las claves asimétricas suelen durar bastante tiempo.

Dos personas (Alicia y Roberto) podrían utilizar el cifrado de clave pública del modo siguiente: en primer lugar, Alicia podría generar un par de claves pública y privada. Si Roberto desea enviar a Alicia un mensaje cifrado, le pide la clave pública. Alicia envía a Roberto su clave pública a través de una red que no es segura y Roberto utiliza esta clave para cifrar un mensaje. Roberto envía el mensaje cifrado a Alicia y ésta lo descifra utilizando su clave privada. Si Roberto recibiera la clave de Alicia a través de un canal que no es seguro, como una red pública, Roberto estaría expuesto a un ataque del tipo "Man in the middle". Por consiguiente, Roberto debe comprobar con Alicia que tiene una copia correcta de su clave pública.

Durante la transmisión de la clave pública de Alicia, un agente no autorizado podría interceptarla. Además, el mismo agente podría interceptar el mensaje cifrado de Roberto. No obstante, el agente no puede descifrar el mensaje con la clave pública. El mensaje solo puede descifrarse con la clave privada de Alicia, que no se ha transmitido. Alicia no utiliza su clave privada para cifrar un mensaje de respuesta a Roberto, porque cualquiera que tenga la clave pública podría descifrarlo. Si Alicia desea enviar un mensaje a Roberto, le pide su clave pública y cifra su mensaje con ella. Seguidamente, Roberto descifra el mensaje utilizando su clave privada asociada.

En este escenario, Alicia y Roberto utilizan un cifrado de clave pública (asimétrica) para transferir una clave secreta (simétrica) y utilizan el cifrado de clave secreta para el resto de la sesión.

En la lista siguiente se incluyen comparaciones entre algoritmos criptográficos de clave pública y de clave secreta:

- Los algoritmos criptográficos de clave pública utilizan un tamaño de búfer fijo mientras que los de clave secreta usan un búfer de longitud variable.

- Los algoritmos de clave pública no se pueden usar para encadenar datos juntos en secuencias como sucede con los de clave secreta, ya que solo pueden cifrarse pequeñas cantidades de datos. Por lo tanto, las operaciones asimétricas no utilizan el mismo modelo de streaming que las simétricas.

- El cifrado de claves públicas tiene un espacio de claves (el intervalo de valores posibles de la clave) mucho mayor que el cifrado de claves secretas. Por tanto, el cifrado de claves públicas es menos vulnerable a los ataques exhaustivos que prueban cada clave posible.

- Al no tener que estar protegidas, las claves públicas resultan fáciles de distribuir, siempre que exista algún mecanismo para comprobar la identidad del remitente.

- Algunos algoritmos de clave pública (como RSA y DSA, aunque no Diffie-Hellman) se pueden utilizar para crear firmas digitales con el fin de comprobar la identidad del remitente de los datos.

- Los algoritmos de clave pública son muy lentos comparados con los de clave secreta y no están diseñados para cifrar grandes cantidades de datos. Son útiles solo para transferir cantidades muy pequeñas de información. Normalmente, el cifrado de clave pública se utiliza para cifrar la clave y el vector de inicialización que serán utilizados por un algoritmo de clave secreta. Después de transferir la clave y el vector de inicialización, el cifrado de clave secreta se utiliza para el resto de la sesión.

.NET proporciona las siguientes clases que implementan algoritmos de clave pública:

- <xref:System.Security.Cryptography.RSA>

- <xref:System.Security.Cryptography.ECDsa>

- <xref:System.Security.Cryptography.ECDiffieHellman>

- <xref:System.Security.Cryptography.DSA>

RSA permite el cifrado y la firma, pero DSA solo se puede usar para la firma. DSA no es tan seguro como RSA y se recomienda RSA. Diffie-Hellman solo se puede usar para la generación de claves. En general, los algoritmos de clave pública tienen una aplicación más limitada que los algoritmos de clave privada.

## <a name="digital-signatures"></a>Firmas digitales

Los algoritmos de clave pública también se pueden usar para formar firmas digitales. Las firmas digitales autentican la identidad de un remitente (si se fía de la clave pública de éste) y ayudan a proteger la integridad de los datos. Con una clave pública generada por Alicia, el remitente de los datos de Alicia puede comprobar que ésta los envió si compara la firma digital de los datos de Alicia y la clave pública de ésta.

Para utilizar criptografía de clave pública con el objeto de firmar digitalmente un mensaje, Alicia aplica primero un algoritmo hash al mensaje para crear una síntesis del mismo. La síntesis del mensaje es una representación compacta y única de los datos. Seguidamente, Alicia cifra la síntesis del mensaje con su clave privada para crear su firma personal. Después de recibir el mensaje y la firma, Roberto descifra esta última utilizando la clave pública de Alicia para recuperar la síntesis del mensaje y envía éste de forma aleatoria mediante el mismo algoritmo hash que utilizó Alicia. Si la síntesis del mensaje que calcula Roberto coincide exactamente con la que ha recibido de Alicia, Roberto puede estar seguro de que el mensaje provino del poseedor de la clave privada y de que no se han modificado los datos. Si Roberto confía en que Alicia es la propietaria de la clave privada, sabe que el mensaje proviene de Alicia.

> [!NOTE]
> Cualquiera puede comprobar una firma, ya que la clave pública del remitente es de dominio público y normalmente se incluye en el formato de firma digital. Este método no mantiene la confidencialidad del mensaje; para que sea secreto, también se debe cifrar.

.NET proporciona las siguientes clases que implementan algoritmos de firma digital:

- <xref:System.Security.Cryptography.RSA>

- <xref:System.Security.Cryptography.ECDsa>

- <xref:System.Security.Cryptography.DSA>

## <a name="hash-values"></a>Valores hash

Los algoritmos hash asignan valores binarios de longitud arbitraria a valores binarios más pequeños de longitud fija, que se denominan valores hash. Un valor hash es una representación numérica de un segmento de datos. Si aplica un algoritmo hash a un párrafo de texto simple y cambia solo una letra del párrafo, el valor hash subsiguiente producirá un valor distinto. Si el valor hash es criptográficamente seguro, su valor cambiará significativamente. Por ejemplo, si se cambia únicamente un solo bit de un mensaje, una función hash segura puede generar un resultado que difiera en un 50 por ciento. Muchos valores de entrada pueden aplicar un algoritmo hash al mismo valor de salida. Sin embargo, técnicamente es poco factible encontrar dos entradas distintas cuyo valor hash sea el mismo.

Dos partes (Alicia y Roberto) podrían utilizar una función hash para asegurar la integridad de los mensajes. Podrían seleccionar un algoritmo hash para firmar sus mensajes. Alicia escribiría un mensaje y, a continuación, crearía un valor hash de ese mensaje utilizando el algoritmo seleccionado. Después seguiría uno de los métodos siguientes:

- Alicia enviaría a Roberto el mensaje de texto simple y el mensaje al que aplicó el algoritmo hash (firma digital). Roberto recibiría el mensaje y le aplicaría el algoritmo hash. A continuación, compararía su valor hash con el valor hash que recibió de Alicia. Si los dos valores hash son idénticos, el mensaje no se ha modificado. Si los valores no son idénticos, el mensaje se modificó después de que Alicia lo escribiera.

  Desgraciadamente, este método no determina la autenticidad del remitente. Cualquiera puede suplantar a Alicia y enviar un mensaje a Roberto. Pueden utilizar el mismo algoritmo hash para firmar su mensaje, y todo lo que Roberto podría determinar es que el mensaje coincide con su firma. Esta es una forma de ataque de tipo "Man in the middle". Para obtener más información, vea [ejemplo de comunicación segura de Cryptography Next Generation (CNG)](/previous-versions/cc488018(v=vs.100)).

- Alicia envía el mensaje de texto simple a Roberto a través de un canal público que no es seguro. Envía a Roberto el mensaje al que aplicó el algoritmo hash a través de un canal privado seguro. Roberto recibe el mensaje de texto simple, le aplica un algoritmo hash y compara el valor hash con el valor hash que se intercambió de forma privada. Si los valores hash coinciden, Roberto sabe dos cosas:

  - que el mensaje no se alteró.

  - que el remitente del mensaje (Alicia) es auténtico.

  Para que este sistema funcione, Alicia debe ocultar el valor hash original a todos excepto a Roberto.

- Alicia envía el mensaje de texto simple a Roberto a través de un canal público que no es seguro y publica el mensaje al que aplicó el algoritmo hash en su sitio web para que esté visible públicamente.

  Este método evita que se manipule el mensaje, ya que impide que nadie modifique el valor hash. Aunque cualquier persona puede leer el mensaje y su valor hash, este valor hash únicamente lo puede modificar Alicia. Un atacante que desee suplantar a Alicia necesitaría tener acceso al sitio web de Alicia.

Ninguno de los métodos anteriores evitará que alguien lea los mensajes de Alicia, ya que se transmiten en texto simple. Para conseguir una seguridad total, normalmente se necesitarán firmas digitales (firma del mensaje) y mecanismos de cifrado.

.NET proporciona las siguientes clases que implementan algoritmos hash:

- <xref:System.Security.Cryptography.SHA256>.

- <xref:System.Security.Cryptography.SHA384>.

- <xref:System.Security.Cryptography.SHA512>.

.NET también proporciona <xref:System.Security.Cryptography.MD5> y <xref:System.Security.Cryptography.SHA1> . Pero los algoritmos MD5 y SHA-1 se han descubierto como inseguros, y ahora se recomienda usar SHA-2. SHA-2 incluye SHA256, SHA384 y SHA512.

## <a name="random-number-generation"></a>generación de números aleatorios

La generación de números aleatorios es propia de muchas operaciones criptográficas. Por ejemplo, las claves criptográficas deben ser lo más aleatorias posible para que no se puedan reproducir. Los generadores de números aleatorios criptográficos deben generar resultados que, mediante cálculos, no se pueden predecir con una probabilidad mayor del cincuenta por ciento. Por tanto, cualquier método para predecir el siguiente bit del resultado no debe ser más eficaz que el cálculo aleatorio. Las clases de la .NET Framework utilizan generadores de números aleatorios para generar claves criptográficas.

La clase <xref:System.Security.Cryptography.RandomNumberGenerator> es una implementación de un algoritmo generador de números aleatorios.

## <a name="clickonce-manifests"></a>Manifiestos de ClickOnce

En el .NET Framework 3,5, las siguientes clases de criptografía permiten obtener y comprobar información sobre las firmas de manifiesto para las aplicaciones que se implementan mediante la [tecnología ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment):

- La clase <xref:System.Security.Cryptography.ManifestSignatureInformation> obtiene información sobre una firma de manifiesto cuando se utiliza la sobrecarga de su método <xref:System.Security.Cryptography.ManifestSignatureInformation.VerifySignature%2A> .

- Puede utilizar la enumeración <xref:System.Security.ManifestKinds> para especificar los manifiestos que se van a comprobar. El resultado de la comprobación es uno de los valores de la enumeración <xref:System.Security.Cryptography.SignatureVerificationResult> .

- La clase <xref:System.Security.Cryptography.ManifestSignatureInformationCollection> proporciona una colección de objetos <xref:System.Security.Cryptography.ManifestSignatureInformation> de solo lectura de las firmas comprobadas.

 Además, las clases siguientes proporcionan información de firma específica:

- <xref:System.Security.Cryptography.StrongNameSignatureInformation> contiene información sobre la firma de nombre seguro de un manifiesto.

- <xref:System.Security.Cryptography.X509Certificates.AuthenticodeSignatureInformation> representa la información sobre la firma Authenticode de un manifiesto.

- <xref:System.Security.Cryptography.X509Certificates.TimestampInformation> contiene información sobre la marca de tiempo de una firma Authenticode.

- <xref:System.Security.Cryptography.X509Certificates.TrustStatus> proporciona un mecanismo sencillo para comprobar si se confía en una firma Authenticode.

## <a name="cryptography-next-generation-cng-classes"></a>Clases de criptografía de próxima generación (CNG)

En el .NET Framework 3,5 y versiones posteriores, las clases de Cryptography Next Generation (CNG) proporcionan un contenedor administrado en torno a las funciones CNG nativas. (CNG es el sustituto de CryptoAPI). Estas clases tienen "CNG" como parte de sus nombres. La clase contenedora de claves <xref:System.Security.Cryptography.CngKey> es fundamental en estas clases contenedoras CNG, pues abstrae el almacenamiento y el uso de claves CNG. Esta clase permite almacenar de forma segura un par de claves o una clave pública y hacer referencia a ella utilizando un nombre de cadena simple. La clase de firma <xref:System.Security.Cryptography.ECDsaCng> y la clase de cifrado <xref:System.Security.Cryptography.ECDiffieHellmanCng> basadas en curvas elípticas pueden utilizar los objetos <xref:System.Security.Cryptography.CngKey> .

La clase <xref:System.Security.Cryptography.CngKey> se utiliza en otras numerosas operaciones, entre las que se incluyen la apertura, creación, eliminación y exportación de claves. También proporciona acceso al identificador de clave subyacente que se va a utilizar en las llamadas directas a las funciones nativas.

El .NET Framework 3,5 también incluye una serie de clases CNG compatibles, como las siguientes:

- <xref:System.Security.Cryptography.CngProvider> mantiene un proveedor de almacenamiento de claves.

- <xref:System.Security.Cryptography.CngAlgorithm> mantiene un algoritmo CNG.

- <xref:System.Security.Cryptography.CngProperty> mantiene las propiedades clave que se utilizan con frecuencia.

## <a name="see-also"></a>Vea también

- [Modelo de criptografía](cryptography-model.md) : describe cómo se implementa la criptografía en la biblioteca de clases base.
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- [Vulnerabilidades de temporalización con descifrado simétrico en modo CBC al usar el relleno](vulnerabilities-cbc-mode.md)
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
