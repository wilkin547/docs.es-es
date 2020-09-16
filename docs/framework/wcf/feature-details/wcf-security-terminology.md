---
title: Terminología de seguridad en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], terminology
- security glossary [WCF]
- security terms [WCF]
ms.assetid: 68dde024-8e51-40ba-804f-ec52d85e9ca9
ms.openlocfilehash: 8941350e46680c4ecaeb9b89fe9e6910c5830bcb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553296"
---
# <a name="wcf-security-terminology"></a>Terminología de seguridad en WCF
Alguna de la terminología utilizada al hablar sobre seguridad puede ser poco familiar. Este tema proporciona breves explicaciones sobre algunos términos de seguridad, pero no está diseñado para proporcionar una documentación completa sobre cada elemento.  
  
 Para obtener más información sobre los términos usados en la documentación de Windows Communication Foundation (WCF), vea [conceptos básicos de Windows Communication Foundation](../fundamental-concepts.md).  
  
 lista de control de acceso (ACL)  
 Lista de protecciones de seguridad que se aplica a un objeto. (Un objeto puede ser un archivo, un proceso, un evento o cualquier otro elemento que tenga un descriptor de seguridad). Una entrada en una ACL es una entrada de control de acceso (ACE). Hay dos tipos de ACL: discrecional y de sistema.  
  
 autenticación  
 El proceso para comprobar que un usuario, equipo, servicio o proceso es quién o lo que dice ser.  
  
 authorization  
 El acto de controlar el acceso y los derechos a un recurso. Por ejemplo, permitir a los miembros de un grupo leer un archivo, pero permitir solo a los miembros de otro grupo modificar el archivo.  
  
 certificado de la entidad de certificación (CA)  
 Identifica la CA emisora de certificados de autenticación de cliente y servidor a los servidores y clientes que los solicitan. Dado que contiene una clave pública que se utiliza en firmas digitales, también se conoce como certificado de *firma*. Si la entidad de certificación es una entidad raíz, el certificado de entidad de certificación se puede denominar *certificado raíz*. También se conoce como *certificado de sitio*.  
  
 Jerarquía de la CA  
 Una jerarquía de la CA contiene varias CA. Está organizada de modo que cada CA esté certificada por otra CA en un nivel superior de la jerarquía hasta que se alcance la parte superior de la jerarquía, también conocida como *entidad de certificación raíz*.  
  
 certificado  
 Una instrucción firmada digitalmente que contiene información sobre una entidad y la clave pública de la entidad, enlazando, por tanto, estas dos partes de información. Una organización de confianza (o entidad) emite un certificado, llamada “entidad emisora de certificados”, después de que la autoridad haya comprobado que la entidad es quién dice ser.  
  
 Los certificados pueden contener tipos diferentes de datos. Por ejemplo, un certificado X.509 incluye el formato del certificado, el número de serie del certificado, el algoritmo utilizado para firmar el certificado, el nombre de la CA que emitió el certificado, el nombre y clave pública de la entidad que solicita el certificado, y la firma de la CA.  
  
 almacén de certificados  
 Por lo general, un almacenamiento permanente donde se almacenan los certificados, las listas de certificados revocados (CRL) y las listas de certificados de confianza (CTL). Es posible, sin embargo, crear y abrir un almacén de certificados solamente en memoria al trabajar con certificados que no necesiten colocarse en un almacenamiento permanente.  
  
 claims  
 Información pasada de una entidad a otra utilizada para establecer la identidad del remitente. Por ejemplo, un token de contraseña y nombre de usuario, o un certificado X.509.  
  
 certificado de cliente  
 Hace referencia a un certificado utilizado para la autenticación de cliente, como la autenticación en un explorador web en un servidor web. Cuando un cliente del explorador web intenta obtener acceso a un servidor web seguro, el cliente envía su certificado al servidor para permitirle comprobar la identidad del cliente.  
  
 credentials  
 Datos de inicio de sesión previamente autenticados que utiliza una entidad de seguridad para establecer su propia identidad, como una contraseña o un vale del protocolo Kerberos. Las credenciales se utilizan para controlar el acceso a los recursos.  
  
 datos resumidos  
 Un tipo de contenido de datos definido por el estándar criptográfico de clave pública (PKCS) #7 que consiste de cualquier tipo de datos más un hash del mensaje (resumen) del contenido.  
  
 firma digital  
 Datos que enlazan la identidad de un remitente con la información que se está enviando. Una firma digital se puede empaquetar junto con cualquier mensaje, archivo o cualquier otra información codificada o transmitida por separado. Las firmas digitales se utilizan en entornos de claves públicas y proporcionan servicios de integridad y autenticación.  
  
 encoding  
 El proceso de convertir datos en una secuencia de bits. La codificación es parte del proceso de serialización que convierte datos en una secuencia de unos y ceros.  
  
 par de la clave de intercambio  
 Un par de claves pública/privada usada para cifrar claves de sesión para que se puedan almacenar e intercambiar con otros usuarios de forma segura.  
  
 hash  
 Un valor numérico de tamaño fijo obtenido aplicando una función matemática (vea algoritmo hash) a una cantidad arbitraria de datos. Normalmente, los datos incluyen datos aleatorios, conocido como un *nonce*. El servicio y cliente aportan nonces de intercambio para aumentar la complejidad del resultado. El resultado también se conoce como una *síntesis del mensaje*. Enviar un valor hash es más seguro que enviar datos confidenciales, como una contraseña, aun cuando la contraseña esté cifrada. El remitente y receptor del hash deben usar el mismo algoritmo hash y nonces para que, una vez recibido, se pueda comprobar el hash.  
  
 algoritmo de hash  
 Un algoritmo utilizado para generar un valor hash de una parte de datos, como un mensaje o clave de sesión. Entre los algoritmos más comunes de hash se incluyen: MD2, MD4, MD5 y SHA-1.  
  
 Protocolo Kerberos  
 Un protocolo que define cómo los clientes interactúan con un servicio de autenticación de red. Los clientes obtienen vales del Centro de distribución de claves Kerberos (KDC) y presentan estos vales a los servidores cuando se establecen las conexiones. Los vales de Kerberos representan las credenciales de red del cliente.  
  
 autoridad de seguridad local (LSA)  
 Un subsistema protegido que autentica e inicia sesión a los usuarios en el sistema local. LSA también guarda información sobre todos los aspectos de seguridad local de un sistema, colectivamente conocida como la directiva de seguridad local del sistema.  
  
 Negotiate  
 Un proveedor de compatibilidad de seguridad (SSP) que actúa como un nivel de aplicación entre la Interfaz del proveedor de compatibilidad de seguridad (SSPI) y el resto de SSP. Cuando una aplicación llama en SSPI para iniciar sesión en una red, puede especificar un SSP para que procese la solicitud. Si la aplicación especifica `Negotiate`, `Negotiate`, analiza la solicitud y escoge el mejor SSP para administrar la solicitud en función de la directiva de seguridad configurada por cliente.  
  
 valor de seguridad  
 Un valor generado de forma aleatoria y que se utiliza para acabar con los ataques basados en “repeticiones”.  
  
 no rechazo  
 La capacidad para identificar a los usuarios que realizaron ciertas acciones, contrarrestando de manera irrefutable cualquier intento de negación de responsabilidades por parte de un usuario. Por ejemplo, un sistema puede registrar el identificador de un usuario cada vez que se elimine un archivo.  
  
 Estándar de criptografía de clave pública (PKCS)  
 Especificaciones generadas por RSA Data Security, Inc. en cooperación con desarrolladores de sistemas seguros de todo el mundo para acelerar la implementación de la criptografía de clave pública.  
  
 PKCS #7  
 Estándar de sintaxis de mensajes criptográficos. Una sintaxis general para los datos a los que se puede aplicar la criptografía, como cifrado y firmas digitales. También proporciona la sintaxis para difundir certificados o listas de certificados revocados y otros atributos de mensaje, como marcas de tiempo, al mensaje.  
  
 plaintext  
 Un mensaje no cifrado. Los mensajes de texto no cifrado a veces se denominan mensajes de *texto no cifrado* .  
  
 privilegio  
 El derecho de un usuario para realizar varias operaciones relacionadas con el sistema, como apagar el sistema, cargar los controles de dispositivos o cambiar la hora del sistema. Un token de acceso del usuario contiene una lista de los privilegios que el usuario o los grupos de usuarios tienen.  
  
 clave privada  
 La mitad secreta de un par de claves utilizada en un algoritmo de clave pública. Las claves privadas se utilizan normalmente para cifrar una clave de sesión simétrica, firmar digitalmente un mensaje o descifrar un mensaje cifrado con la clave pública correspondiente. Vea también “clave pública”.  
  
 proceso  
 El contexto de seguridad bajo el que se ejecuta una aplicación. Normalmente, el contexto de seguridad está asociado a un usuario, por lo que todas las aplicaciones que se ejecutan bajo un proceso determinado toman los permisos y privilegios del usuario propietario.  
  
 par de clave pública y privada  
 Un conjunto de claves criptográficas utilizado para la criptografía de clave pública. Para cada usuario, un proveedor de servicios de cifrado (CSP) mantiene normalmente dos pares de claves pública y privada: un par de claves de intercambio y un par de claves de firma digital. Ambos pares de claves se mantienen de una sesión a otra.  
  
 clave pública  
 Una clave criptográfica utilizada normalmente al descifrar una clave de sesión o una firma digital. La clave pública también se puede utilizar para cifrar un mensaje, garantizando que solo la persona con la clave privada correspondiente puede descifrar el mensaje.  
  
 cifrado de clave pública  
 Cifrado que utiliza un par de claves, una clave para cifrar los datos y la otra clave para descifrar los datos. Por el contrario, los algoritmos de cifrado simétricos usan la misma clave para cifrado y descifrado. En la práctica, la criptografía de clave pública se utiliza normalmente para proteger la clave de sesión que usa un algoritmo de cifrado simétrico. En este caso, la clave pública se utiliza para cifrar la clave de sesión, que, a su vez, fue utilizada para cifrar algunos datos, y la clave privada se utiliza para el descifrado. Además de para proteger las claves de sesión, la criptografía de clave pública también se puede utilizar para firmar digitalmente un mensaje (mediante la clave privada) y validar la firma (mediante la clave pública).  
  
 infraestructura de clave pública (PKI)  
 Una infraestructura que proporciona un conjunto integrado de servicios y herramientas administrativas para crear, implementar y administrar aplicaciones de claves públicas.  
  
 rechazo  
 La capacidad de un usuario de negar falsamente el haber realizado una acción cuando el resto de partes no pueden demostrar lo contrario. Por ejemplo, un usuario que elimina un archivo y que puede negar con éxito el haberlo hecho.  
  
 entidad raíz  
 La CA que se encuentra en la parte superior de una jerarquía de la CA. La entidad emisora raíz certifica CA en el siguiente nivel de la jerarquía.  
  
 Algoritmo hash seguro (SHA)  
 Un algoritmo hash que genera una síntesis del mensaje. SHA se utiliza con el Algoritmo de firma digital (DSA) en el Estándar de firmas digitales (DSS), entre otros. Hay cuatro variedades de SHA: SHA-1, SHA-256, SHA-384 y SHA-512. SHA-1 genera una síntesis del mensaje de 160 bits. SHA-256, SHA-384 y SHA-512 generan síntesis de mensajes de 256, 384 y 512 bits, respectivamente. SHA fue desarrollado por el National Institute of Standards and Technology (NIST, Instituto nacional de estándares y tecnología) y la National Security Agency (NSA, Agencia de seguridad nacional).  
  
 Capa de sockets seguros (SSL)  
 Un protocolo que proporciona comunicaciones de red seguras mediante una combinación de tecnología de claves públicas y secretas.  
  
 contexto de seguridad  
 Las reglas o atributos de seguridad que están en vigor actualmente. Por ejemplo, el usuario actual con sesión iniciada en el equipo o el número de identificación personal escrito por el usuario de tarjeta inteligente. Para SSPI, un contexto de seguridad es una estructura de datos opaca que contiene datos de seguridad pertinentes a una conexión, como una clave de sesión o una indicación de la duración de la sesión.  
  
 entidad de seguridad  
 Una entidad reconocida por el sistema de seguridad. Las entidades de seguridad pueden incluir usuarios humanos así como procesos autónomos.  
  
 proveedor de compatibilidad con seguridad (SSP)  
 Una biblioteca de vínculo dinámico (DLL) que implementa la SSPI haciendo que uno o más paquetes de seguridad estén disponibles para las aplicaciones. Cada paquete de seguridad proporciona asignaciones entre las llamadas de funciones de SSPI de una aplicación y las funciones de un modelo de seguridad real. Los paquetes de seguridad admiten protocolos de seguridad como la autenticación Kerberos y Microsoft LAN Manager (LanMan).  
  
 Interfaz del proveedor de compatibilidad con seguridad (SSPI)  
 Una interfaz común entre aplicaciones del nivel de transporte, como la llamada a procedimiento remoto de Microsoft (RPC), y los proveedores de seguridad, como la seguridad distribuida de Windows. SSPI permite a una aplicación de transporte llamar a uno de varios proveedores de seguridad para obtener una conexión autenticada. Estas llamadas no requieren un conocimiento extenso de los detalles del protocolo de seguridad.  
  
 servicio de token de seguridad  
 Los servicios diseñaron para emitir y administrar tokens de seguridad personalizados (tokens emitidos) en un escenario de múltiples servicios. Los tokens personalizados normalmente son tokens de lenguaje de marcado de aserciones de seguridad (SAML) que incluyen una credencial personalizada.  
  
 certificado de servidor  
 Hace referencia a un certificado utilizado para la autenticación de servidores, como la autenticación de un servidor web en un explorador web. Cuando un cliente del explorador web intenta obtener acceso a un servidor web seguro, el servidor envía su certificado al explorador para permitirle comprobar la identidad del servidor.  
  
 hora de sesión  
 Un intercambio de mensajes bajo la protección de una única parte de material para claves. Por ejemplo, las sesiones SSL utilizan una clave única para devolver varios mensajes hacia delante y hacia detrás bajo esa clave.  
  
 clave de sesión  
 Una clave generada de forma aleatoria que se utiliza una vez y, a continuación, se descarta. Las claves de sesión son simétricas (se utilizan para el cifrado y el descifrado). Se envían con el mensaje, protegidas por cifrado con una clave pública del destinatario previsto. Una clave de sesión está compuesta de un número aleatorio de aproximadamente 40 a 2.000 bits.  
  
 credenciales complementarias  
 Credenciales para el uso en la autenticación de una entidad de seguridad en dominios de seguridad externos.  
  
 cifrado simétrico  
 Cifrado que utiliza una clave única tanto para el cifrado como para el descifrado. Se prefiere el cifrado simétrico si se van a cifrar cantidades grandes de datos. Algunos de los algoritmos de cifrado simétrico más comunes son RC2, RC4 y Estándar de cifrado de datos (DES).  
  
 Vea también "cifrado de clave pública."  
  
 clave simétrica  
 Una clave única utilizada para el cifrado y el descifrado. Las claves de sesión son normalmente simétricas.  
  
 token (token de acceso)  
 Un token de acceso contiene la información de seguridad para una sesión de inicio. El sistema crea un token de acceso cuando un usuario inicia sesión, y cada proceso ejecutado en nombre del usuario tiene una copia del token. El token identifica al usuario, los grupos del usuario y los privilegios del usuario. El sistema utiliza el token para controlar el acceso a los objetos que se pueden proteger y controlar la capacidad del usuario para realizar varias operaciones relacionadas con el sistema en el equipo local. Hay dos tipos de tokens de acceso, principal y de suplantación.  
  
 nivel de transporte  
 El nivel de red que es responsable de la calidad de servicio y de la entrega precisa de la información. Entre las tareas realizadas en esta capa se encuentran la corrección y detección de errores.  
  
 lista de confianza (lista de certificados de confianza o CTL)  
 Una lista predefinida de elementos firmados por una entidad de confianza. Un CTL puede ser cualquier cosa, como una lista de hash de certificados o una lista de nombres de archivos. La entidad de la firma autentica (aprueba) todos los elementos de la lista.  
  
 proveedor de confianza  
 El software que decide si un archivo determinado es o no de confianza. Esta decisión se basa en el certificado asociado al archivo.  
  
 nombre principal del usuario (UPN)  
 Un nombre de cuenta de usuario (a veces denominado *nombre de inicio de sesión de usuario*) y un nombre de dominio que identifica el dominio en el que se encuentra la cuenta de usuario. Éste es el uso estándar para iniciar sesión en un dominio de Windows. El formato es: someone@example.com (como para una dirección de correo electrónico).  
  
> [!NOTE]
> Además del formulario de UPN estándar, WCF acepta los UPN en formato de nivel inferior, por ejemplo, cohowinery. com\someone.  
  
 X.509  
 Un estándar reconocido internacionalmente para los certificados que define sus partes necesarias.  
  
## <a name="see-also"></a>Vea también

- [Conceptos básicos de Windows Communication Foundation](../fundamental-concepts.md)
- [Conceptos de seguridad](security-concepts.md)
- [Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
